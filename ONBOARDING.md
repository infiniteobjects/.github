# 👤 Accounts

You're going to need to make sure you've been invited to all of these accounts

- Google Account
- Pivotal Tracker
- Figma
- 1Password
- Slack
- Asana
- Github (need to be added to Infinite Objects organization and assigned a team)
- Shopify
- Sentry
- Crossbrowsertesting (Shared account in 1pass)
- PM2
- Paw
- Google Calendars: “Infinite Objects” and “IO OOO”.

# 💾 Downloads

 Now let’s start with some downloads. 

- XCode CLI tools
- Visual Studio Code
- homebrew
- NVM
- Node 14 via `nvm`
- JDK: `brew install java`
- Shopify Theme Kit: `brew tap shopify/shopify` `brew install themekit` 
- Docker
- Cyberduck
- iTerm2 (optional)
- ZSH
- Paw
- [Jumpcut](https://snark.github.io/jumpcut/)
- [Rectangle](https://rectangleapp.com/)

Chrome Extensions
- [mermaid-diagrams](https://chrome.google.com/webstore/detail/mermaid-diagrams/phfcghedmopjadpojhmmaffjmfiakfil)
- [JSON Formatter](https://chrome.google.com/webstore/detail/json-formatter/mhimpmpmffogbmmkmajibklelopddmjf)
- [Better Pull Request for GitHub](https://chrome.google.com/webstore/detail/better-pull-request-for-g/nfhdjopbhlggibjlimhdbogflgmbiahc)
- [GoFullPage - Full Page Screen Capture](https://chrome.google.com/webstore/detail/gofullpage-full-page-scre/fdpohaocaechififmbbbbbknoalclacl)
- [MetaMask](https://chrome.google.com/webstore/detail/metamask/nkbihfbeogaeaoehlefnkodbefgpgknn?hl=en)
- [1Password](https://chrome.google.com/webstore/detail/1password-%E2%80%93-password-mana/aeblfdkhhhdcdjpifhhbdiojplfjncoa)

VS Code Extensions
- [Markdown Preview Mermaid Support](https://marketplace.visualstudio.com/items?itemName=bierner.markdown-mermaid)


# 🔑 Tokens

- [Follow these instructions](https://docs.github.com/en/github/authenticating-to-github/keeping-your-account-and-data-secure/creating-a-personal-access-token) to create a Github personal access token. (NOTE: Keep the token handy for the next step!)
  - Make sure to define the full `repo` scope as well as the `write:packages` scope
- `git clone` via HTTPS one of the UI repo (or any IO repo) and use that token as your password when prompted.
- Create a `~/.npmrc` file with these contents: `//npm.pkg.github.com/:_authToken=TOKEN`
- `npm login --scope=@infiniteobjects --registry=https://npm.pkg.github.com`


