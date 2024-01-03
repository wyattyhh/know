---
layout: default
title: Refactoring
parent: Book
---

# Refactoring
{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## 1.  [Refactoring: A First Example](https://memberservices.informit.com/my_account/webedition/9780135425664/html/opening.html)
## 2. [Principles in Refactoring](https://memberservices.informit.com/my_account/webedition/9780135425664/html/principles.html)
## 3. [Bad Smells in Code](https://memberservices.informit.com/my_account/webedition/9780135425664/html/smells.html)
### Mysterious Name
> When you can't think of a good name for something, it's often a sign of a deeper design malaise.
### Long Function
>The net effect is that you should be much more aggressive about **decomposing functions**. A heuristic we follow is that **whenever we feel the need to comment something, we write a function instead**. Such a function contains the code that we wanted to comment but is named after the _intention_ of the code rather than the way it works. We may do this on a group of lines or even on a single line of code. **We do this even if the method call is longer than the code it replaces** - provided the method name explains the purpose of the code. The key here is not function length but the semantic distance between what the method does and how it does it.
## 4. 
### The Value of Self-Testing Code
> Make sure all tests are fully **automatic** and that they check their own results.

**Spend your time to write self-testing code! **

>Soon, I began to notice my productivity had shot upward. I realized that I wasn’t spending so much time debugging. If I added a bug that was caught by a previous test, it would show up as soon as I ran that test. The test had worked before, so I would know that the bug was in the work I had done since I last tested.

>The Test-Driven Development approach to programming relies on short cycles of writing a (failing) test, writing the code to make that test work, and refactoring to ensure the result is as clean as possible.