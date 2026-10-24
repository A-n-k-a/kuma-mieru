# 概览 (https://alice39s.github.io/kuma-mieru/zh/)

Kuma Mieru 是一个第三方 Uptime Kuma 监控仪表盘，基于 Next.js 16、TypeScript 和 Recharts 构建。它读取 Uptime Kuma 公开状态页的数据，用交互式图表展示每个监控项的延迟和状态。Uptime Kuma 内建的公开状态页没有延迟图表，展示也不够直观，Kuma Mieru 补上了这两点。

<Callout type="warn" title="把 Uptime Kuma 的显示时区设为 UTC+0">
  v1.1.4 及以后的版本重写了时间处理逻辑。请在 Uptime Kuma 后台设置中把 `Display
  Timezone`（显示时区）改为任意 UTC+0 时区。原因见[常见问题](https://alice39s.github.io/kuma-mieru/zh/guides/faq/)。
</Callout>

## 功能 [#功能]

- 状态实时更新，页面自动刷新。
- 界面基于 HeroUI 组件，适配不同尺寸的屏幕。
- 用 Recharts 绘制交互式图表，可以查看每个节点的延迟和状态。
- 提供暗色、亮色和跟随系统三种主题。
- 显示 Uptime Kuma 状态页上的事件公告和状态更新。
- 一个 Kuma Mieru 可以展示多个状态页，这些状态页可以来自不同的 Uptime Kuma 实例。

## 截图 [#截图]

<Tabs items={['浅色主题', '暗色主题']}>
<Tab value="浅色主题">

![浅色主题](</kuma-mieru/_next/static/media/v1.2.1-light-zh.1jgx5w46pb28h.png>)

</Tab>
<Tab value="暗色主题">

![暗色主题](</kuma-mieru/_next/static/media/v1.2.1-dark-zh.2r6r0mcokrjt3.png>)

</Tab>
</Tabs>

## 技术栈 [#技术栈]

| 用途       | 技术                    |
| ---------- | ----------------------- |
| 框架       | Next.js 16、React 19    |
| 语言       | TypeScript              |
| 图表       | Recharts                |
| 组件与样式 | HeroUI、Tailwind CSS v4 |
| 包管理器   | Bun                     |

## 下一步 [#下一步]

<Cards>
  <Card
    title="选择部署方式"
    description="比较 Vercel、Netlify、EdgeOne Pages、Docker 和源码运行。"
    href="https://alice39s.github.io/kuma-mieru/zh/deploy/"
    icon={<Rocket />}
  />
  <Card
    title="连接 Uptime Kuma"
    description="创建状态页，设置显示时区，取得状态页 URL。"
    href="https://alice39s.github.io/kuma-mieru/zh/configuration/uptime-kuma/"
    icon={<Link />}
  />
  <Card
    title="环境变量"
    description="查看全部变量、默认值和修改后的生效方式。"
    href="https://alice39s.github.io/kuma-mieru/zh/configuration/environment/"
    icon={<Settings2 />}
  />
  <Card
    title="常见问题"
    description="时区偏移、配置不生效、嵌入 iframe 等问题的处理方法。"
    href="https://alice39s.github.io/kuma-mieru/zh/guides/faq/"
    icon={<CircleHelp />}
  />
</Cards>
