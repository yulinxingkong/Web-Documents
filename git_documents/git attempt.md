### git 使用
#### 分支(branch)
- 拿过来项目创建自己分支<br>
```git clone https 地址 或 ssh 地址 开发最好用ssh 一劳永逸```
- 一般项目leader 会建好dev  branch 这样我们自己直接创建并追踪就可以<br>
```git  checkout -b dev origin/dev```
- 创建并切换到自己开发使用的branch<br>
```git checkout -b mybranch```
- 把mybranch push 到 remote 服务器<br>
```git push  origin mybranch```
- 把mybranch 设置远程追踪, 下班前提交代码,做备份<br>
```git branch --set-upstream-to=origin/mybranch```
- 删除branch <br>
```git branch -d mybranch```

#### 合并(merge)
- 切换到dev 分支<br>
```git checkout dev```
- 拉取最新代码<br>
```git pull```
- 将mybranch 内容合并到dev<br>
```git merge mybranch```
- 将合并后的dev 分支推push 上去 供别人merge 代码<br>
```git push origin dev```
#### **_合并代码出现冲突(conflict)_**
- 商议解决,后 <br>
```git add .```<br>
```git commit -m '解决冲突注释''```<br>
```git merge mybranch```

#### bug分支
> 正在写代码,有bug了,手头工作没完成不够提交, 怎么办?

- 保存当前工作区<br>
```git stash  ```

- 创建并切换到 bug分支<br>
```git checkout -b bug001```

    ```git merge master  # 合并master分支到bug 分支, 在这个分支上修改代码```
> 一般master 分支上放线上稳定运行的版本
- 修改完,合并分支到master 分支<br>
`git checkout master  `<br>
` git merge --no-ff -m '合并注释' bug001 `<br>
- 删除bug 分支<br>
`git branch -d bug`

- 回到stash 时的工作区
`git stash pop`

#### 撤销
- 从 服务器到本地仓库<br>
 `git pull `
- 从 本地仓库到暂存区<br>
`git reset`
- 从 暂存区到工作区<br>
` git checkout`
- 从 本地仓库到工作区<br>
`git reset --hard`

