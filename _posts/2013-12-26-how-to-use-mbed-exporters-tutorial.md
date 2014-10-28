---
layout: post
title: "How to use mbed exporters (tutorial)"
date: 2013-12-26
comments: true
categories:
 - tutorial
 - mbed
---

I always created my own projects while I was developing offline with mbed. Fortunately, there are exporters which I assume are used in the online compiler. They are available in the mbed sources, in the folder /workspace_tools/export, Github mbed - export folder [github.com/mbedmicro/mbed]


These exporters support more platforms than online compiler, thus if you see a platform in the mbed sources but is not yet available online, this is your chance to start using your target. It requires IDE or at least a toolchain to compile it.


What targets are currently supported by exporters?
<pre>
    NUCLEO_F103RB
    KL25Z,
    LPC1347
    LPC11U24_301
    LPC4330_M4
    nRF51822,
    LPC11U35_401
    LPC810
    KL46Z
    LPC812
    KL05Z
    LPC1768
    K20D5M
    LPC4088
    LPC11C24
    MBED_MCU
    LPC1114
    LPC11U24,
    STM32F407
    LPC2368
</pre>

To see what options are available, invoke project.py, an output:

d:\Code\git_repo\github\mbed\workspace_tools>python project.py

<pre>
[ERROR] You have to specify one of the following tests:
[ 0] MBED_A1: Basic
[ 1] MBED_A2: semihost file system
[ 2] MBED_A3: C++ STL
[ 3] MBED_A4: I2C TMP102
[ 4] MBED_A5: DigitalIn DigitalOut
[ 5] MBED_A6: DigitalInOut
[ 6] MBED_A7: InterruptIn
[ 7] MBED_A8: Analog
[ 8] MBED_A9: Serial Echo at 115200
[ 9] MBED_A10: PortOut PortIn
[ 10] MBED_A11: PortInOut
[ 11] MBED_A12: SD File System
[ 12] MBED_A13: I2C MMA7660
[ 13] MBED_A14: I2C Master
[ 14] MBED_A15: I2C Slave
[ 15] MBED_A16: SPI Master
[ 16] MBED_A17: SPI Slave
[ 17] MBED_A18: Interrupt vector relocation
[ 18] MBED_A19: I2C EEPROM read/write test
[ 19] MBED_A20: I2C master/slave test
[ 20] MBED_A21: Call function before main (mbed_main)
[ 21] MBED_A22: SPIFI for LPC4088 (test 1)
[ 22] MBED_A23: SPIFI for LPC4088 (test 2)
[ 23] MBED_A24: Serial echo with RTS/CTS flow control
[ 24] BENCHMARK_1: Size (c environment)
[ 25] BENCHMARK_2: Size (float math)
[ 26] BENCHMARK_3: Size (printf)
[ 27] BENCHMARK_4: Size (mbed libs)
[ 28] BENCHMARK_5: Size (all)
[ 29] MBED_1: I2C SRF08
[ 30] MBED_2: stdio
[ 31] MBED_3: PortOut
[ 32] MBED_4: Sleep
[ 33] MBED_5: PWM
[ 34] MBED_6: SW Reset
[ 35] MBED_7: stdio benchmark
[ 36] MBED_8: SPI
[ 37] MBED_9: Sleep Timeout
[ 38] MBED_10: Hello World
[ 39] MBED_11: Ticker
[ 40] MBED_12: C++
[ 41] MBED_13: Heap & Stack
[ 42] MBED_14: Serial Interrupt
[ 43] MBED_15: RPC
[ 44] MBED_16: RTC
[ 45] MBED_17: Serial Interrupt 2
[ 46] MBED_18: Local FS Directory
[ 47] MBED_19: SD FS Directory
[ 48] MBED_20: InterruptIn 2
[ 49] MBED_21: freopen Stream
[ 50] MBED_22: Semihost
[ 51] MBED_23: Ticker 2
[ 52] MBED_24: Timeout
[ 53] MBED_25: Time us
[ 54] MBED_26: Integer constant division
[ 55] MBED_27: SPI ADXL345
[ 56] MBED_28: Interrupt chaining (InterruptManager)
[ 57] MBED_29: CAN network test
[ 58] MBED_30: CAN network test using interrupts
[ 59] MBED_31: PWM LED test
[ 60] CMSIS_RTOS_1: Basic
[ 61] CMSIS_RTOS_2: Mutex
[ 62] CMSIS_RTOS_3: Semaphore
[ 63] CMSIS_RTOS_4: Signals
[ 64] CMSIS_RTOS_5: Queue
[ 65] CMSIS_RTOS_6: Mail
[ 66] CMSIS_RTOS_7: Timer
[ 67] CMSIS_RTOS_8: ISR
[ 68] RTOS_1: Basic
[ 69] RTOS_2: Mutex
[ 70] RTOS_3: Semaphore
[ 71] RTOS_4: Signals
[ 72] RTOS_5: Queue
[ 73] RTOS_6: Mail
[ 74] RTOS_7: Timer
[ 75] RTOS_8: ISR
[ 76] RTOS_9: File
[ 77] NET_1: TCP client hello world
[ 78] NET_2: UDP client hello world
[ 79] NET_3: TCP echo server
[ 80] NET_4: TCP echo client
[ 81] NET_5: UDP echo server
[ 82] NET_6: UDP echo client
[ 83] NET_7: HTTP client
[ 84] NET_8: NTP client
[ 85] NET_9: Multicast Send
[ 86] NET_10: Multicast Receive
[ 87] NET_11: Broadcast Send
[ 88] NET_12: Broadcast Receive
[ 89] NET_13: TCP client echo loop
[ 90] UB_1: u-blox USB modem: HTTP client
[ 91] UB_2: u-blox USB modem: SMS test
[ 92] USB_1: Mouse
[ 93] USB_2: Keyboard
[ 94] USB_3: Mouse_Keyboard
[ 95] USB_4: Serial Port
[ 96] USB_5: Generic HID
[ 97] USB_6: MIDI
[ 98] USB_7: AUDIO
[ 99] CMSIS_DSP_1: FIR
[100] DSP_1: FIR
[101] KL25Z_1: LPTMR
[102] KL25Z_2: PIT
[103] KL25Z_3: TSI Touch Sensor
[104] KL25Z_4: RTC
[105] KL25Z_5: MMA8451Q accelerometer
[106] EXAMPLE_1: /dev/null
[107] EXAMPLE_2: FS + RTOS


Usage: project.py [options]

Options:
-h, --help show this help message and exit
-m MCU, --mcu=MCU generate project for the given MCU (NUCLEO_F103RB, KL25Z,
LPC1347, LPC11U24_301, LPC4330_M4, nRF51822,
LPC11U35_401, LPC810, KL46Z, LPC812, KL05Z, LPC1768,
K20D5M, LPC4088, LPC11C24, MBED_MCU, LPC1114, LPC11U24,
STM32F407, LPC2368)
-p PROGRAM The index of the desired test program: [0-107]
-i IDE The target IDE: ['ds5_5', 'gcc_arm', 'codered',
'codesourcery', 'uvision', 'iar']
-b Use the mbed library build, instead of the sources
</pre>


The output provides all information which we need to build a project. As I pushed today K20D5M target to mbed repository, I'll take that as an example how to start with mbed target which is not yet supported in the mbed compiler.
If you don't have prebuilt mbed sources for your target, don't use -b option (you can use it if you have built your target previously, then it creates the mbed library, same output as from the online compiler exporter). If you have not built target sources, use -b option, error is shown.



The very first application we can build is Hello world ([ 38] MBED_10: Hello World) To build it for GCC ARM, invoke:

python project.py -m K20D5M -p 38 -i gcc_arm

If you receive an error which contains jinja2, that means the projects generators require jinja2 package, please add it to your python installation. Easy install can help you, for more help, a procedure Jinja2 windows - how to install [forums.udacity.com/questions](http://forums.udacity.com/questions/6014880/how-to-install-jinja2-under-windows-for-newbies-like-me-)


The output should be many compiled files, at the end [OK]. In the mbed root directory, there's should be a new folder build. Inside in the path build/export/workspace are sources which were copied there by an exporter. In the build/export folder, should be located an archive MBED_10_GCC_ARM_K20D5M.zip
This archive contains the exported application, unzip it , invoke make command to build Hello world application.
