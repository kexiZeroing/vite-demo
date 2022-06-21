## Vue and Vite project
Create a new app out of the template `degit antfu/vitesse-lite myapp` without git history, or build the app from scratch: 

```sh
# create project with Vite + Vue
npm init vue@latest
git init
pnpm i  # https://pnpm.io

# install extensions
# ni https://github.com/antfu/ni
ni -D unplugin-vue-components  # https://github.com/antfu/unplugin-vue-components
ni -D unplugin-auto-import  # https://github.com/antfu/unplugin-auto-import
ni -D unocss  # https://github.com/unocss/unocss

# netlify deploy
# https://app.netlify.com/teams/kexizeroing/overview
touch netlify.toml  # https://github.com/antfu/what-time/blob/main/netlify.toml
Go to `app.netlify.com`, Add new site -> import an existing project from Github
```
