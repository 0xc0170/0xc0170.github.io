---
layout: post
title: "project generator v0.4 - new features"
date: 2015-03-19
comments: true
categories:
 - python
---

There was an issue created for project generator, to eliminate specific settings in the records. There are various settings, different for each tool, and I wanted to cover 100 percent of each tool, without implementing a specific method for each one.

I started looking at how to make it easier for any project to use project_generator. It started by defining new boards definitions, which I described a month ago here on my page. The idea I started with was to create init command, which would generate a record for a project. It is time consuming to write all by typing, each file plus folders. This init command opened a new ways how to make it simplier, why not to include entire folder of sources?

There will be 4 main commands - init , export , list and clean. It used to be everything under the export. Here's the help printed:

{% highlight ruby %}
usage: project_generator-script.py [-h] [-v] [-q] [--version]
                                   {init,export,list,clean} ...

positional arguments:
  {init,export,list,clean}
                        commands
    init                Create a project record
    export              Export a project record
    list                List all projects
    clean               Clean generated projects
{% endhighlight %}

Init creates a record for selected folder. I have been testing it with a sample baremetal demo I created for twr-k20 gcc. I had to write my own makefile to be able to compile and link it. This time all it is needed, to run project_generator init project_folder, create projects.yaml file to include this project record. And exporting should be possible, as project_generator -p twr-k20 -t make_gcc_arm.

This is how the simple project record looks like:
{% highlight ruby %}
common:
  board:
  - twr-k20
  include_paths:
  - \gpio_demo_twrk20d72
  - \gpio_demo_twrk20d72\common
  - \gpio_demo_twrk20d72\cpu
  - \gpio_demo_twrk20d72\cpu\headers
  linker_file:
  - \gpio_demo_twrk20d72\k20x256_flash.ld
  source_files:
  - \gpio_demo_twrk20d72
  - \gpio_demo_twrk20d72\cpu
{% endhighlight %}

There's currently open a pull request, I am testing and trying to improve things. It should land soon.
