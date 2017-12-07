# Git-3
### .gitignore
如果在项目中存在一些` untracked 	`文件需要完全忽略，可以在与.git同目录下创建一个` .gitignore `的文件，在文件中说明需要忽略的文件
```
	#.gitignore
	pkg/
	Gemfile.lock
	vendor/
	spec/fixtures/
	.vagrant/
	.bundle/
	coverage/
	.idea/
	*.iml
```
### git mv
> 仓库文件重命名

```
	git mv test1.txt test2.txt
	# 以上命令等效于以下三条命令
	mv test1.txt test2.txt
	git rm test1.txt
	git add test2.txt
	git commit -m "rename"
```
### git log
> 查看提交日志
```
	git log # 提交日志时间由近及远
	git log -2 # 只显示最近两条日志
	git log -p # 显示每次提交改变的地方
	git log -p -2
	git log --stat # 显示额外的统计信息
	git log --pretty=oneline # 每条日志显示为一行
	git log --graph # 以图的形式表示分支
	git log --author=xx # 显示特定用户的提交日志
```
### git diff
```
	git diff HEAD -- readme.txt # 查看工作区和版本库里最新版本的区别
```