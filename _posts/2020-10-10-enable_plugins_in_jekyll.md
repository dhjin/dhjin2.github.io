---
title: "Trick: Enable Plugin in jekyll"
date: 2020-10-10
permalink: /solutions/2020/10/
---
## Using two branches to make the plugin work on my github blog
How do I enable css-plug-in to operate on my github-pages? **A simplest solution is making two branches.** In my case, I used sass plugins for my blog and it worked well in my localhost. However, the github-pages could not build it when I committed sources to a remote repository. I've got a message from github, It's like below.

![error screenshot](/images/gitpages-error.png)

It's because github-pages doesn't support a custom theme other than native themes.
I found a good solution to this problem by [Rademaker](http://arademaker.github.io/blog/2011/12/01/github-pages-jekyll-plugins,"rademaker").
I think making two branches is more effective way to me. 
- First, make a **work** branch for your customized jekyll blog and clone it to some directory other than your main(or master) directory.
- Make a change at **work** branch
- Commit as **work** branch
```bash
> git add * && git commit -m "blah.." && git push origin work
```
- Build with 'jekyll' command
```bash
> jekyll build
```
- (If you don't have main branch's directory) Prepare main branch's directory and clone
```bash
> cd .. 
> git clone http://yourblog.github.io.git
```
- Remove all files in **main** branch's root. Copy all files in **_site** directory from a **work** branch to **main** branch's root
```bash
> rm -r yourblog.github.io/* && cp -r work.yourblog.github.io/_site/* yourblog.github.io/ && touch yourblog.github.io/.nojekyll
```
- Commit your **main** branch
```bash
> cd yourblog.github.io
> git add * && git commit -m "blah.." && git push origin main
```
- And it will be updated.