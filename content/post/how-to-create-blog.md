+++
date = "2016-01-31T12:20:43-05:00"
draft = true
title = "how to create blog"

+++


[How To Install and Configure VNC Remote Access for the GNOME Desktop on CentOS 7](https://www.digitalocean.com/community/tutorials/how-to-install-and-configure-vnc-remote-access-for-the-gnome-desktop-on-centos-7?comment=35734). You can adjust the color by refer to [SOLVED: Getting blurred background while accessing via VNC viewer](http://www.linuxquestions.org/questions/linux-newbie-8/getting-blurred-background-while-accessing-via-vnc-viewer-4175555060/#post5437254).


```
[ryoeng@rstudio-scibrokes ryoeng]$ git submodule add https://github.com/syui/hugo-theme-air.git themes/air
```

  Due to the author put the backgound image as comment, therefore you are required to edit the file `Home/englianhu/ryoeng/themes/air/status/css` inside ®Studio. You can also changed to your desired image after save inside image folder.

  The files inside **public** folder will be knited and post as html format file. 

  Well, you need to connect your subfolder inside **public** folder (You might remove the folder **public** if any) to the default github page website.

```
[ryoeng@rstudio-scibrokes ryoeng]$ grm -rf public
[ryoeng@rstudio-scibrokes ryoeng]$ git submodule add https://github.com/englianhu/englianhu.github.io.git public
```


  * [使用hugo搭建个人博客站点](http://blog.coderzh.com/2015/08/29/hugo/)
  * [利用 Hugo & GitHub 搭建个人博客静态网站](http://blog.bpcoder.com/2015/12/hugo-create-blog/)
  * [AIR theme for hugo](https://github.com/syui/hugo-theme-air)


