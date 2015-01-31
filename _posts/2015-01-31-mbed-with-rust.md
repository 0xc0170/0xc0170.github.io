---
layout: post
title: "mbed and rust?"
date: 2015-01-31
comments: true
categories:
 - rust, mbed
---

While I was reading about rust ffi (http://doc.rust-lang.org/book/ffi.html), I had a though what if I try rust with mbed library? The mbed library consists of two parts - C++ API and HAL (cmsis and target hal), which is written in C. This can be an exercise how to interact with C world.

I built the mbed library for K64F with GCC, copied files which are required for an application to link, and started writing small rust demo. The fastest approach is to create a module DigitalOut which would imitate what C++ class DigitalOut does - initialize gpio pin as output, write and read methods. If I make the blinky working, I got clock running, and being able to call C functions, which would do all "the hard work" for me.

Most of FFI examples are not for embedded or better said bare-metal. Using libc, dynamic allocations and many features I did not want to start with. Therefore DigitalOut currently have predefined array which equals to gpio_t object for K64F - 4 bytes. I woudl like to find better way to handle a memory required for C HAL, as gpio_t differs per platform.

The link to the K64F mbed blinky - [mbed-rust-frdm-k64f-blinky](https://github.com/0xc0170/mbed-rust-frdm-k64f-blinky). It uses a makefile, prebuilt mbed library for K64F.

### The current status

The wait() is commented out as currently it's not functional, will need to look at it.
There's lot of to improve, I would like to turn it to cargo modules, have mbed as submodule and depending on the target, to create a library for it's HAL and many others things. I would like to find a easy way to have enums in rust, as mbed targets have PinNames which are used in the programs, like LED1 or PTA10.
