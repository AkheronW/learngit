# Git-1
### ` git config `
git的配置文件有三个：
` /etc/gitconfig ` --System Level(` system `)
` ~/.gitconfig ` --User Level(` global `)
` .git/config ` --Repository Level,存放在本地仓库(` local `)
** 优先级： Repository > User > System **
> Git 安装完毕后，在使用之前需要先配置用户名(user.name)以及邮箱(user.email)，因为Git需要这些信息标识每个人每次的任务提交以便于跟踪是谁提交了什么。

	git config --global user.name "Name"
	git config --global user.email "Name@name.com"

` git config [--local|--global|--system] --list `:查看当前生效的配置信息

	git config user.name "Name" #省略global参数，默认Repository级别
***修改配置***

	git config [--local|--global|--system] --edit
***增加配置*** 

	git config [--local|--global|--system] -–add section.key value
***获取某一个配置***

	git config [--local|--global|--system] --get section.key

***注***：*我在安装git后，配置了用户名和邮箱后，在执行` git config --system --list `后，会出现` unable to read config file '/etc/gitconfig': No such file or directory `错误，原因在于没有进行` System Level `级别的配置*