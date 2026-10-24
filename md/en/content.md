# Overview (https://alice39s.github.io/kuma-mieru/en/)

Kuma Mieru is a third-party monitoring dashboard for Uptime Kuma, built with Next.js 16, TypeScript and Recharts. It reads the data of Uptime Kuma public status pages and shows the latency and status of each monitor in interactive charts. The built-in public status page of Uptime Kuma has no latency charts and is hard to read at a glance. Kuma Mieru adds these charts and a clearer layout.

<Callout type="warn" title="Set the Uptime Kuma display time zone to UTC+0">
  Version 1.1.4 and later use new time handling logic. In the Uptime Kuma settings, set `Display
  Timezone` to a UTC+0 time zone. For the reason, see the [FAQ](https://alice39s.github.io/kuma-mieru/en/guides/faq/).
</Callout>

## Features [#features]

- The status updates in real time, and the page refreshes automatically.
- The interface uses HeroUI components and fits screens of different sizes.
- Interactive Recharts charts show the latency and status of each node.
- Three themes are available: dark, light and system.
- The dashboard shows the incident updates and status events of the Uptime Kuma status page.
- One Kuma Mieru instance can show multiple status pages. The status pages can come from different Uptime Kuma instances.

## Screenshots [#screenshots]

<Tabs items={['Light theme', 'Dark theme']}>
<Tab value="Light theme">

![Light theme](</kuma-mieru/_next/static/media/v1.2.1-light-en.3q9r5zlffny9w.png>)

</Tab>
<Tab value="Dark theme">

![Dark theme](</kuma-mieru/_next/static/media/v1.2.1-dark-en.3n44ru4vwcnno.png>)

</Tab>
</Tabs>

## Tech stack [#tech-stack]

| Purpose               | Technology              |
| --------------------- | ----------------------- |
| Framework             | Next.js 16, React 19    |
| Language              | TypeScript              |
| Charts                | Recharts                |
| Components and styles | HeroUI, Tailwind CSS v4 |
| Package manager       | Bun                     |

## Next steps [#next-steps]

<Cards>
  <Card
    title="Choose a deployment method"
    description="Compare Vercel, Netlify, EdgeOne Pages, Docker and running from source."
    href="https://alice39s.github.io/kuma-mieru/en/deploy/"
    icon={<Rocket />}
  />
  <Card
    title="Connect Uptime Kuma"
    description="Create a status page, set the display time zone and get the status page URL."
    href="https://alice39s.github.io/kuma-mieru/en/configuration/uptime-kuma/"
    icon={<Link />}
  />
  <Card
    title="Environment variables"
    description="See all variables, their defaults and when a change takes effect."
    href="https://alice39s.github.io/kuma-mieru/en/configuration/environment/"
    icon={<Settings2 />}
  />
  <Card
    title="FAQ"
    description="Fix time offsets, configuration changes that do not apply, iframe embedding and more."
    href="https://alice39s.github.io/kuma-mieru/en/guides/faq/"
    icon={<CircleHelp />}
  />
</Cards>
