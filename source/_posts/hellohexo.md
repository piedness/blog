---
title: Hello Hexo
date: 2023-06-06 14:26:54
index_img: https://pic1.imgdb.cn/item/636c6ef216f2c2beb1a15627.jpg
banner_img: https://pic1.imgdb.cn/item/636c6ef216f2c2beb1a15627.jpg
excerpt: 从零开始的 Hexo 生活！
category: hexo
sticky: 9998
---


### 新建 GitHub Repository

名称设置为：username.github.io，后续访问站点就为此网址。

[百度经验：新建GitHub Repository](https://jingyan.baidu.com/article/acf728fd64b5a2f8e510a31d.html)

### 安装Git和Node.js

[Git](https://git-scm.com/downloads)
[Git镜像站](https://npm.taobao.org/mirrors/git-for-windows/)
[Node.js](https://nodejs.org/en/download/)
[CSDN：安装Git和Node.js](https://blog.csdn.net/weixin_44863436/article/details/125079036)

### 安装hexo在本地建站并安装next主题文件

win+r 打开cmd

```
cd  D:\blog (blog目录)
```

安装hexo

```
npm install -g hexo-cli
```

建站

```
hexo init
```

安装next主题

```
git clone https://github.com/theme-next/hexo-theme-next themes/next
```

[参考](https://segmentfault.com/a/1190000017986794)

### 本地新建ssh，关联githubpage并配置blog config.yml

在blog文件夹下右击打开gitbash

· 配置本地git账户
```
git config --global user.name "用户名"
git config --global user.email "邮箱地址"
```

· 生成密钥 SSH key

```
ssh-keygen -t rsa -C
```

三次回车，即可生成 ssh key。

· 修复文件

```
ssh-agent -s
ssh-agent bash
ssh-add ~/.ssh/id_rsa_name
```


· 复制ssh到剪贴板
```
clip < ~/.ssh/id_rsa.pub
```

· 进入github账号网页，在settings页面下，SSH and GPG keys下new SSH key，然后将id_rsa.pub里的内容复制到Key中，完成后Add SSH Key。

· 验证Key
```
ssh -T git@github.com
```
输入yes确认

### 将本地站点推送至github Repository

打开项目根目录下的 config.yml 配置文件配置参数。拉到文件末尾，填上如下配置:
```
theme: next

deploy:
       type: git
       repo:
          github: https://github.com/pieches/pieches.github.io.git
```

· 安装deployer完成站点推送
```
npm install hexo-deployer-git --save
hexo g -d
```

稍后访问网址：https://pieches.github.io 就可以看到博客已经上线啦！！ 


### 插件示例

#### 音乐
```
{% meting "60198" "netease" "playlist" "autoplay" "mutex:false" "listmaxheight:340px" "preload:none" "theme:#ad7a86"%}
```


#### 字体
修改单页md的字体：
```
<style>
  @import url('https://fonts.font.im/css?family=Merienda');
  /* 设置整个页面的字体 */
  html, body, .markdown-body {
    font-family: Merienda,KaiTi,"Microsoft YaHei",Georgia, sans, serif;
    font-size: 15px;
  }

  /* 只设置 markdown 字体 */
  .markdown-body {
    font-family: Merienda,KaiTi,"Microsoft YaHei",Georgia, sans, serif;
    font-size: 15px;
  }
</style>

```

设置单页中英文字体
```
<link rel="stylesheet" href="https://cdn.staticfile.org/lxgw-wenkai-screen-webfont/1.6.0/lxgwwenkaiscreen.css" media="print" onload="this.media='all'">

<style>
  @import url('https://fonts.font.im/css?family=Merienda');
  
  html, body, .markdown-body :lang(zh){
    font-family: "LXGW WenKai Screen",  serif;
    font-size: 15px;
  }


  html, body, .markdown-body :lang(en){
    font-family: Merienda,"LXGW WenKai Screen",  serif;
    font-size: 15px;
  }

</style>
```
### 图片
{% gi 5 2-2-1 %}
  ![](https://pic1.imgdb.cn/item/636c6eef16f2c2beb1a15217.jpg)
  ![](https://pic1.imgdb.cn/item/636c6ef116f2c2beb1a15419.jpg)
  ![](https://pic1.imgdb.cn/item/636c6ef216f2c2beb1a15627.jpg)
  ![](https://pic1.imgdb.cn/item/636c6ef416f2c2beb1a157e6.jpg)
  ![](https://pic1.imgdb.cn/item/636c6ef516f2c2beb1a15963.jpg)
{% endgi %}

```
{% gi 5 2-2-1 %}
  ![](https://pic1.imgdb.cn/item/636c6eef16f2c2beb1a15217.jpg)
  ![](https://pic1.imgdb.cn/item/636c6ef116f2c2beb1a15419.jpg)
  ![](https://pic1.imgdb.cn/item/636c6ef216f2c2beb1a15627.jpg)
  ![](https://pic1.imgdb.cn/item/636c6ef416f2c2beb1a157e6.jpg)
  ![](https://pic1.imgdb.cn/item/636c6ef516f2c2beb1a15963.jpg)
{% endgi %}
```

## 参考
[^1]: <https://pieches.github.io>
[NexT官方github]: <https://github.com/theme-next/hexo-theme-next>
[Next旧网址]: <http://theme-next.iissnan.com/>
[Hexo官方文档]: <https://hexo.io/zh-cn/docs/>
[live2d安装]: <https://blog.csdn.net/BIT_666/article/details/107835822?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165864926116781790781408%2522%252C%2522scm%2522%253A%252220140713.130102334.pc%255Fblog.%2522%257D&request_id=165864926116781790781408&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~blog~first_rank_ecpm_v1~rank_v31_ecpm-18-107835822-null-null.185^v2^tag_show&utm_term=Live2D%20%E5%8D%9A%E5%AE%A2&spm=1018.2226.3001.4450>
[ssh-agent 服务是否启动]: <https://blog.csdn.net/qq_34815826/article/details/125099213?spm=1001.2101.3001.6650.5&depth_1-utm_relevant_index=8>