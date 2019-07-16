## install git flow tool

```bash
brew install git-flow-avh
```

## init git flow

```bash
git flow init
```

- 自动建立本地`develop`分支，并切换到`develop`分支

## start a new feature

```bash
git flow feature start {feature name/ticket number}
```

- 基于`develop`分支新建了`featureName`分支，并且切换到该分支下

## publish a new feature
**多人开发，code review，PR**

```
git add .
git commit -m 'msg'
git flow feature publish {feature}
```

- 讲本地`feature`分支push到远程`feature`分支

## finish a new feature
**适合单人开发**

```bash
git add .
git commit -m 'commit msg'
git flow feature finish {feature name/ticket number}
```

- 合并`feature`分支到`develop`
- 删除本地`feature`分支
- 切换到`develop`分支
- **如何需要`code review`后再进行merge，建议使用`publish`**
