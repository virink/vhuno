## Github Pages

### Sign up an account for Github.com

[Github](https://github.com)

### New repository for Github Pages

- New repository
- Repository named: `username.github.io`
- Create it

## Hexo

### Env && Install

- [Node.js](http://nodejs.org/)
- [Git](https://git-scm.com/)

`npm install -g hexo-cli`

>[Hexo Docs](https://hexo.io/zh-cn/docs/)

### Create Your Site(Blog)

    cd ~
    hexo init your_site_name
    cd your_site_name
    npm install

## Deploy git

### Install Hexo Plugin

    npm install hexo-deployer-git --save

### Setting deploy in _confing.yml

    deploy:
      type: git
      repo: <repository url>
      branch: [branch]

eg:

    deploy:
      type: git
      repo: git@github.com:username/username.github.io
      branch: master

### Add SSH Key for Git

    cd ~/.ssh/
    ssh-keygen -t rsa -C "yourmail@mail.com"

- Copy your public key `id_rsa.pub` what your created
- Open your site url `https://github.com/username/username.github.io`
- -> Settings
- -> Deploy keys
- -> Add deploy key
- Input:
    - Title: anything
    - Key: your public key
- -> Allow write access
- -> Add key

## Updata Your Site

    hexo g
    hexo d

## Change Theme

[vHuno](README.md)