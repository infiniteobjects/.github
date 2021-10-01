# Welcome to IO


## Accounts

You're going to need to make sure you've been invited to all of these company wide accounts

- Google Account
- Pivotal Tracker
- Figma
- 1Password
- Slack
- Asana
- Github (need to be added to Infinite Objects organization)
- Shopify
- Sentry
- Crossbrowsertesting

## Tokens

Once you've been added to the IO Github Org, you're going to need to [follow these instructions](https://docs.github.com/en/github/authenticating-to-github/keeping-your-account-and-data-secure/creating-a-personal-access-token) to create a Github personal access token.

After you have your token `git clone` of one of the IO repos and use that token as your password when it prompts you.

You're going to also need this line with your token to your `~/.npmrc` file:
`//npm.pkg.github.com/:_authToken=TOKEN`

And lastly, you're going to need to sign into `npm` with this token. Type this in your terminal and use the token as your password once again.

`npm login --scope=@infiniteobjects --registry=https://npm.pkg.github.com`

## Calendars

Someone is also going to need to be added to 2 Calendars in your Google Account: “Infinite Objects” and “IO OOO”.

## Downloads

Now let’s start with some downloads. 

- XCode CLI tools
- Visual Studio Code
- iTerm2 (optional)
- homebrew
- Node 14 via homebrew: `brew install node`
- JDK via homebrew: `brew install java`
- Shopify Theme Kit: `brew tap shopify/shopify` `brew install themekit` 
- Docker

Chrome Extensions
- [mermaid-diagrams](https://chrome.google.com/webstore/detail/mermaid-diagrams/phfcghedmopjadpojhmmaffjmfiakfil)
- [JSON Formatter](https://chrome.google.com/webstore/detail/json-formatter/mhimpmpmffogbmmkmajibklelopddmjf)
- [Better Pull Request for GitHub](https://chrome.google.com/webstore/detail/better-pull-request-for-g/nfhdjopbhlggibjlimhdbogflgmbiahc)
- [GoFullPage - Full Page Screen Capture](https://chrome.google.com/webstore/detail/gofullpage-full-page-scre/fdpohaocaechififmbbbbbknoalclacl)

VS Code Extensions
- [Markdown Preview Mermaid Support](https://marketplace.visualstudio.com/items?itemName=bierner.markdown-mermaid)

## Readings

- After you’ve bootstrapped your machine, Be sure to read through our [Developer Manifesto](https://github.com/infiniteobjects/.github/blob/main/CONTRIBUTING.md) before you begin coding.

- In fact, the [Default Files repo](https://github.com/infiniteobjects/.github/)  where that Developer Manifesto (and this document) lives is a good place to poke around our organization wide docs.

- Check out our [common IO configs repo](https://github.com/infiniteobjects/utils-web-configs) to get a sense of the rules we usually bootstrap our apps with (`prettier`, `postcss`, `eslint`...)

- Finally, [this](https://docs.google.com/document/d/1Zeexj_N7ACkXIdXEn0E2LafOTjvXL8pobhM9dr5aVw8/edit) is a running list of all the apps at IO. You can find the designs, repos, general notes and definitions here. A great place to start.


