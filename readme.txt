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
git push -u origin master	 		   将当前分支master推送到远程库origin
git clone <address>

git branch
git branch <branch_name>
git checkout <branch_name>
git checkout -b <branch_name>
git branch -d <branch_name>  			   删除指定分支
git branch -D <branch_name>			   强制删除指定分支

git merge <branch_name>      			   提交指定分支成果到当前分支
git merge --no-ff -m "comment" <branch_name>       禁用Fast forward方式合并分支

git log --graph		     			   查看分支合并图
git log --graph --pretty=oneline --abbrev-commit   查看简化合并图

git stash  					   储存现场
git stash list					   查看保存的现场存档列表
git stash apply <stash_name>			   恢复现场，但存档还在
git stash drop <stash_name>			   删除存档
git stash pop <stash_name>			   恢复现场，同时删除存档
