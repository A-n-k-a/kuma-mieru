# Cloudflare Workers (https://alice39s.github.io/kuma-mieru/zh/deploy/cloudflare/)

<Callout type="warn" title="暂不支持">
  Cloudflare Workers 部署暂未支持，请改用 [Vercel](https://alice39s.github.io/kuma-mieru/zh/deploy/vercel/) 或
  [Netlify](https://alice39s.github.io/kuma-mieru/zh/deploy/netlify/)。相关讨论见
  [#88](https://github.com/Alice39s/kuma-mieru/issues/88#issuecomment-2919619066)。
</Callout>

## 仓库中的 Cloudflare 配置 [#仓库中的-cloudflare-配置]

Web 应用保留了基于 OpenNext（`@opennextjs/cloudflare`）的 Cloudflare 构建配置，文件都在 `apps/web` 目录中：

| 文件                  | 内容                                                                                                                                    |
| --------------------- | --------------------------------------------------------------------------------------------------------------------------------------- |
| `wrangler.jsonc`      | Worker 名称 `uptime-kuma-pages`，启用 `nodejs_compat`，入口 `.open-next/worker.js`，静态资源目录 `.open-next/assets`（绑定名 `ASSETS`） |
| `open-next.config.ts` | OpenNext 的 Cloudflare 配置                                                                                                             |

## 脚本 [#脚本]

在 `apps/web` 目录执行：

| 命令                        | 作用                                                                                     |
| --------------------------- | ---------------------------------------------------------------------------------------- |
| `bun run build:cloudflare`  | 设置 `CF_DEPLOYMENT=true`，运行 `generate` 脚本，再用 `opennextjs-cloudflare build` 构建 |
| `bun run deploy:cloudflare` | 设置 `CF_DEPLOYMENT=true`，用 `opennextjs-cloudflare deploy` 部署                        |

自行尝试时，在 Cloudflare 导入仓库后把根目录设为 `apps/web`，并按[环境变量](https://alice39s.github.io/kuma-mieru/zh/configuration/environment/)配置变量。
