#Git 安装配置

##[Git简明指南](http://www.runoob.com/manual/git-guide/)

##[git doc](https://git-scm.com/docs)

##[git runoob duc](http://www.runoob.com/manual/github-git-cheat-sheet.pdf)

###Linux平台上安装
- Debian/Ubuntu
***
	$apt-get install libcur14-gnutls-dev libexpat1-dev gettext libz-dev libssl-dev
	$apt-get install git-core
	$git --version

- Centos/RedHat
***
	$yum install curl-devel expat-devel gettext-devel openssl-devel zlib-devl
	$yum -y install git-core
	$git version

###Window平台上安装
在Windows平台上安装Git同样轻松，有个叫做msysGit的项目提供了安装包，可以到GitHub上下载exe安装文件并运行：
安装包下载地址：[msysGit](http://msysgit.github.io/)

完成安装之后，就可以使用命令行的git工具（已经自带了ssh客户端）了，另外还有一个图形界面的Git项目管理工具。
在开始菜单里找到"Git"->"Git Bash"，会弹出Git命令窗口，你可以在该窗口进行Git操作。

###Mac平台上安装
在 Mac 平台上安装 Git 最容易的当属使用图形化的 Git 安装工具，下载地址为：[this](http://sourceforge.net/projects/git-osx-installer/)

###Git配置
Git提供了一个叫做git config的工具，专门用来配置或读取相应的工作环境变量。
该变量存放一下三个不同的地方：
1. /etc/gitconfig：系统中对所有用户都普遍适用的配置。若使用 git config 时用 --system 选项，读写的就是这个文件。
2. ~/.gitconfig 文件：用户目录下的配置文件只适用于该用户。若使用 git config 时用 --global 选项，读写的就是这个文件。
3. 当前项目的 Git 目录中的配置文件（也就是工作目录中的 .git/config 文件）：这里的配置仅仅针对当前项目有效。每一个级别的配置都会覆盖上层的相同配置，所以 .git/config 里的配置会覆盖 /etc/gitconfig 中的同名变量。

在 Windows 系统上，Git 会找寻用户主目录下的 .gitconfig 文件。主目录即 $HOME 变量指定的目录，一般都是 C:\Documents and Settings\$USER。
此外，Git 还会尝试找寻 /etc/gitconfig 文件，只不过看当初 Git 装在什么目录，就以此作为根目录来定位。

###用户信息
配置个人的用户名和电子邮件地址：
***
	$git config --global user.name "Eric"
	$git config --global user.email xxx@edu.cn

如果用了 --global 选项，那么更改的配置文件就是位于你用户主目录下的那个，以后你所有的项目都会默认使用这里配置的用户信息。
如果要在某个特定的项目中使用其他名字或者电邮，只要去掉 --global 选项重新配置即可，新的设定保存在当前项目的 .git/config 文件里。

###文本编辑器
设置Git默认使用的文本编辑器, 一般可能会是 Vi 或者 Vim。如果你有其他偏好，比如 Emacs 的话，可以重新设置：:
***
	$git config --global core.editor emacs

###差异分析工具
还有一个比较常用的是，在解决合并冲突时使用哪种差异分析工具。比如要改用 vimdiff 的话：
***
	$git config --global merge.tool vimdiff
Git 可以理解 kdiff3，tkdiff，meld，xxdiff，emerge，vimdiff，gvimdiff，ecmerge，和 opendiff 等合并工具的输出信息。
当然，你也可以指定使用自己开发的工具，具体怎么做可以参阅第七章。

###查看配置信息
要检查已有的配置信息，可以使用：
***
	$git config --list
	$git config user.name
