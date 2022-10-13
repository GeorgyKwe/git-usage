# git usage

Installation and configuration of git in ubuntu and code pulling and uploading

## Git 安装

```bash
sudo apt-get install git
```

## 设置用户和邮箱

```bash
sudo git config --global user.name "GeorgyKwe"
sudo git config --global user.email "zkzhaoo@qq.com"
```

## 设置 SSH Key

在 Ubuntu 终端运行如下命令，可生成 SSH Key，若已有 Key，则无需再次生成

```bash
ssh-keygen -t rsa      #该命令敲完后，一路回车即可得到如下信息
  Generating public/private rsa key pair.
  Enter file in which to save the key (/home/user/.ssh/id_rsa):
  Created directory '/home/user/.ssh'.
```

### 查看密钥

生成公钥文件位置 ~/.ssh/id_rsa.pub

```bash
cat  ~/.ssh/id_rsa.pub    #查看生成密钥
```

### 查看是否配置成功

```bash
sudo apt-get install xclip
xclip -sel clip < ~/.ssh/id_rsa.pub
ssh -T git@github.com    
# 测试ssh key是否成功，若出现 "You’ve successfully authenticated, but GitHub does not provide shell access" 表示已成功连上 Github
```

## 设置 Github

打开 [Github](https://github.com/) 并成功登陆后，点击自己的账户名->Settings->New SSH Key，将刚刚复制的 pubkey 内容粘贴到下图位置中，然后点击 “ADD SSH KEY” 保存即可

## Git 使用

Github 和 Gerrit 上 Git 工具使用方法相同 

### Pull

拉取下来后为主分支，可在本地新新建工作分支

```bash
git clone git@github.com:GeorgyKwe/git-usage.git
```

关联远程分支

```bash
git branch --set-upstream-to=origin/main
```

### Push

```bash
git status
git log
git add 文件名
git commit -m "修改内容"
git push origin main
```
