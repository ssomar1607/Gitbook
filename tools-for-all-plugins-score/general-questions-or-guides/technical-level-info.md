---
description: >-
  Only useful for people who pay attention on the tiniest
  info/function/mechanics about how plugins such as ExecutableItems,
  ExecutableBlocks work
---

# Technical-Level Info



## Activator Execution Properties

* Commands run first before variable update, causing items that spawn particles in one place to be impossible in the free version
* In some cases, activators run faster than commands so even if you used the action counter method and used SCore variables instead of item variables, it won't work.
