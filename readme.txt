git config --global user.name "name"
git config --global user.email "email@example.com"

git init
git add <filename>
git commit -m "comment"
git log
git reset --hard HEAD~<num>\<ID>
git reflog
git status

git diff		    工作区和缓存区的比较
git diff --cached	    缓存区和分支的比较

git remote add origin <address>  关联远程库，名字叫origin
git push -u origin master	 将当前分支master推送到远程库origin
git clone <address>

git branch
git branch <branch_name>
git checkout <branch_name>
git checkout -b <branch_name>
git merge <branch_name>      提交指定分支成果到当前分支
git branch -d <branch_name>  删除指定分支

########################test#############################
Creating a new branch is quick AND simple.


