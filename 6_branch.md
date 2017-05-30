#Git分支管理

- 创建分支命令：
***
	$git branch (branchname)

- 切换分支命令：
***
	$git checkout (branchname)

- 合并分支命令：
***
	$git merge

###分支管理
- 列出分支基本命令：
***
	$git branch
- 没有参数时，git branch会列出你在本地的分支：
***
	$git branch
	* master

- 切换分支
***
	$git checkout (branch)

- 创建并立即切换到该分支下
***
	$git checkout -b (branch)

- 删除分支
***
	$git branch -d (branch)

- 分支合并(一旦分支有了独立内容，最终还是希望合并回主分支)
***
	$git merge

	$git branch
	* master
	  newtest
	
	$git merge newtest
	Updating 2e082b7..556f0a0
	...

- 合并冲突
***
	$ git merge change_site
	Auto-merging test.txt
	CONFLICT (content): Merge conflict in test.txt
	Automatic merge failed; fix conflicts and then commit the result.
	$ cat test.txt 
	<<<<<<< HEAD
	runoob.com
	新增加一行
	=======
	www.runoob.com
	>>>>>>> change_site

**当合并分支出现冲突时，需要我们手动修改解决冲突**

- 可使用git add告诉Git文件冲突已经解决
***
	$ git status -s
	UU test.txt
	$ git add test.txt 
	$ git status -s
	M  test.txt
	$ git commit
	[master 88afe0e] Merge branch 'change_site'