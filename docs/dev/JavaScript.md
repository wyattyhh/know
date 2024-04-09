---
layout: default
title:
---
# 
{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## Closure
A Function access variables outside of its own scope.
```js
let b = 3
function impureFun(a) {
	return a + b
}
```