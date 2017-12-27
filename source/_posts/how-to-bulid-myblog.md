---
title: how to bulid myblog
date: 2017-12-18 16:11:47
categories:
- blog
tags: 
- hexo
copyright: true
---
#### 一、development environment
1. download nodejs
2. download git
3. download hexo
```
npm install -g hexo
```

#### 二、build a local blog
1. create a folder, like **_myblob_**
2. enter the folder and run git to gengearte the HEXO template
```
cd myblob
hexo init
```
3. install dependency
```
npm install
```
4. Finally,run **_hexo server_** to run program
![](/images/hexo-server.png)
5. access [localhost:4000](localhost:4000)
![](/images/hexo.png)


#### 三、connect blog and github
1. first, create a new repository that name **_yourGithubName.github.io_**
2. open the **_ _config.yml_** configuraton file the local floder that name myblog,and set the type to git
```
deploy:
  type: git
  repository: https://github.com/yourGithubName/yourGithubName.github.io.git
  branch: master
```
3. install hexo-deployer-git
```
npm install hexo-deployer-git --save
```
4. generate local static files
```
hexo g
or
hexo generate
```
5. push local static files to github, run **_hexo d_** or **_hexo deploy_**
![](/images/hexo-d.png)
6. Finally, open the browser and access [http://yourGithubName.github.io](http://Hbingbing.github.io)



#### 四、last but not least
1. In the **_ _config.yml_** configuration file, there is a space after ":". If you forget this space,it run fail.
2. When you run **_hexo server_**, if return "Error: watch ENOSPC ...".
- First, run **_npm dedupe_**. 
- If always return error,then run **_echo fs.inotify.max_user_watches=524288 | sudo tee -a /etc/sysctl.conf && sudo sysctl -p_**.
- More detail please access [https://hexo.io/zh-cn/docs/troubleshooting.html](https://hexo.io/zh-cn/docs/troubleshooting.html)

#### 五、start publish your blog
1. run **_hexo new yourbolgname_** and you can find it in the **_source/_post_** directory
```
hexo new "hello world"
```
2. write with the [markdown](https://oncemore2020.github.io/blog/markdown-in-action/) syntax
![](/images/new-blog.png)

