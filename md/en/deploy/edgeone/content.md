# EdgeOne Pages (https://alice39s.github.io/kuma-mieru/en/deploy/edgeone/)

<Steps>
<Step>

### Fork the repository [#fork-the-repository]

Open the [fork page](https://github.com/Alice39s/kuma-mieru/fork) of this repository and click `Create fork`.

</Step>
<Step>

### Import the repository [#import-the-repository]

Log in to [EdgeOne Pages](https://pages.edgeone.ai), select the option to import a Git repository, and select your fork.

</Step>
<Step>

### Configure the build [#configure-the-build]

1. Set the root directory to `apps/web`.
2. Select the `Next.js` framework preset.

`apps/web/edgeone.json` sets the install command `bun install --frozen-lockfile` and the build command `bun run build`.

</Step>
<Step>

### Add environment variables and deploy [#add-environment-variables-and-deploy]

Add the `UPTIME_KUMA_URLS` environment variable with the full URL of the status page. Separate multiple URLs with `|`. Then start the deployment. For the other variables, see [Environment Variables](https://alice39s.github.io/kuma-mieru/en/configuration/environment/).

</Step>
</Steps>

## Change environment variables [#change-environment-variables]

The configuration is generated during the build. After you change an environment variable on EdgeOne Pages, redeploy to apply it.
