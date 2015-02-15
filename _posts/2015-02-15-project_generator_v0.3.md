---
layout: post
title: "project generator v0.3"
date: 2015-02-15
comments: true
categories:
 - python
---

The last days were quite short, as I have been developing the project generator. The last version (v0.2) was published in September. It got the update to the v0.3. What new is there?

First of all, the major change that it is now python [pypi package](https://pypi.python.org/pypi/project_generator). It's my very first python package published. The new structure of project generator is in smaller modules.

The board definition was introduced, means that the user does not need to define MCU for each tool (specific for each tool, as they name it differently, although it's the same chip). This is in the common section for a project:

{% highlight ruby %}
common:
  board:
    - mbed-lpc1768
{% endhighlight %}

To enable a new board, the board definiton needs to be defined and it's MCU if it's already not in the tool definitions. More to this will be available in the wiki page.
projects.yaml file becomes the default record file to contain all projects within a repo ,and even settings. If project generator is run without -f, it will look for this file in the root (from where project_generator was run). Otherwise, will use specified yaml record, which brings some flexibility.
The enviroment settings for building projects (if just export, don't need to care about them) are now set by default. To override them, define them in the main record file.

An example:
{% highlight ruby %}
projects:
    my_blink:
      - here yaml records for blinky

settings:
    uvision:
        - path to uvision installation
    iar:
        - path to IAR installation
{% endhighlight %}

No more need to clone the project generator repository (you still can and just install it via setup.py). The [mbed example project](https://github.com/0xc0170/project_generator_mbed_examples) how to use this project generator was updated, so you can test how does it work.

I am going to update wiki pages for project generator, to be up to the date with the v0.3. What I would like to look at in the next weeks, to expand MCU and boards definitions, minimize tools specific settings (boards was one of it), write tests, expand tools by some other new IDEs, like emblocks. Add a new example, simple baremetal demo, because that mbed is good for testing as it has specific configuration for each tool, might be difficult to start with.
