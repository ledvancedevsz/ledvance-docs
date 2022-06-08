# 快速开始
  本章将介绍如何快速使用本文档系统。

  本文档系统基于[docsify](https://docsify.js.org/#/zh-cn/)，使用[markdown](https://markdown.com.cn/basic-syntax/)语法进行编辑，md文件可以使用[VS Code](https://code.visualstudio.com/download "VS Code下载地址")或者记事本进行编辑。

## 获取源码
  文档内容托管在[GitHub](https://github.com/ledvancedevsz/ledvance-docs)，因此在操作文档前应先获取文档源码。如果还未安装[git](https://git-scm.com/downloads "git下载地址")，请先安装。
  ```bash
  git clone git@github.com:ledvancedevsz/ledvance-docs.git
  ```

## 新增文档
### 新增分类
  假如要新增一个Flutter分类，那么，需要先在docs目录下新建一个文件夹，取名**flutter**。
  >你可以创建一个*docs/flutter/README.md*文件，作为路由的默认页面。
  
  并在*docs/_sidebar.md*文件中添加对应的目录描述。
  ```markdown
  * [Flutter](flutter/)
  ```
  >由于启用了嵌套目录，所以点击每个分类名都会跳转到对应的目录。

### 新增文档
  要新增一份flutter教学文档，可以在*docs/flutter*目录下新建一个文件，取名**flutter-study.md**，并在*docs/flutter/_sidebar.md*文件中添加对应的目录描述。
  ```markdown
  * [Flutter学习](flutter/flutter-study.md)
  ```

### 新增内容
  编辑*docs/flutter/flutter-study.md*文件，添加文档内容。
  ````markdown
  # 一级标题
  ## 二级标题
  ### 三级标题
  正文内容
  ```
  代码块
  ```
  ````
  > flutter-study.md文件中的二级标题将会出现在左侧菜单栏中。

## 编辑文档
  找到需要编辑的md文件，按照markdown语法编辑即可。

## 删除文档
  当要删除文档时，先删除对应分类下*_sidebar.md*文件中的目录说明，在删除对应的md文件即可。

## 提交文档
  当文档新增、修改、删除完成后，我们需要将其提交到GitHub，其他人才能够访问到更新的文档内容。
  ```bash
  git add .
  git commit -m "update docs"
  git push
  ```

至此，文档系统的快速开始就完成了。