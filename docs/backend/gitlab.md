# GitLab

## Ubuntu 20.04 安装GitLab

1. 安装前置依赖
```shell
sudo apt-get update
sudo apt-get install -y curl openssh-server ca-certificates tzdata perl
```

2. 添加GitLab软件包仓库
```shell
curl https://packages.gitlab.com/install/repositories/gitlab/gitlab-ee/script.deb.sh | sudo bash
```
>gitlab-ee是企业版，需要许可，但是不提供许可也可以使用社区版的完整功能，gitlab-ce是社区版，建议安装gitlab-ee。

3. 安装GitLab
```shell
sudo EXTERNAL_URL="http://gitlab.ledvance.com" apt-get install gitlab-ee
```
>设置GitLab的域名时，如果使用https，则会自动向[Let's Encrypt](https://letsencrypt.org/)申请证书。

4. 解决Nginx冲突

  当本机同时存在Nginx时，GitLab会出现冲突，需要解决。否则跳过此步骤。

  禁用GitLab捆绑的Nginx
  ```shell
  sudo vi /etc/gitlab/gitlab.rb
  # 加入以下内容
  nginx['enable'] = false
  gitlab_workhorse['listen_network'] = 'tcp'
  gitlab_workhorse['listen_addr'] = '127.0.0.1:8633'
  # 保存
  :wq
  # 重启GitLab
  sudo gitlab-ctl reconfigure
  ```
  本地Nginx新增代理配置
  ```shell
  sudo vi /etc/nginx/conf.d/gitlab.conf

  # 加入以下内容
  server {
    listen 80;
    server_name gitlab.ledvance.com;

    location / {
      root html;
      index index.html index.htm;
      proxy_pass http://127.0.0.1:8633;
    }
  }

  # 保存
  :wq

  # 重启Nginx
  sudo service nginx restart
  ```

5. 更改用户注册选项
   
  使用root账户登录，按下图步骤操作
  ![更改用户注册选项](./images/%E6%9B%B4%E6%94%B9GitLab%E6%B3%A8%E5%86%8C%E9%80%89%E9%A1%B9.png "xxx")

6. 配置使用SMTP发送邮件
  修改配置文件
  ```shell
  sudo vi /etc/gitlab/gitlab.rb
  # 更改以下内容
  ### GitLab email server settings
  gitlab_rails['smtp_enable'] = true
  gitlab_rails['smtp_address'] = "smtp.office365.com"
  gitlab_rails['smtp_port'] = 587
  gitlab_rails['smtp_user_name'] = "username@outlook.com"
  gitlab_rails['smtp_password'] = "password"
  gitlab_rails['smtp_domain'] = "office365.com"
  gitlab_rails['smtp_authentication'] = "login"
  gitlab_rails['smtp_enable_starttls_auto'] = true
  gitlab_rails['smtp_tls'] = false # 设为false，否则会出现错误
  gitlab_rails['smtp_openssl_verify_mode'] = 'none'

  ### Email Settings
  gitlab_rails['gitlab_email_enabled'] = true
  gitlab_rails['gitlab_email_from'] = 'username@outlook.com'
  gitlab_rails['gitlab_email_display_name'] = 'GitLab Server'

  # 保存
  :wq

  # 重启GitLab
  sudo gitlab-ctl reconfigure

  # 测试邮件发送
  sudo gitlab-rails console
  Notify.test_email('n.liu@ledvance.com', 'Subject', 'Content').deliver_now
  ```

7. 访问GitLab
    1. 在浏览器中输入地址：http://gitlab.ledvance.com
    2. 注册账户，并确认邮件
    3. 登录账户，即可正常创建项目