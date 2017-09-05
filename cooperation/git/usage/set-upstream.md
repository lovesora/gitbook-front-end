# Git设置upstream
* 将当前分支的upstream为origin远程仓库的dev分支

    `$ git branch --set-upstream-to=origin/dev`

    or

    `git branch -u origin/dev`

* 在推送的同时，同时设置upstream

    `$ git push -u origin master`
