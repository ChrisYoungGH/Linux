初始化用户
```bash
git config --global user.name "name"
git config --global user.email "email"
```

添加ssh key
```bash
ssh-keygen -t rsa
```

或者：

```bash
ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
```

复制 ~/.ssh/id_rsa.pub to github 到 SSH keys
```bash
clip < ~/.ssh/id_rsa.pub
```

```bash
git init
git clone git@github.com:user/repository.git
```

文件操作
```bash
git add file
git rm file
git commit -m "add file"
git push -u origin master / git push origin master (第一次需要-u参数)
```
