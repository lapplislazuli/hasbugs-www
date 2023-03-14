# Hasbugs Website

Main repository at [Ciselab/HasBugs](https://github.com/ciselab/HasBugs).
This repository is used to build the website only.

## How to 

**Serve:**

```
hugo serve
```

**Build:** 

```
hugo --minify
```

Output will be in `./public` and can be copied.

*Important*: There is a second branch `ciselab-page` that is used to host the website under https://ciselab.github.io/HasBugs/ , 
it changes some URLs in the config. 

To adjust: 

```
git checkout ciselab-page
git rebase main
hugo --minify
```

Then the `./public` (all contents) can be copied to the branch `gh-pages` (everything at root level).  A push will then publish the site (takes ~ 2 minutes). 

## Other reading 

- [Hugo Quickstart](https://gohugo.io/getting-started/quick-start/)