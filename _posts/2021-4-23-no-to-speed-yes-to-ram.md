---
date: '2021-4-23'
title: 'No to speed, yes to ram: Why CiCI will never be quick, but will be the more versatile.'
slug: 'no-to-speed-yes-to-ram'
layout: post
permalink: '/articles/revolutions/no-to-speed-yes-to-ram/'
---

# No to speed, yes to ram: Why CiCI will never be quick, but *will be* the more versatile.

_By **[that mar](https://github.com/that-mar)**._
_2021-4-23_

While thinking about the MAASL project and drawing the first lines of CiCI, I knew one thing: *RAM management for variables is nasty.* So, as the true dreamer that I am, I continued my sentence. *let's clean it up by opening that cesspit, and just completely ignoring the rest.* 

I did that while writing the [.:](https://asccisl-org.github.io/docs/Commands/dot/dotcolon/)-command, inspired by my strong hate for the way variables work in Java.

> In programming languages, numbers are typically split into 32-bit  numbers, and 64-bit numbers. In Batch, you had to evoke PowerShell to be able to use 64-bit numbers. And in JAVA the variables of numbers and of what it calls ‘`doubles`’  are two entirely different things. 32-bit numbers and 64-bit numbers.
>
> In CiCI, variables are not saved in ram, but put directly into a temporary file (`(temp folder)/CiCISessions/(session).tmp/vars/(varname).cicivar`).
>
> This might slow down CiCIscripts a lot, especially in case of  number variables. And that’s where .:# comes in. It defines a number,  not a string. Even though it won’t change the way the variable can be  called it does make CiCI aware that is a number that needs to be in the  RAM, and CiCI will have to figure out what type of number it is.

The idea of having RAM handled by the programming language did appeal to me, and its the thought behind doing this. 
The RAM handling should be automatic, but should not hold any programmer back. That is why I decided to take over parts of Java's approach, the way numbers are stored is okay, but CiCI will have to determine the difference between integer variables and double variables, and if not clear just treat them like a string.
A string can be used in place of a number, because the separate commands are to hand out errors, not the variables themselves.

The strings are going to be a bit different, they will only be in RAM while a command calling them is running. Meaning that _once the variable is written to a **variable file**, it will be removed from RAM before the next command is ran._ 

