# 网站

这是一个使用Hexo构建的静态网站。

## 部署说明

网站会自动部署到 GitHub Pages。当代码推送到 `main` 分支时，GitHub Actions 会自动构建并部署网站到 `gh-pages` 分支。

### 手动部署

你也可以使用以下命令手动部署网站：

```bash
npm run deploy
```

这会将网站部署到配置中指定的仓库 `git@github.com:gzl001116/wangzhan.git` 的 `gh-pages` 分支。

### 设置自动部署

为了使 GitHub Actions 能够自动部署，你需要：

1. 生成一个 SSH 密钥对：
   ```bash
   ssh-keygen -t rsa -b 4096 -C "$(git config user.email)" -f gh-pages -N ""
   ```

2. 在 GitHub 仓库设置中：
   - 添加公钥（`gh-pages.pub` 的内容）到 "Deploy Keys" 并允许写入权限
   - 添加私钥（`gh-pages` 的内容）到 "Secrets" 并命名为 `DEPLOY_KEY`

3. 确保 GitHub Pages 在仓库设置中配置为使用 `gh-pages` 分支