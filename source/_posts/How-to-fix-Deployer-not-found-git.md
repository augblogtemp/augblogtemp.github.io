---
title: 'How to fix Deployer not found: git'
categories:
  - Dev
  - Hexo
tags:
 - Hexo
 - Blog
 - GitHub
 - Node.js
 - Git
date: 2018-01-11 22:38:51
thumbnail: /images/thumbnail/deployer.jpg
---
# ERROR Deployer not found: git
This error occurs, if you don't install *`hexo-deployer-git`* but attempt to deploy.

---

# Solution
```bash
$ npm install hexo-deployer-git --save
```
Then open `_config.yml`, fix `#deployment`
```bash
# Deployment
## Docs: https://hexo.io/docs/deployment.html
deploy:
  type: git
  repo: https://github.com/your_github_id/your_github_id.github.io.git
  branch: master
```
