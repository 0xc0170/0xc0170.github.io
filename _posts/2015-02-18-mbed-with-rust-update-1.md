---
layout: post
title: "mbed with rust - update 1"
date: 2015-02-18
comments: true
categories:
 - rust
---

In the initial post about mbed and rust, there were couple of problems, I fixed some, some are still ongoing. What has been fixed?

The initial version completely ignored the _start (no C library was linked). I fixed this recently, the required C libraries are linked, to resolve the startup. This fixed wait() issue I had. It simplified the main source file. The main loop is:

{% highlight ruby %}
#[no_mangle]
pub fn main() {
    let mut led = DigitalOut::DigitalOut::new((1 << 12) | 22);
    unsafe {
        loop {
            led.write(1);
            wait(1.0);
            led.write(0);
            wait(1.0);
        }
    }
}
{% endhighlight %}

Now there's another issue, that's the predefined size of gpio structure (for mbed C HAL it's gpio_t), which is set to 4 bytes - K64F.

{% highlight ruby %}
pub struct DigitalOut {
    gpio : [u8; 4]
}
{% endhighlight %}

#### mbed C HAL alloc

To be able to replace this with the dynamic allocations, I created a new [C HAL generic layer](https://github.com/0xc0170/mbed-hal-alloc). This expands C HAL by new functions:

{% highlight ruby %}
analogin_t* analogin_allocate(void)
{
    return (analogin_t *)malloc(sizeof(analogin_t));
}

void analogin_deallocate(analogin_t *p)
{
    free(p);
}

size_t analogin_get_size(void)
{
    return sizeof(analogin_t);
}
{% endhighlight %}

This is an example from analogin C HAL. It extends the current C HAL by 3 functions per peripheral. To get a size of the object, which might be used if the allocation happens in the upper layer (rust or any other language). Or C HAL to handle the allocations/free. Therefore I added this functionality there. I tested this with this DigitalOut rust layer, to have only a pointer, and let C layer handle the allocation.

The blinky example uses modified K64F mbed library, as gpio_write and read are inline functions, thus not visible. I will create an issue for this, try to enforce that public C HAL functions should not be defined in a header file.
