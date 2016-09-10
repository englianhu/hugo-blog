# RYO, Lian Hu ENG

This is my **new** blog : [englianhu.github.io](https://englianhu.github.io)

# 1. HUGO Blog

  This is my first post about how do I build this hugo blog. I used to try to build a Hugo blog during January 2016 via [DigitalOcean.com](https://m.do.co/c/aabb124120d0) (CentOS 7) but there has some unexpected issues:
  
  - Unable access into console.
  - Mouse unable control the cursor in the virtual operating system.
  - Internet line always interrupted.
  - The theme [hugo-theme-air](https://github.com/syui/hugo-theme-air) is not complete and not workable.

  Today I am trying to continue build my hugo blog in Windows 10 as I occassionally saw the hugo-theme-air has maintaned and updated. You can read the reference to know about what is HUGO.
  
# 2. Build Hugo Blog in Windows 10

## 2.1 Create 2 Github Repo

### 2.1.1 Create a Repo for Store All Files

  Firstly, you need to create a repo (GitHub Pages is a blog service which provides by GitHub) at [GitHub](https://github.com). I just simply created mine as [hugo-blog](https://github.com/englianhu/hugo-blog). You are feel free to refer to [GitHub Pages](https://pages.github.com/) for further information.

  After that, I've just simply download as a ｮStudio project via [ｮStudio](http://www.rstudio.com) IDE. You are feel free to read [Setup ｮStudio Server on Digital Ocean --- CentOS 7](https://github.com/scibrokes/setup-rstudio-server) if you are using centOS 7 on DigitalOcean.com. You might choose only command prompt will be able to create yours easily.

  Here is my path for the Hugo blog which I just simply copy the <https://github.com/englianhu/englianhu.github.io.git> and create a new project in ｮStudio.
  
  It will be `> C:\Users\scibr\Documents\GitHub\englianhu\hugo-blog`.

### 2.2.2 Create a Repo for Only Blog Content

  Secondly, create another repo which is [englianhu.github.io](https://github.com/englianhu/englianhu.github.io) (or your own url if you have your own paid domain name.).
  
  The first **hugo-blog** is a repo to save all relevant files include whole struture but **englianhu.github.io** is the GitHub blog which only contain the files inside folder `public` in hugo website folder `hugo-blog`.

  Here I try to eloberates the use and different between these:
  
  - <https://github.com/englianhu/hugo-blog> is a GitHub repo which can store all your blog relevant files which contain whole struture of the website.
  - <https://github.com/englianhu/hugo-blog.git> is a GitHub git file which is able to connect (pull and push files) your files to the GitHub server and repo **hugo-blog**.
  - `C:\Users\scibr\Documents\GitHub\englianhu\hugo-blog\hugo-blog.Rproj` is a ｮStudio file which store a project for repo **hugo-blog**. I use ｮStudio since it is a user friendly IDE for markdown files management/handling.
  - <https://github.com/englianhu/englianhu.github.io> is repo for hugo blog since the default url provides by GitHub is `https://<yourname>.github.io>`.

## 2.2 Download Hugo Apps

  Secondly, you need to go to [spf13/hugo](https://github.com/spf13/hugo/releases) to download the latest (currently version 1.6 is the most updated version) version. Click [here](https://github.com/spf13/hugo/releases/download/v0.16/hugo_0.16_windows-64bit.zip) to download the HUGO server Windows 64 bit.
  
  Due to the Hugo.exe is a standalone app, therefore I just simply locate it at `> C:\Users\scibr\Documents\GitHub\englianhu` and then move the folder `hugo-blog` to path `C:\Users\scibr\Documents\GitHub\` to save the github and ｮStudio \*.Rproj relevant files and avoid the error duplicate folder name `hugo-blog`.
  
  Now, you can create a new website by run below codes :
  
```
> C:\Users\scibr\Documents\GitHub\englianhu>hugo new site hugo-blog
```

  After you created the folder `hugo-blog`. Please remember move the prvious files inside path `C:\Users\scibr\Documents\GitHub\hugo-blog` into `C:\Users\scibr\Documents\GitHub\englianhu\hugo-blog` and delete the folder `C:\Users\scibr\Documents\GitHub\hugo-blog`. The purpose to do so just moved the github and \*.Rproj relevant files to our hugo new site folder in order to handle in ｮStudio and also pull from or push to GitHub repo.

## 2.3 Install Hugo Theme

  After create a structure of the website, move the hugo.exe into folder `hugo-blog` manually and then run below codes to download the theme:

```
> C:\Users\scibr\Documents\GitHub\englianhu>cd hugo-blog
> C:\Users\scibr\Documents\GitHub\englianhu\hugo-blog>git init
> C:\Users\scibr\Documents\GitHub\englianhu\hugo-blog>echo .DS_Store >> .gitignore
> C:\Users\scibr\Documents\GitHub\englianhu\hugo-blog>git submodule add -f https://github.com/syui/hugo-theme-air.git themes/air
```

  The *利用 Hugo & GitHub 搭建个人博客静态网站* in reference use `git submodule add git@github.com:Zenithar/hugo-theme-crisp.git themes/crisp` but there will require passphrase and SSH while I directly using url which will be more easier.
  
  Remember the Hugo.exe is an standalone app and I move it to `C:\Users\scibr\Documents\GitHub\englianhu\englianhu.github.io\themes>` in order to run the app as below codes in [2.4 Browse via LocalHost Before Publish].

## 2.4 Configuration

  We need to modify the configuration file via file name `config.toml` inside folder theme `air` as well as the `config.toml` inside folder `englianhu.github.io`.

```
baseurl = "http://englianhu.github.io"
languageCode = "en"
title = "RYO, ENG Lian Hu"
paginate = 8
theme = "air"
[params]
    description = "白戸則道：実に面白いですね！"
    email = "englianhu@gmail.com"
[permalinks]
    post = "/:year/:title/"
    addendum = "/addendum/:year/:title/"
```

## 2.5 Browse via LocalHost Before Publish

  We can try to browse the demo version and modify it prior to publish.

```
> C:\Users\scibr\Documents\GitHub\englianhu\hugo-blog>hugo server -w
> C:\Users\scibr\Documents\GitHub\englianhu\hugo-blog>git rm -rf public
> C:\Users\scibr\Documents\GitHub\englianhu\hugo-blog>git submodule add https://github.com/englianhu/englianhu.github.io.git public
```

<s>
```
> C:\Users\scibr\Documents\GitHub\englianhu\hugo\themes>hugo server --theme=hugo-theme-air --buildDrafts --watch
```
</s>

  Well, now we try to browse the [http://127.0.0.1:1313/](http://127.0.0.1:1313/) localhost.
  
![*figure 2.3.1 : Hugo blog layout*](content/figure/20160910_121813.gif)

## 2.6 Post to Hugo Blog

  When you modified your post content and decide to post on your blog. Now you just run below codes and a folder `public` will be created.

```
> C:\Users\scibr\Documents\GitHub\englianhu\englianhu.github.io>hugo
> C:\Users\scibr\Documents\GitHub\englianhu\englianhu.github.io>cd public
> C:\Users\scibr\Documents\GitHub\englianhu\englianhu.github.io>git add -A && git commit -m "first post"
> C:\Users\scibr\Documents\GitHub\englianhu\englianhu.github.io>git push origin master
> C:\Users\scibr\Documents\GitHub\englianhu\englianhu.github.io>cd ..
> C:\Users\scibr\Documents\GitHub\englianhu\englianhu.github.io>git add -A && git commit -m "init hugo coder"
> C:\Users\scibr\Documents\GitHub\englianhu\englianhu.github.io>git push origin master
```

  The files will upload to github repo and your blog and 1st post has been successful. Please be mind that [**Hugo**](https://gohugo.io) blogs only publish the index file as html web page inside folder `Public`. **Therefore the index.html right inside the folder `Public` will be the home page of the blog.**

# 3. Conclusion

  It is very simple to build a hugo blog. You might try to build yours. *Benoît Benedetti (2015)* in [4. Reference] is a tutorial about create a HUGO theme which is quite interesting and might read through some other days to create mine.

# 4. Reference

1. [使用hugo搭建个人博客站点](http://blog.coderzh.com/2015/08/29/hugo/)
2. [利用 Hugo & GitHub 搭建个人博客静态网站](http://blog.bpcoder.com/2015/12/hugo-create-blog/)
3. [**Building a theme with Hugo** - Tutorial to build a Hugo Theme *by Benoît Benedetti (2015)*](http://www.humboldtux.net/sbcb-demo/post/post-01/)
