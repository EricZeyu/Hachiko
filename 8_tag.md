#Tag

	$git tag -a v1.0

**-a 选项意为“创建一个带注解的标签”**


当你执行 git tag -a 命令时，Git 会打开你的编辑器，让你写一句标签注解，就像你给提交写注解一样。
现在，注意当我们执行 git log --decorate 时，我们可以看到我们的标签了：
***	
	$ git log --oneline --decorate --graph
	*   88afe0e (HEAD, tag: v1.0, master) Merge branch 'change_site'
	|\  
	| * d7e7346 (change_site) changed the site
	* | 14b4dca 新增加一行
	|/  
	* 556f0a0 removed test2.txt
	* 2e082b7 add test2.txt
	* 048598f add test.txt
	* 85fc7e7 test comment from w3cschool.cc

查看所有标签：
***
	$git tag

	$git tag -a <tagname> -m "cc tag"
	
	$git tag -s <tagname> -m "dd tag"


1 新建标签

Git 使用的标签有两种类型：轻量级的（lightweight）和含附注的（annotated）。
轻量级标签就像是个不会变化的分支，实际上它就是个指向特定提交对象的引用。
而含附注标签，实际上是存储在仓库中的一个独立对象，它有自身的校验和信息，包含着标签的名字，电子邮件地址和日期，以及标签说明，标签本身也允许使用 GNU Privacy Guard (GPG) 来签署或验证。
一般我们都建议使用含附注型的标签，以便保留相关信息；
当然，如果只是临时性加注标签，或者不需要旁注额外信息，用轻量级标签也没问题。

2 创建标签
***
	[root@Git git]# git tag v1.0

3 查看已有标签
***
	[root@Git git]# git tag
	v1.0
	[root@Git git]# git tag v1.1
	[root@Git git]# git tag
	v1.0
	v1.1

4 删除标签
***
	[root@Git git]# git tag -d v1.1
	Deleted tag ‘v1.1’ (was 91388f0)
	[root@Git git]# git tag
	v1.0

5 查看此版本所修改的内容
***
	[root@Git git]# git show v1.0
	commit 91388f0883903ac9014e006611944f6688170ef4
	Author: "syaving" <"819044347@qq.com">
	Date: Fri Dec 16 02:32:05 2016 +0800
	commit dir
	diff –git a/readme b/readme
	index 7a3d711..bfecb47 100644
	— a/readme
	+++ b/readme
	@@ -1,2 +1,3 @@
	text
	hello git
	+use commit
	[root@Git git]# git log –oneline
	91388f0 commit dir
	e435fe8 add readme
	2525062 add readme