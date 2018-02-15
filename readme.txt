git config --global user.name "name"
git config --global user.email "email@example.com"

git init
git add <filename>
git commit -m "comment"
git log
git reset --hard HEAD~<num>\<ID>
git reflog
git status

git diff		    			   工作区和缓存区的比较
git diff --cached	    			   缓存区和分支的比较

git remote add origin <address>  		   关联远程库，名字叫origin
git remote					   查看远程库信息
git remote -v					   查看远程库更详细信息
git push <remote_name> <branch_name>		   将指定本地分支推送到远程库上
git push -u origin master	 		   将当前分支推送到远程库origin的master分支(即使master不存在也可以，会新建这个分支)
git pull					   将远程库的最新提交抓下来
注意：git pull = git fetch + git merge，git fetch更安全一些
git clone <address>

git branch
git branch <branch_name>
git checkout <branch_name>
git checkout -b <branch_name>			   创建并切换到指定分支
git branch -d <branch_name>  			   删除指定分支
git branch -D <branch_name>			   强制删除指定分支
git branch --set-upstream-to origin/branch1 local1 关联origin库的branch1与本地local1分支(前提是远程库有branch1分支)

git merge <branch_name>      			   提交指定分支成果到当前分支
git merge --no-ff -m "comment" <branch_name>       禁用Fast forward方式合并分支

git log --graph		     			   查看分支合并图
git log --graph --pretty=oneline --abbrev-commit   查看简化合并图

git stash  					   储存现场
git stash list					   查看保存的现场存档列表
git stash apply <stash_name>			   恢复现场，但存档还在
git stash drop <stash_name>			   删除存档
git stash pop <stash_name>			   恢复现场，同时删除存档

git tag <tag_name>				   打一个新的标签(在最新提交的commit上)
git tag <tag_name> <commit_id>			   给指定的commit上打标签
git tag						   查看所有的标签
git tag -a <tag_name> -m "comment" <commit_id>     指定标签并指定说明文字
git tag -s <tag_name> -m "comment" <commit_id>	   通过私钥签名一个标签，采用PGP签名，若没有GnuPG则报错
git show <tag_name>				   查看标签信息

多人协作的工作模式通常是这样：
1.首先，可以试图用git push origin branch-name推送自己的修改；
2.如果推送失败，则因为远程分支比你的本地更新，需要先用git pull试图合并；
3.如果合并有冲突，则解决冲突，并在本地提交；
4.没有冲突或者解决掉冲突后，再用git push origin branch-name推送就能成功！

注意：如果git pull提示“no tracking information”，则说明本地分支和远程分支的链接关系没有创建，用命令git branch --set-upstream branch-name origin/branch-name。
