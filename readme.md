# Step-by-step install & setup

1) Prerequisites

● Shopify Partner account and a development store (use Partner Dashboard → Create dev store).

● Node.js (LTS) and npm — download from nodejs.org or use nvm-windows.

● Git (Git for Windows).

● VS Code (recommended editor).

Check installs:

```sh
node -v
npm -v
git --version
```

2) Install Shopify CLI and theme tool
Open PowerShell / terminal and run:

```sh
npm install -g @shopify/cli @shopify/theme
```

Verify:

```sh
shopify version
```

(If you prefer, use the native Shopify installers documented on Shopify’s site.)

3) Authenticate to your store
Login to your dev store:

```sh
shopify login --store your-store.myshopify.com
```

Follow the browser prompts to connect your CLI session.

4) Create or clone a theme
To scaffold an official starter theme (e.g., Dawn):

```sh
shopify theme init my-theme
cd my-theme
```

Or clone an existing theme repository with Git:

```sh
git clone <repo-url> my-theme
cd my-theme
```

5) Start local development server
Run:


```sh
shopify theme dev
```

This serves the theme and opens a live preview tunnel to your store so you can see changes in real time.

6) Edit Liquid files in your editor
Open the project in VS Code:

```sh 
code .
```

Recommended extensions:

● Shopify Liquid (syntax highlighting & snippets)

● Theme Check (linting for Shopify theme best practices)

● Prettier + Liquid plugin (optional: consistent formatting)

● Tip: templates/, sections/, snippets/ are where Liquid files live.

7) Linting & testing
● Use the Theme Check VS Code extension or run a theme linter if you installed the Theme Check tool (Ruby gem or integrated tool).

● Test functionality on your dev store and with shopify theme dev open to verify real-world behavior.

8) Deploy / push changes to a store
When ready:

```sh 
shopify theme push
```

Or use git-based workflows and deploy from CI — whichever matches your team process.

⚠️ Troubleshooting & tips

● Use a dev store for safe testing (not a live production store).

● If the CLI prompts about permissions or scopes, accept the minimal required scopes for theme dev.

● If shopify theme dev fails due to firewall/tunnel, try a different network or check VPN/firewall rules.

● Keep Shopify CLI up to date:

```sh
npm update -g @shopify/cli @shopify/theme
```

✅ Wrap-up
● Install Node.js, Git, VS Code → install Shopify CLI → login → scaffold/clone a theme → run shopify theme dev → edit Liquid files and use Theme Check.