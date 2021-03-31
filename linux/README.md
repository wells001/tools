# linux 部分操作

## 基础

	ls,cd,vi,vim

## 查看目录内文件夹大小

```
du -h --max-depth=1
```

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

# auto bash
## 自动部署
> 项目中需要 编译后到新仓库部署 手动打标签过慢，过于麻烦

 [自动部署分支](./auto-bash/try-test.sh)
 [自动部署标签](./auto-bash/try-tag.sh)

## 执行结果输出到文件

```
echo "日志内容"  > 文件
git log > index.md
```


## wsl Ubuntu mysql8 修改密码
```
alter user 'root'@'%' identified by '123456'; // 修改root登录密码
ALTER USER 'root'@'%' IDENTIFIED WITH mysql_native_password BY '123456'; // 修改可视化连接密码
```