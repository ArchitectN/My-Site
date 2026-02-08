---

title: "Building Hugo"
summary: Learn hhow I built my ArchitectN blog site
date: "2025-12-05"
description: "How I built Hugo"
weight: 1
aliases: ["/building-ArchitectN"]
tags: ["tech", "Docs"]
author: ["Nick Hong"]
---


## Test
return the markdown

### Breakdown of How I setup ArchitectN

- Themes reside in `MyFreshWebsite/themes` directory.
- PaperMod will be installed in `MyFreshWebsite/themes/PaperMod`

> {{< collapse summary="**Expand Step 1 - Setup Hugo**" >}}

**INSTALL** : Inside the folder of your Hugo site `MyFreshWebsite`, run:

```bash
git clone https://github.com/adityatelange/hugo-PaperMod themes/PaperMod --depth=1
```

You may use ` --branch v7.0` to end of above command if you want to stick to specific release.

**UPDATE**: Inside the folder of your Hugo site `MyFreshWebsite`, run:

```bash
cd themes/PaperMod
git pull
```

{{</ collapse >}}

> {{< collapse summary="**Expand Method 2 - Git Submodule (recomended)**" >}}

**INSTALL** : Inside the folder of your Hugo site `MyFreshWebsite`, run:

```bash
git submodule add --depth=1 https://github.com/adityatelange/hugo-PaperMod.git themes/PaperMod
git submodule update --init --recursive # needed when you reclone your repo (submodules may not get cloned automatically)
```

You may use ` --branch v7.0` to end of above command if you want to stick to specific release.
Read more about git submodules [here](https://www.atlassian.com/git/tutorials/git-submodule).

**UPDATE**: Inside the folder of your Hugo site `MyFreshWebsite`, run:

```bash
git submodule update --remote --merge
```

{{</ collapse >}}

> {{< collapse summary="**Expand Method 3 - Download an unzip**" >}}

Download PaperMod source as Zip from Github Releases and extract in your themes directory at `MyFreshWebsite/themes/PaperMod`

Direct Links:

- [Master Branch (Latest)](https://github.com/adityatelange/hugo-PaperMod/archive/master.zip)
- [v7.0](https://github.com/adityatelange/hugo-PaperMod/archive/v7.0.zip)
- [v6.0](https://github.com/adityatelange/hugo-PaperMod/archive/v6.0.zip)
- [v5.0](https://github.com/adityatelange/hugo-PaperMod/archive/v5.0.zip)
- [v4.0](https://github.com/adityatelange/hugo-PaperMod/archive/v4.0.zip)
- [v3.0](https://github.com/adityatelange/hugo-PaperMod/archive/v3.0.zip)
- [v2.0](https://github.com/adityatelange/hugo-PaperMod/archive/v2.0.zip)
- [v1.0](https://github.com/adityatelange/hugo-PaperMod/archive/v1.0.zip)

{{</ collapse >}}

> {{< collapse summary="**Expand Method 4 - Hugo module**" >}}

**INSTALL** :

- Install [Go programming language](https://go.dev/doc/install) in your operating system.

- Intialize your own hugo mod

```
hugo mod init YOUR_OWN_GIT_REPOSITORY
```

- Add PaperMod in your `config.yml` file

```go {linenos=true}
module:
  imports:
  - path: github.com/adityatelange/hugo-PaperMod
```

**UPDATE**:

```
hugo mod get -u
```

Read more : [Hugo Docs's - HUGO MODULES](https://gohugo.io/hugo-modules/use-modules/)

{{</ collapse >}}
