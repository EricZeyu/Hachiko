#Git创建仓库

##git init
Git使用`git init`命令来初始化一个Git仓库，Git的很多命令都需要在Git的仓库中运行，所以`git init`是使用Git的第一个命令。
在执行完成`git init`命令后，Git仓库会生成一个.git目录，该目录包含了资源的所有元数据，其他的项目目录保持不变（不像SVN会在每个目录生成.svn目录，Git只在仓库的根目录生成.git目录）。

####使用方法
***
	$git init
	$git init newrepo

###git clone
***
	$git clone <repo>
	$git clone <repo> <directory>
	$git clone git:://github.com/school/my.git
	$git clone git:://github.com/school/my.git newMyRepo