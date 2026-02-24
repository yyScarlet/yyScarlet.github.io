---
title: ''
date: '2026-02-07 16:57:44'
updated: '2026-02-24 18:53:46'
tags:
  - git
permalink: /post/hexo-s-fluid-theme-detailed-modification-tutorial-1wjffk.html
comments: true
toc: true
---



# 

首先所有有关主题的修改都是在config.fluid.yml这个文件中进行，所以在修改的过程中**建议备份一份_config.fluid.yml**，并且将**config.fluid.yml至于myblogs根目录下，** YML文件对于缩进的严格程度很高，如果不小心调整了文件的缩进，会在推送的过程中对该文件进行报错，如下：

![屏幕截图 2026-02-01 135826](https://yyscarlet.github.io/img/%E5%B1%8F%E5%B9%95%E6%88%AA%E5%9B%BE%202026-02-01%20135826-20260224185339-ylu5uwa.png)

所以备份一份config.fluid.yml文件对你的修改是有备无患的。

‍

## **一.有关banner image的修改**

首页（index）的Banner头图：在配置文件中，index部分下的banner_img。

文章页（post）的Banner头图：post部分下的banner_img。

归档页（archive）的Banner头图：archive部分下的banner_img。

分类页（category）的Banner头图：category部分下的banner_img。

标签页（tag）的Banner头图：tag部分下的banner_img。

关于页（about）的Banner头图：about部分下的banner_img。  
每个page都可以设置不同的图片，我的修改方式如下：

1.在myblogs的根目录下的source中创建一个文件夹img，里面专门放入你的图片，路径示例如下：**D:\yyScarlet.github.io\myblogs\source\img**，还有图片的命名，最好和你放置的位置有关，比如归档也的banner图片，可以命名为archive.jpg

2.修改config.fluid.yml,你可以使用记事本打开config.fluid.yml文件，在编辑查找中输入banner_img，方便你定位到修改的位置，然后对img/后面的内容进行修改即可，修改为你对图片的命名，比如banner_img: /img/**archive.jpg**

3.**以下所有代码操作都在myblogs根目录的git bash中进行**，在本地中生成http://localhost:4000，检查一下效果

```undefined
hexo clean
hexo g
hexo s
```

‍

4.检查完以后提交图片至git，如果你按照我上面的建议进行命名，可以直接复制该代码

```undefined
git add source/img/index.jpg
git add source/img/about.jpg
git add source/img/my-avatar.jpg
git add source/img/my-favicon.jpg
git add source/img/tag.jpg
git add source/img/category.jpg
git add source/img/archive.jpg
```

‍

5.记得修改配置文件

```undefined
git add _config.fluid.yml
```

6.保存到本地仓库，将文件推送到github

```undefined
git commit -m "更换tag,my-favicon,category,archive等封面"
git push origin main
```

7最后一步是执行最后的上线操作  

```undefined
hexo d
```

## 二.博客名称设计

1.首先在config.fluid.yml修改好你的blog_title为你想要的名称，接下来在myblogs的source文件中，创建文件夹css，路径如下：**D:\yyScarlet.github.io\myblogs\source\css，** 接下来你可以上网搜索或者问AI，让他编写你想要的添加发光效果CSS，我的CSS代码如下，大家可以直接复制应用：

```undefined
/* 奢华金色发光标题 - 专为 yyScarlet's BLOG 设计 */
.navbar-brand {
    /* 1. 核心金色渐变文字 */
    background: linear-gradient(90deg, #FFD700 0%, #FFEC8B 25%, #FFFACD 50%, #FFEC8B 75%, #FFD700 100%);
    -webkit-background-clip: text;
    background-clip: text;
    color: transparent;
    font-weight: 900; /* 确保字体足够粗以显示效果 */
    text-transform: uppercase; /* 可选：改为大写更显霸气 */
    letter-spacing: 2px;

    /* 2. 核心多层发光阴影 - 塑造立体感和光晕 */
    text-shadow: 
        /* 第一层：最内层的白色高光，提升锐利度 */
        0px 0px 1px rgba(255, 255, 255, 1),
        /* 第二层：暖金色内发光 */
        0px 0px 3px rgba(255, 215, 0, 0.8),
        /* 第三、四层：主要金色光晕，向外扩散 */
        0px 0px 10px rgba(255, 190, 0, 0.8),
        0px 0px 20px rgba(255, 165, 0, 0.7),
        /* 第五、六层：更宽、更柔和的橙色外光晕 */
        0px 0px 40px rgba(255, 140, 0, 0.6),
        0px 0px 70px rgba(255, 69, 0, 0.4);

    /* 3. 添加一点模糊滤镜，让光芒更融合 */
    filter: drop-shadow(0 0 5px rgba(255, 215, 0, 0.3));

    /* 4. 简单的悬停增强交互 */
    transition: all 0.3s ease;
}

/* 鼠标悬停时，光晕轻微放大增强，更有互动感 */
.navbar-brand:hover {
    text-shadow: 
        0px 0px 2px rgba(255, 255, 255, 1),
        0px 0px 5px rgba(255, 215, 0, 0.9),
        0px 0px 15px rgba(255, 190, 0, 0.9),
        0px 0px 30px rgba(255, 165, 0, 0.8),
        0px 0px 50px rgba(255, 140, 0, 0.7),
        0px 0px 90px rgba(255, 69, 0, 0.5);
    filter: drop-shadow(0 0 8px rgba(255, 215, 0, 0.5));
}

/* 暗色模式适配：在深色背景下，使用更高对比度的黄金 */
[data-user-color-scheme="dark"] .navbar-brand {
    background: linear-gradient(90deg, #FFCC00 0%, #FFE55C 25%, #FFF6B3 50%, #FFE55C 75%, #FFCC00 100%);
    text-shadow: 
        0px 0px 2px rgba(255, 255, 200, 1),
        0px 0px 5px rgba(255, 220, 50, 0.9),
        0px 0px 15px rgba(255, 180, 0, 0.9),
        0px 0px 30px rgba(255, 120, 0, 0.8),
        0px 0px 50px rgba(255, 80, 0, 0.7);
}
```

2.你可以打开电脑自带的记事本，将上述css的代码进行粘贴，然后将文件命名为custom.css，记得是所有文件格式，然后将它放入**D:\yyScarlet.github.io\myblogs\source\css文件夹中**  
3接下来要在config.fluid.yml文件中的修改如下  

```undefined
custom_css:
  - /css/custom.css
```

4如同之前步骤一致，不再赘述
