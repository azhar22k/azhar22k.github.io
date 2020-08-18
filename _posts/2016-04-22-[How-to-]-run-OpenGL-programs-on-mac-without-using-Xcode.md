---
layout: post
title:  "[How to ] run OpenGL programs on mac without using Xcode"
date:   2016-04-22 14:41:47 +0530
categories: [unix, macOS, openGL]
tags: [unix, macOS, openGL]
---

I recently moved from windows PC to Mac Book Air and as a Computer engineer I had to mess up with CGMT code(Although I hate it).

When I worked with windows PC, I just had to paste some .dll files in system32 and some header files in MinGw folder of code blocks.

But, for MAC, it is even more easy.

Mac already comes with all required header files, all you need is an IDE and a good compiler like Xcode but downloading and running 4gb IDE for such a small purpose is not worth it.

The answer is Code:BLocks IDE

* STEP 1

Download Code:Blocks from [here](http://www.codeblocks.org/downloads/binaries "Link to download code blocks")

* STEP 2

Unzip the file and paste the app in your applications folder.

* STEP 3

Now open code blocks and New Project > Glut Project and all done, Build and run all of your programs.

Note: Remember to replace with and remove which is not required on mac.

Thanks you, Hope it helped out.
