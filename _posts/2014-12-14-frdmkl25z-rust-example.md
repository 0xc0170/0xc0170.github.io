---
layout: post
title: "FRDM-KL25Z rust demo"
date: 2014-12-14
comments: true
categories:
 - rust
---

Rust has been on scene for a while, but ignored by me. Once I spotted there's zinc, I glanced at the implementation and there was something which picked up my interest. I started contributing to zinc. You should be able to run demo on FRDM-K20 board with small modifications.

I usually start with simple things to quickly learn. I have been looking for a simple project running on ARM. There are few on github, often not up to date with the latest rust version.

The aim of an example would be to build a blinky demo, be able to flash it to the MCU and be able to debug it. Not to use any C file or assembly, entire startup plus vectors written in Rust.

The example is here [github.com/0xc0170/frdm-kl25z-rust](https://github.com/0xc0170/frdm-kl25z-rust). Read readme, where are all instructions to be able to build the blinky.

Wonder what's the size of this blinky demo? The answer:

**text    data     bss     dec     hex**

1056       0       0    1056     420

The only depedency is libcore.

I would like to find more time to write about zinc, and explain this demo in more details, how are things implemented. Another goal is to have IDE for debugging. I have been using gdb command line so far.

By the way, there was announced this week that Rust 1.0 will be released in February 2015.
