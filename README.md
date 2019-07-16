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

## finish a new feature

```bash
git flow feature finish {feature name/ticket number}