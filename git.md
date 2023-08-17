## 记录GIT相关的用法和命令

### 删除仓库中间 Commit

```bash
# 查看 commit 并确定需要删除 commit
git log
# 回退到上一个 commit
git rebase -i "commit_id"
# 进入 Vim 编辑模式，将要删除的 commit 前面的 `pick` 改成 `drop`
# 保存并退出 Vim
```

> [参考：删除commit三种方法](https://blog.csdn.net/qq_34977392/article/details/110817621)

若在其他节点更新仓库，则需要退回至待删除 commit 上一个位置节点，并执行下列命令。

```bash
git reset --hard "commit_id"
git pull
```

### Remote-ssh 免密登录

```bash
ssh-copy-id vscode.com
ssh-copy-id hello@vscode.com
ssh hello@vscode.com
```

`config 文件配置项`

```bash
Host DomainName
  HostName vscode.com
  User hello
  IdentityFile ~/.ssh/id_rsa
```

> [参考：VSCode配置SSH免密登录](https://juejin.cn/post/7023042621295558692)