# GitHub秘钥配置

> 问题描述：git提交出错，或者仓库关联失败

```shell
git@github.com: Permission denied (publickey).
fatal: Could not read from remote repository.
```

原因：本地公钥没有添加至github

## 解决方法：

```shell
cd ~/.ssh
ls
ssh-keygen -t rsa -C "email@123.com"
cat id_rsa.pub
```

复制id_rsa.pub内容，添加至github

git添加位置 **settings --> ssh and gpg keys --> new ssh key**

