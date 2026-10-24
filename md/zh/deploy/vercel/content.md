# Vercel (https://alice39s.github.io/kuma-mieru/zh/deploy/vercel/)

Vercel 是推荐的部署方式。整个流程在网页上完成，不需要自己的服务器。

<Steps>
<Step>

### Fork 仓库 [#fork-仓库]

1. 打开本仓库的 [Fork 页面](https://github.com/Alice39s/kuma-mieru/fork)。
2. 点击 `Create fork`。

<Callout type="info">
  请保持 Fork 的仓库为公开仓库，否则后续可能无法快速同步上游的更新。所有配置都通过环境变量设置，Fork
  的仓库中不会包含你的任何配置信息。
</Callout>

</Step>
<Step>

### 导入到 Vercel [#导入到-vercel]

打开 [vercel.com/new](https://vercel.com/new)，找到刚才 Fork 的仓库，点击 `Import`。

![导入仓库](</kuma-mieru/_next/static/media/vercel-import.3ti7u11pp7bhz.png>)

</Step>
<Step>

### 设置根目录 [#设置根目录]

在项目配置页把 `Root Directory` 设为 `apps/web`。Web 应用和它的 `vercel.json` 都在这个目录中。

</Step>
<Step>

### 添加环境变量 [#添加环境变量]

展开 `Environment Variables`，添加 `UPTIME_KUMA_URLS`，值为 Uptime Kuma 状态页的完整 URL。多个状态页用 `|` 分隔。

![添加环境变量](</kuma-mieru/_next/static/media/vercel-deploy.3qjqt-qnk-c4f.png>)

<Callout type="warn">
  必须设置 `UPTIME_KUMA_URLS`（推荐）或旧版的 `UPTIME_KUMA_BASE_URL` 加 `PAGE_ID`。两者都没有设置，或者 URL 中没有 `/status/<页面 ID>` 时，`generate` 脚本报错退出，Vercel 构建失败。其他变量见[环境变量](https://alice39s.github.io/kuma-mieru/zh/configuration/environment/)。
</Callout>

</Step>
<Step>

### 部署 [#部署]

点击 `Deploy`。

</Step>
</Steps>

## 修改环境变量 [#修改环境变量]

Vercel 在构建时运行 `generate` 脚本，把环境变量和状态页信息写入生成的配置。在 Vercel 修改环境变量后，重新部署项目才会生效。

## 同步上游更新 [#同步上游更新]

1. 打开你 Fork 的 GitHub 仓库，点击 `Sync fork`。
2. 点击 `Update branch`，同步上游仓库的最新代码。

## 仓库中的 Vercel 配置 [#仓库中的-vercel-配置]

`apps/web/vercel.json` 为首页 `/` 设置以下响应头：

| 响应头                   | 值                                                |
| ------------------------ | ------------------------------------------------- |
| `Cache-Control`          | `public, max-age=300, stale-while-revalidate=300` |
| `X-XSS-Protection`       | `1; mode=block`                                   |
| `X-Content-Type-Options` | `nosniff`                                         |
