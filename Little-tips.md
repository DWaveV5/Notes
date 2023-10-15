# 一些有用的小点

## 关于git

### 初次创建本地项目，提交到git

已经有项目上传

```bash
git init
git add README.md
git commit -m "first commit"
---上面看情况而定----
git remote add origin https地址
git branch -M main （-m强行改分支名子）
git push -u origin main （指定推送到远端）
```

### 提交到上一次的提交记录

```bash
git commit -a --amend --no-edit
```

## nvm版本操作

```bash
nvm list
//指定默认版本
nvm alias default v16.15.1
```

