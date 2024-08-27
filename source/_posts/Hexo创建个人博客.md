---
title: Hexo创建个人博客
date: 2024-08-21 20:30:07
tags:
---

1. 登录https://github.com/，点击New，填写放置资源仓库名称(blog-resource)，勾选【Public】，勾选【Add a README file】
2. 生成Token令牌，右上角头像--》Settings--》Developer settings--》Personal Access tokens--》Tokens(classic)--》Generate New Token
	
3. Typora--》设置--》图像，安装upic（https://blog.svend.cc/upic/）
4. 登录https://github.com/，点击New，填写放置仓库名称(xxx.github.io)，勾选【Public】，勾选【Add a README file】
5. 配置upic，把blog-resource仓库配置进去
6. Hexo安装
    6.1 下载nodejs，
    npm -v
    npm config set registry https://registry.npm.taobao.org
    失败的话换npm config set registry https://registry.npmmirror.com 
    npm config get registry
    sudo npm install hexo-cli -g
    npm install hexo-deployer-git --save
    hexo init blog
    cd blog
    npm install
    文章名
    --更换主题(https://hexo.io/themes/index.html)
    选择合适的主题，进入对应仓库下载Release版本,将下载下来的主题放到themes文件夹内，复制这个主题的_config_yml到blog目录，文件名为_config.xxx.yml,然后将xxx配置到_confg.yml的theme后面

    --创建新博客
    hexo new xxx
    --启动本地服务
    hexo s
    --生成网页
    hexo g
    --部署
    hexo d
    --部署前先生成
    hexo clean && hexo g -d

7. Hexo配置github
    git config --global user.name "xxx"
    git config --global user.email "xxx@qq.com"
    ssh-keygen -t rsa -C "xxx@qq.com"
    cat ~/.ssh/id_rsa.pub
    将这个内容粘贴到头像--》Settings--》SSH and GPG keys--》New SSH key
    检测时候成功：ssh -T git@github.com

    _config.yml文件中，找到Deployment，然后按照如下修改：
    deploy:
    type: git
    repo: git@github.com:xxx/xxx.github.io.git
    branch: master

    hexo clean && hexo g -d
    输入邮箱和token

    访问：http://xxx.github.io

