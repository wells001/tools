# git

## git 普通操作

````
git add .
git commit -m [message]
git push <-f> // 强推
````



## git 分支

````
git branch
git branch -a

git branch -r

git checkout [分支名]  // 分支名尽量不要包含 特殊符号 例如：& 会导致意外bug
````

## git 拉取代码
```
git pull 拉取当前分支
git pull origin [远程分支] 拉取特定远程分支到当前本地分支
git pull origin [远程分支]:[本地分支] 拉取特定远程分支到特定本地分支
```

## git 合并代码

````
git merge branch // 合并某个分支到当前分支
git merge --no-ff branch // 合并某个分支到当前分支，保留原分支记录
````


## git 重置

````
git reset HEAD <file>
git reset --hard [commitnum] // 强制回退到commitnum信息所在地址  //注意，此处push会报错，需要 git push -f
````


## git 标签

```
git tag // 打标签
git tag -a [version] -m [message] // 打带有信息的标签
git push origin [version] // 上传到远程仓库
```


## git更换https方 式账号

```
git credential-manager remove [--path <installion_path>] [--passive] [--force] 停止使用管理工具
```


## git 更换仓库地址

```
git remote set-url origin [url]
```


## git ignore 忽略不生效问题

```
git rm -r --cached .
git add .
git commit -m 'update .gitignore'
```

