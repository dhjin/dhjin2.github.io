---
title: "Trick: Enable Plugin in jekyll"
date: 2020-10-10
---
## It's a trick
How to enable plug in works?
- Let your customized jekyll blog have a work branch
- Make a change at your blog
- Commit as work branch
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
- Remove all files in main branch's root. Copy all files in work branch's **_site** directory to main branch's root
```bash
> rm -r yourblog.github.io/* && cp -r work.yourblog.github.io/_site/* yourblog.github.io/ && touch yourblog.github.io/.nojekyll
```
- Commit your main branch
```bash
> cd yourblog.github.io
> git add * && git commit -m "blah.." && git push origin main
```
