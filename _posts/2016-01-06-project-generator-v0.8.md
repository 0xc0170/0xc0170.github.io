---
layout: post
title: "Project generator v0.8"
date: 2016-01-06
comments: true
categories:
 - python
---

I am skipping one version, going directly for v0.8 (the last time I wrote here was for progen v0.6). There were lot of changes introduced for the last 2 versions of progen (name change was the main one, from pgen to progen). I'll summarize changes here, how is progen looking today and we might get some details what's coming. All that work made me busy for weeks, I wanted to finish it as soon as possible as there were many major changes which affects user experience.

### Progen defininitions

The progen definitions were taken out from progen, and now resides as a python module. The main reason was there were going to be breaking changes, and they were not versioned.

The target got smarter, we introduced debuggers, as before only cmsis-dap was set for a target, a project had to set a debugger.

{% highlight ruby %}
    # target definition
    'efm32wg-stk': {
        'mcu':'mcu/siliconlabs/efm32wg990f256',
        'debugger': {
            'name': 'j-link',
            'interface': 'swd',
        }
    },
{% endhighlight %}

Target or MCU can be used, both are checked if it's supported. As above highlighted, currently only debugger definition is an advantage to use target, than MCU.

### Internal redesign

Thanks to Sarah Marshy, who did a lot of code reviews, which led to simplification, improvements in the code base. The main redesign was around Project class. There were many bugs fixed with this redesigning. I like how it turned out. There's still space for refactoring, but hopefully not that major as it was.

I created a design document where we should capture the ideas about how progen works, and why was it design the way it is. Anyone new coming to progen can have a look to get an idea how it's layered and all connected together.

I added workspaces, however I consider the project is the most usable feature, thus workspaces will require bit of more work to make it right, if someone is interested using them.

The debug logger prints the data collected (common, tool specific and merged for generating), plus it dumps to a log file. It's useful to see what progen collected. There are times when a generated project misses an include or an option in the project. Just add to command -vv and logging should be set to debug.

### Tools

We got a new tools, cmake, visual studio were added. Visual studio is limited at the moment, as their plugin is feature-rich, I hope the gdb there gets update, so we can use it with yotta or other tools. I tested it with pyOCD, it works, but sometimes I hit some exception in their engine, did not elaborate as I assume it will be updated soon, then we can test further.

Makefile template got generic, using similar syntax than CMake (flags).

Tools like uvision and IAR which provide command line options got this implemented as misc option. As misc, ld_flags - --linker-command-line-flag, which gets then injected into the generated project.

uvision was split to uvision4 and uvision5. They are alike, but uvision5 uses new software packs, which make difference mainly for mcu definitions, thus a user should properly choose and we should provide definitions for both tools. The new packs have versioning, which is new.

### Tests

We used to run into issues, and changes which lead to be a breaking changes sometimes or even misunderstood features. This was a wakeup call for me to start writing tests for everything, every regression to be captured. They caught lot of errors in our code base, or even wrong implementation for features we provided.

Feel free to look at the tests, you can grasp ideas how to use progen.

### mbed integration

Yes, progen will come to mbed SDK. There are exporters which are using templates, lot of templates, no tests. There's open PR to first add only progen to be able to use its API to generate projects. I have working uvision and IAR, it will take some time to fully tested and not to cause any regression. I estimate this can be done within January this year. 

By time, progen can replace all exporters there, and provide unified way to generate projects. Then all this can be used for mbed OS or any other project which needs generating project files.

### What we can expect for v1.0.0

This version will come within Q1 or Q2, depends on how fast we do mbed integration. I would like to get more projects/developers involved. Using progen in mbed will prove progen is capable of exporting to various tools, using only python (no yaml files), providing definitions for hundreds of MCUs.

The aim should be at docs. I already wrote a porting guide in the wiki pages, which needs more love plus reviews! Expand the tools, to add some vendors tools like LPCExpresso, Freescale KDS or Atmel Studio.
