## Install git flow tool

```bash
brew install git-flow-avh
```

## Init git flow

```bash
git flow init
```

-   自动建立本地`develop`分支，并切换到`develop`分支

## Start a new feature

```bash
git flow feature start {feature name/ticket number}
```

-   基于`develop`分支新建了`featureName`分支，并且切换到该分支下

## Publish a new feature

**适合多人开发，code review，PR**

```
git add .
git commit -m 'msg'
git flow feature publish {feature}
```

-   讲本地`feature`分支 push 到远程`feature`分支

## Finish a new feature

**适合单人开发**

```bash
git add .
git commit -m 'commit msg'
git flow feature finish {feature name/ticket number}
```

-   合并`feature`分支到`develop`
-   删除本地`feature`分支
-   切换到`develop`分支
-   **如何需要`code review`后再进行 merge，建议使用`publish`**

## Start a new release

```bash
git flow release start {release} [base]
```

-   基于`develop`分支新建本地`release`分支，并切换到该分支
-   可以提供一个 base，`develop`分支下某个版本的 hash 值

## Publish a new release

```bash
git flow release publish {release}
```

-   将本地`release`分支 push 到远程`release`分支

## Finish a new release

```bash
git checkout master
git pull   // Make sure your local master is up to date
git flow release finish {release}
git push origin develop
git checkout master
git rebase develop
git push origin master
git push --tags
```

-   拉取 master 分支，确保本地 master 分支与远程 master 分支同步
-   将本地`release`分支合并到本地`master`分支上
-   为`release`分支打`tag`
-   切换到`develop`分支
-   将本地`tag`版本合并到本地`develop`分支上
-   删除本地`release`分支
-   同步远程`master`分支
-   同步远程`develop`分支
-   将`tag`推送至远程仓库

## Start a new hotfix

```bash
git flow hotfix start {version} [base version]
...edit code
git add .
git commit -m 'msg'
```

-   新建本地`release`分支，并切换到该分支

## Finish a new hotfix

**其步骤与`git flow release finish {release}`一致**

```bash
git checkout master
git pull   // Make sure your local master is up to date
git flow hotfix finish {version}
git push origin develop
git checkout master
git rebase develop
git push origin master
git push --tags
```

-   拉取 master 分支，确保本地 master 分支与远程 master 分支同步
-   将本地`hotfix`分支合并到本地`master`分支上
-   为`hotfix`分支打`tag`
-   切换到`develop`分支
-   将本地`tag`版本合并到本地`develop`分支上
-   删除本地`hotfix`分支
-   同步远程`master`分支
-   同步远程`develop`分支
-   将`tag`推送至远程仓库

_Create By Allen_
