# 将网站部署到Cloudflare Pages的指南

本文档提供了将内蒙古默默文化传媒服务有限公司官网部署到Cloudflare Pages的详细步骤。

## 前提条件

1. 拥有Cloudflare账户
2. 将代码推送到GitHub或GitLab等Git仓库
3. 确保项目能够正确构建

## 部署步骤

### 1. 准备项目

确保您的项目已经准备好进行部署：

- 项目使用Vue 3和Vite构建
- 已经配置了正确的构建命令(`npm run build`)和输出目录(`dist`)
- 项目能在本地成功构建

### 2. 登录Cloudflare Dashboard

1. 访问[Cloudflare Dashboard](https://dash.cloudflare.com/)
2. 使用您的账户登录

### 3. 创建Pages项目

1. 在左侧导航栏中，点击「Pages」
2. 点击「创建项目」按钮
3. 选择「连接到Git」选项

### 4. 连接Git仓库

1. 选择您的Git提供商（GitHub或GitLab）
2. 授权Cloudflare访问您的仓库
3. 从列表中选择`nmgmcn`仓库

### 5. 配置构建设置

在配置页面中，设置以下参数：

- **项目名称**：`nmgmcn`（或您喜欢的名称）
- **生产分支**：`main`（或您的主分支名称）
- **构建命令**：`npm run build`
- **构建输出目录**：`dist`
- **构建系统版本**：选择最新版本

### 6. 环境变量（可选）

如果您的项目需要环境变量，可以在此处添加。对于基本部署，通常不需要额外的环境变量。

### 7. 开始构建

点击「保存并部署」按钮开始构建过程。Cloudflare将自动：

1. 克隆您的仓库
2. 安装依赖项
3. 运行构建命令
4. 部署生成的静态文件

### 8. 查看部署

构建完成后，Cloudflare会提供一个`*.pages.dev`的URL，您可以通过该URL访问您的网站。

### 9. 配置自定义域名（可选）

如果您想使用自己的域名：

1. 在项目页面中，点击「自定义域」
2. 点击「设置自定义域」
3. 输入您的域名（例如：www.nmgmcn.com）
4. 按照Cloudflare提供的说明配置DNS记录

## 持续部署

设置完成后，每当您推送更改到指定的Git分支时，Cloudflare Pages将自动触发新的构建和部署。

## 常见问题解答

### 构建失败怎么办？

检查构建日志以获取详细错误信息。常见问题包括：

- 依赖项安装失败
- 构建命令错误
- 环境变量缺失

### 如何预览部署前的更改？

Cloudflare Pages为每个提交创建预览部署。您可以在项目的「部署」标签页中找到所有预览链接。

### 如何配置自定义构建设置？

如果需要更高级的构建配置，可以在项目根目录创建`_redirects`或`_headers`文件，或者使用`wrangler.toml`文件进行配置。

## 结论

通过以上步骤，您已经成功将内蒙古默默文化传媒服务有限公司官网部署到Cloudflare Pages。该平台提供了免费的静态网站托管，全球CDN分发，以及自动HTTPS加密，确保您的网站快速、安全地提供给全球用户。