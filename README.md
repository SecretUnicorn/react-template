# Setup

Node is required: https://nodejs.org/en/download/
Git is required ... duh
```bash
git clone --recurse-submodules ssh://git@gitlab.8gm.subdns.de:2222/nahlers/react-template.git APPNAME
cd APPNAME
# If submodules have not been initialized use
# git submodule init
# git submodule update
git remote set-url origin <remote_url> # Do this to not push into this repository
npm install
npm run prepare
touch .env.local
echo VITE_API_BASE= DJANGO_URL > .env.local
npm run dev
```

### Husky

Staged files are getting automaticly checked with eslint. Only code with 0 warnings can be commited!

_**Warning:** When errors are present fix those and use `git add .` otherwise the next commit try overrides the changes!_

### Env-Files

```bash
.env                  # loaded in all cases
.env.local            # loaded in all cases, ignored by git
.env.[mode]           # only loaded in specified mode
.env.[mode].local     # only loaded in specified mode, ignored by git
.env.production.local # used in production ( run build ), ignored by git
```

For more information refer to: https://vitejs.dev/guide/env-and-mode.html

| Name                  | Type | Default | Example                 | Required?  |
|-----------------------|------|---------|-------------------------|----------- |
| VITE_API_BASE         | STR  | -       | http://10.10.10.57:8100 | ✅         |
| VITE_DEPLOY_BASE_NAME | STR  | /       | /kaufinteressten/       | ❌         |
| VITE_DEV_PORT         | INT  | 3100    | 3200                    | ❌         |
