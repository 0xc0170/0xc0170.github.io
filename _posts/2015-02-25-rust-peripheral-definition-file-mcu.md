---
layout: post
title: "rust for embedded projects - peripheral definitions file"
date: 2015-02-25
comments: true
categories:
 - rust
---

I have been thinking lately about rust device drivers, it started looking at various projects written in rust, aiming at embedded. There are some simple applications or even robust embedded stacks (zinc for example). I published one simple blinky demo for FRDM-KL25Z board, and one blinky example with mbed library (using rust FFI, to see how to use it). For baremetal demo, I had "reinvent" the wheel. Need a timer, have to define registers. A snippet for KL25Z SIM peripheral:

{% highlight ruby %}
const BASE_SIM : u32 = 0x40047000;

pub struct Sim {
    pub sopt1 : VolatileRW<u32>,
    pub sopt1cfg : VolatileRW<u32>,
    pub reserved_0 : [u8; 4092],
    pub sopt2 : VolatileRW<u32>,
    pub reserved_1 : [u8; 4],
    pub sopt4 : VolatileRW<u32>,
    pub sopt5 : VolatileRW<u32>,
    pub reserved_2 : [u8; 4],
    pub sopt7 : VolatileRW<u32>,
    pub reserved_3 : [u8; 8],
    pub sdid : VolatileRW<u32>,
    pub reserved_4 : [u8; 12],
    pub scgc4 : VolatileRW<u32>,
    pub scgc5 : VolatileRW<u32>,
    pub scgc6 : VolatileRW<u32>,
    pub scgc7 : VolatileRW<u32>,
    pub clkdiv1 : VolatileRW<u32>,
    pub reserved_5 : [u8; 4],
    pub fcfg1 : VolatileRW<u32>,
    pub fcfg2 : VolatileRW<u32>,
    pub reserved_6 : VolatileRW<u32>,
    pub uidmh : VolatileRW<u32>,
    pub uidml : VolatileRW<u32>,
    pub uidl : VolatileRW<u32>,
    pub reserved_7 : [u8; 156],
    pub copc : VolatileRW<u32>,
    pub srvcop : VolatileRW<u32>,
}

impl Sim {
    pub fn get() -> &'static Sim {
        unsafe {
            &*(BASE_SIM as *const Sim)
        }
    }
}
{% endhighlight %}

As rust does not use header files, CMSIS files are no use. They simplify development, as they are provided in various tools or available online with permissive license. Download and start using the defined register structures or all macros predefined to mask bits in registers or set values. A lot of software around is based on it.

I would like to look at parsing cmsis header file and redefine structures to rust structures. I'll give it a shot with [rust-binden](https://github.com/crabtw/rust-bindgen), or another option is to parse svd file.

Any other ideas?
