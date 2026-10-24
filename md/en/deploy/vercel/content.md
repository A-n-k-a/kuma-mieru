# Vercel (https://alice39s.github.io/kuma-mieru/en/deploy/vercel/)

Vercel is the recommended deployment method. You do all steps in the browser and need no server.

<Steps>
<Step>

### Fork the repository [#fork-the-repository]

1. Open the [fork page](https://github.com/Alice39s/kuma-mieru/fork) of this repository.
2. Click `Create fork`.

<Callout type="info">
  Keep your fork public. A private fork can prevent a quick sync of upstream updates. All
  configuration is in environment variables, so your fork contains none of your configuration.
</Callout>

</Step>
<Step>

### Import the repository to Vercel [#import-the-repository-to-vercel]

Open [vercel.com/new](https://vercel.com/new), find your fork and click `Import`.

![Import the repository](</kuma-mieru/_next/static/media/vercel-import.3ti7u11pp7bhz.png>)

</Step>
<Step>

### Set the root directory [#set-the-root-directory]

On the project configuration page, set `Root Directory` to `apps/web`. The web application and its `vercel.json` are in this directory.

</Step>
<Step>

### Add environment variables [#add-environment-variables]

Expand `Environment Variables` and add `UPTIME_KUMA_URLS`. Use the full URL of the Uptime Kuma status page as the value. Separate multiple status pages with `|`.

![Add environment variables](</kuma-mieru/_next/static/media/vercel-deploy.3qjqt-qnk-c4f.png>)

<Callout type="warn">
  You must set `UPTIME_KUMA_URLS` (recommended) or the legacy pair `UPTIME_KUMA_BASE_URL` and
  `PAGE_ID`. If neither is set, or a URL has no `/status/<page ID>` part, the `generate` script
  stops with an error and the Vercel build fails. For the other variables, see
  [Environment Variables](https://alice39s.github.io/kuma-mieru/en/configuration/environment/).
</Callout>

</Step>
<Step>

### Deploy [#deploy]

Click `Deploy`.

</Step>
</Steps>

## Change environment variables [#change-environment-variables]

Vercel runs the `generate` script during the build. The script writes the environment variables and the status page data into the generated configuration. After you change an environment variable on Vercel, redeploy the project to apply it.

## Sync upstream updates [#sync-upstream-updates]

1. Open your fork on GitHub and click `Sync fork`.
2. Click `Update branch` to get the latest code from the upstream repository.

## Vercel configuration in the repository [#vercel-configuration-in-the-repository]

`apps/web/vercel.json` sets these response headers for the home page `/`:

| Header                   | Value                                             |
| ------------------------ | ------------------------------------------------- |
| `Cache-Control`          | `public, max-age=300, stale-while-revalidate=300` |
| `X-XSS-Protection`       | `1; mode=block`                                   |
| `X-Content-Type-Options` | `nosniff`                                         |
