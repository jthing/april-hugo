---
title: "SBCL GC"
date: 2023-11-16T06:24:00+01:00
tags: ["april"]
draft: false
---

## New Garbage collector in 2.3.8 {#new-garbage-collector-in-2-dot-3-dot-8}

There is a new parallel garbage collector in SBCL 2.3.8 It is not enabled by default. To
enable do a git clone of SBCL and make sure you have version 2.3.8. When compiling use
'sh make.sh --without-gencgc --with-mark-region-gc'

Unfortunately after a git fetch I had SBCL 2.3.7.79-556d7db9e which gave the error
'Feature compatibility check failed, (":SB-THREAD requires :GENCGC" ...'

Anyhow here is a paper announcing the new garbage collector.

[Parallel garbage collection for SBCL](/ox-hugo/swcl-gc.pdf)

and here is the paper describing the original one

[Trading Data Space for Reduced Time and Code Space in Real-Time Garbage Collection on Stock Hardware](https://www.hpl.hp.com/techreports/Compaq-DEC/WRL-TN-12.pdf)
