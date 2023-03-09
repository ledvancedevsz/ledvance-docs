## NPM包发布流程

### 1、切换官方源
```shell
npm config set registry https://registry.npmjs.org
```

### 2、登录
```shell
npm login
# username: ledvance
# password: ledvance@2021
# email: app.developer@ledvance.com
```

### 3、修改版本
```shell
npm oldVersion newVersion
```

### 4、发布
```shell
npm publish --access public
```
