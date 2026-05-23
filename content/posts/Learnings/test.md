---
title: "First time site didn't build out"
summary: Devops Learning
date: 2026-05-22
weight: 1
aliases: ["/First-time-site-async"]
tags: ["tech", "Docs", "Learnings", "devops"]
author: ["Nick Hong"]

---

### Intro

During my learnings for AWS cert that lead me into the rabbit hole use case of kafka I decided to create a post on my website to consolidate my learnings.

After pushing the new content.  It wasn't loading up.  hmmmmm.  I went to check my github repository and looked into the github actions.  It was throwing errors.  One was for a deprecated share code snippet gist.  Seems Github broke their own embed API.  Hugo then decide to remove it.  This cause me to use the Search future on Visual Studio Code IDE and find replace.  I could have down the same in command line using grep -n "gist" content/posts/code_syntax.md which displayed which files had gist.  Went into each file and removed all tracings.