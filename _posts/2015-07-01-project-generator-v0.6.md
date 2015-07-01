---
layout: post
title: "project generator v0.6 "
date: 2015-07-01
comments: true
categories:
 - python
---

It's time to bring some update about pgen. The last blog post was about v0.4. The latest v0.6 was release a week ago and brought a lot of changes. It took 2 months to make it complete with all features which were planned.

What commands does pgen v0.6 provide?

{% highlight ruby %}
positional arguments:
  {flash,list,update,init,export,build,clean}
                        commands
    flash               Flash a project
    list                List all projects
    update              Update definitions source repository
    init                Create a project record
    export              Export a project record
    build               Build a project
    clean               Clean generated projects
{% endhighlight %}

There were lot of breaking changes introduced. The most important is introducing templates for tools. It's basically a project which a user creates (IDE project) and uses as a template - settings are used and pgen data added and a new project generated. This allows a user not to learn anything new about tools they use, neither about YAML specific syntax like it used to be. If I have a project which I know it works in IAR, I can use this project (.ewp file) as a template.

We unified a bit yaml syntax. pgen was using like source_files_c, cpp or source_files_lib. All now belongs to sources. Include_paths were renamed to includes.

{% highlight ruby %}
common:
  sources:
    - file.c
    - object.obj
    - mylib.lib
    - sources # all c/cpp/obj/ar files are used within this folder (does not walk through dirs)
  includes:
    - header.h
    = path/folder #include all files withing a folder (does not walk through dirs)
{% endhighlight %}

Many new keywords were introduced, like debugger, tools_supported, template, sources, includes. This is an example from the mbed example repository, where this new keywords are shown

{% highlight ruby %}
common:
    # Output - exe or lib
    # output:
    #     - lib
    # Tools supported by this project - optional
    tools_supported:
        - iar_arm
        - make_gcc_arm
        - coide
        - uvision
    # Choose a debugger
    # debugger:
    #     - j-link
    target:
        - mbed-lpc1768
    includes:
        - examples/blinky
    sources:
        - examples/blinky/main.cpp
    macros:
        - TARGET_LPC1768
        - TARGET_M3
        - TARGET_NXP
        - __CORTEX_M3
        - __MBED__=1
tools_specific:
    uvision:
      template:
        - path/mytemplate.uvproj
{% endhighlight %}

One neat feature is that pgen can copy all files to the exported directory. This could be useful for using pgen within IDE.

Init command can create a valid project file from a repository. The aim is that any project can be ported to pgen.

Pgen is becoming smarter slowly. There's lot of ideas around this new features, more to come. If you are interested, check out pgen repository [project_generator github](https://github.com/project-generator/project_generator).
