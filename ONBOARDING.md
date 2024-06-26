# 👤 Accounts

You're going to need to make sure you've been invited to all of these accounts

- Google Account
- Figma 
- 1Password ("Web Dev" Vault)
- Slack (especially developer channels, and the "@dev" User Group!)
- Asana
- Github (added to Infinite Objects organization and assigned a team)
- Shopify
- Sentry
- Crossbrowsertesting (shared account in 1pass)
- PM2
- Paw
- Google Calendars
  - “Infinite Objects” Calendar
  - “IO OOO” Calendar
  - Reoccuring meetings

# 💾 Downloads

 Now let’s start with some downloads. 

- XCode CLI tools
- [homebrew](https://brew.sh/)
- NVM: `brew install nvm`
- Node 14: `nvm install 14`
- JDK: `brew install java`
- Shopify Theme Kit: `brew tap shopify/shopify` `brew install themekit`
- GCloud: `brew tap homebrew/cask` and `brew install --cask google-cloud-sdk`
- Terraform: `brew install terraform`
- Rush: `npm install -g @microsoft/rush`
- [Visual Studio Code](https://code.visualstudio.com/download)
- [Docker Desktop](https://www.docker.com/products/docker-desktop)
- [Cyberduck](https://cyberduck.io/)
  - Setup: Open Connection > Google Cloud Storage > Project ID = `io-ugc-v1` > Connect > Follow instructions
- [iTerm2](https://iterm2.com/) (optional)
- ZSH
  - [Oh my Zshell](https://ohmyz.sh/) if you're cool 😎
- [Paw](https://paw.cloud/)
- [Jumpcut](https://snark.github.io/jumpcut/)
- [Rectangle](https://rectangleapp.com/)
- [1Password desktop app](https://1password.com/downloads/mac/)
- [Stoplight Studio](https://stoplight.io/studio/)
- [TeamViewer](https://www.teamviewer.com/en-us/)
- [Export Original Images Figma Plugin](https://www.figma.com/community/plugin/973190386632562805/Export-Original-Images)
  - Figma is the source of truth for assets to use in development stories, use this plugin to export the original files

Chrome Extensions
- [mermaid-diagrams](https://chrome.google.com/webstore/detail/mermaid-diagrams/phfcghedmopjadpojhmmaffjmfiakfil)
- [JSON Formatter](https://chrome.google.com/webstore/detail/json-formatter/mhimpmpmffogbmmkmajibklelopddmjf)
- [GoFullPage - Full Page Screen Capture](https://chrome.google.com/webstore/detail/gofullpage-full-page-scre/fdpohaocaechififmbbbbbknoalclacl)
- [MetaMask](https://chrome.google.com/webstore/detail/metamask/nkbihfbeogaeaoehlefnkodbefgpgknn?hl=en)
- [1Password Chrome extension](https://chrome.google.com/webstore/detail/1password-%E2%80%93-password-mana/aeblfdkhhhdcdjpifhhbdiojplfjncoa)

VS Code Extensions
- [Markdown Preview Mermaid Support](https://marketplace.visualstudio.com/items?itemName=bierner.markdown-mermaid)


# 🔑 Credentials

## 💻 Github and NPM
- [Follow these instructions](https://docs.github.com/en/github/authenticating-to-github/keeping-your-account-and-data-secure/creating-a-personal-access-token) to create a Github personal access token. (NOTE: Keep the token handy for the next couple steps!)
  - Make sure to define the full `repo` scope as well as the `write:packages` scope
- `git clone` via HTTPS one of the UI repo (or any IO repo) and use that token as your password when prompted.
- Create a `~/.npmrc` file with these contents: `//npm.pkg.github.com/:_authToken=TOKEN`
- Run `npm login --scope=@infiniteobjects --registry=https://npm.pkg.github.com`
  - Use the same Github Token from earlier when prompted for your password

## 🌥 Google Cloud
- You're going to need to be added as a user to our GCP sandbox and production environments
- And be provisioned service account keys for both environments to use locally in your repos
