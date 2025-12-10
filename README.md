# Kiro Token Manager

Kiro Token Manager 的发布仓库。

## 下载

前往 [Releases](../../releases) 页面下载最新版本。

### 支持平台

| 平台 | 架构 | 文件 |
|------|------|------|
| Windows | x64 | `KiroTokenManager_版本_x64.msi` / `KiroTokenManager_版本_x64_setup.exe` |
| macOS | Apple Silicon | `KiroTokenManager_版本_aarch64.dmg` |
| macOS | Intel | `KiroTokenManager_版本_x64.dmg` |

## 配置说明

此仓库使用 GitHub Actions 从私有仓库构建发布版本。

### 设置步骤

1. 创建 Personal Access Token (PAT)
   - GitHub Settings → Developer settings → Personal access tokens → Tokens (classic)
   - Generate new token → 勾选 `repo` 权限
   - 复制生成的 token

2. 添加 Secret
   - 本仓库 Settings → Secrets and variables → Actions
   - New repository secret
   - Name: `PRIVATE_REPO_PAT`
   - Value: 粘贴上一步的 token

3. 修改 workflow 文件
   - 编辑 `.github/workflows/build.yml` 和 `release.yml`
   - 将 `repository: anthropics/KTM` 替换为你的私有仓库地址

### 触发构建

- 手动触发：Actions → 选择 workflow → Run workflow
- 自动触发：推送 `v*` 格式的 tag
