# linux 部分操作

## 基础

	ls,cd,vi,vim


## 文件夹内容寻找

```
$ find / -name '*' | xargs grep -r 'timersub'
```
## 权限

	sudo // 禁止访问时可以尝试加入
	//
	chmod -R  777  /home/mypackage
	//
	chmod  // 修改权限
	-R  // 目标路径下的所有文件
	777 // 是读、写、执行权限...

## 端口绑定问题

[Windows10内置Linux子系统初体验](http://www.jianshu.com/p/bc38ed12da1d)