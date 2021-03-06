WARNING!!!!!!

This was the original configuration The port to nuttx_next''s
upstream 73331bded77a7952c79dc3fdcf36762c8b769424 at the time of
this writting was dpen blindly. 

NO Time has been spent validating the current degconfig
The information below is provided for refernece if the board
needs to be resurrected

WARNING!!!!!!


############################################################################
# configs/mavstation/nsh/defconfig
#
#   Copyright (C) 2009-2012 Gregory Nutt. All rights reserved.
#   Author: Gregory Nutt <gnutt@nuttx.org>
#
# Redistribution and use in source and binary forms, with or without
# modification, are permitted provided that the following conditions
# are met:
#
# 1. Redistributions of source code must retain the above copyright
#    notice, this list of conditions and the following disclaimer.
# 2. Redistributions in binary form must reproduce the above copyright
#    notice, this list of conditions and the following disclaimer in
#    the documentation and/or other materials provided with the
#    distribution.
# 3. Neither the name NuttX nor the names of its contributors may be
#    used to endorse or promote products derived from this software
#    without specific prior written permission.
#
# THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS
# "AS IS" AND ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT
# LIMITED TO, THE IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS
# FOR A PARTICULAR PURPOSE ARE DISCLAIMED. IN NO EVENT SHALL THE
# COPYRIGHT OWNER OR CONTRIBUTORS BE LIABLE FOR ANY DIRECT, INDIRECT,
# INCIDENTAL, SPECIAL, EXEMPLARY, OR CONSEQUENTIAL DAMAGES (INCLUDING,
# BUT NOT LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR SERVICES; LOSS
# OF USE, DATA, OR PROFITS; OR BUSINESS INTERRUPTION) HOWEVER CAUSED
# AND ON ANY THEORY OF LIABILITY, WHETHER IN CONTRACT, STRICT
# LIABILITY, OR TORT (INCLUDING NEGLIGENCE OR OTHERWISE) ARISING IN
# ANY WAY OUT OF THE USE OF THIS SOFTWARE, EVEN IF ADVISED OF THE
# POSSIBILITY OF SUCH DAMAGE.
#
############################################################################
#
# architecture selection
#
# CONFIG_ARCH - identifies the arch subdirectory and, hence, the
#   processor architecture.
# CONFIG_ARCH_family - for use in C code.  This identifies the
#   particular chip family that the architecture is implemented
#   in.
# CONFIG_ARCH_architecture - for use in C code.  This identifies the
#   specific architecture within the chip familyl.
# CONFIG_ARCH_CHIP - Identifies the arch/*/chip subdirectory
# CONFIG_ARCH_CHIP_name - For use in C code
# CONFIG_ARCH_BOARD - identifies the configs subdirectory and, hence,
#   the board that supports the particular chip or SoC.
# CONFIG_ARCH_BOARD_name - for use in C code
# CONFIG_ENDIAN_BIG - define if big endian (default is little endian)
# CONFIG_BOARD_LOOPSPERMSEC - for delay loops
# CONFIG_DRAM_SIZE - Describes the installed DRAM.
# CONFIG_DRAM_START - The start address of DRAM (physical)
# CONFIG_DRAM_END - Last address+1 of installed RAM
# CONFIG_ARCH_IRQPRIO - The ST32F100CB supports interrupt prioritization
# CONFIG_ARCH_INTERRUPTSTACK - This architecture supports an interrupt
#   stack. If defined, this symbol is the size of the interrupt
#   stack in bytes.  If not defined, the user task stacks will be
#   used during interrupt handling.
# CONFIG_ARCH_STACKDUMP - Do stack dumps after assertions
# CONFIG_ARCH_BOOTLOADER - Set if you are using a bootloader.
# CONFIG_ARCH_LEDS -  Use LEDs to show state. Unique to board architecture.
# CONFIG_ARCH_BUTTONS -  Enable support for buttons. Unique to board architecture.
# CONFIG_ARCH_CALIBRATION - Enables some build in instrumentation that
#   cause a 100 second delay during boot-up.  This 100 second delay
#   serves no purpose other than it allows you to calibrate
#   CONFIG_BOARD_LOOPSPERMSEC.  You simply use a stop watch to measure
#   the 100 second delay then adjust CONFIG_BOARD_LOOPSPERMSEC until
#   the delay actually is 100 seconds.
# CONFIG_ARCH_DMA - Support DMA initialization
#
CONFIG_ARCH="arm"
CONFIG_ARCH_ARM=y
CONFIG_ARCH_CORTEXM3=y
CONFIG_ARCH_CHIP_STM32=y
CONFIG_ARCH_CORTEXM3=y
CONFIG_ARCH_FAMILY="armv7-m"
CONFIG_ARCH_CHIP="stm32"
CONFIG_ARMV7M_USEBASEPRI=y
CONFIG_ARCH_HAVE_CMNVECTOR=y
CONFIG_ARMV7M_CMNVECTOR=y

CONFIG_ARCH_CHIP_STM32F102CB=y
CONFIG_ARCH_BOARD=mavstation
CONFIG_ARCH_BOARD_MAVSTATION=y
CONFIG_BOARD_LOOPSPERMSEC=24000
CONFIG_RAM_SIZE=16000
CONFIG_RAM_START=0x20000000
CONFIG_RAM_END=(CONFIG_RAM_START+CONFIG_RAM_SIZE)
CONFIG_ARCH_HAVE_INTERRUPTSTACK=y
CONFIG_ARCH_INTERRUPTSTACK=340
CONFIG_ARCH_IRQPRIO=y
CONFIG_ARCH_INTERRUPTSTACK=n
CONFIG_ARCH_STACKDUMP=y
CONFIG_ARCH_BOOTLOADER=y
CONFIG_ARCH_LEDS=n
CONFIG_ARCH_BUTTONS=y
CONFIG_ARCH_CALIBRATION=n
CONFIG_ARCH_DMA=n
#CONFIG_SERIAL_TERMIOS=y

CONFIG_ARMV7M_TOOLCHAIN_GNU_EABIL=y

#
# JTAG Enable settings (by default JTAG-DP and SW-DP are disabled):
#
#   CONFIG_STM32_DFU - Use the DFU bootloader, not JTAG
#
# JTAG Enable options:
#
#   CONFIG_STM32_JTAG_FULL_ENABLE - Enables full SWJ (JTAG-DP + SW-DP)
#   CONFIG_STM32_JTAG_NOJNTRST_ENABLE - Enables full SWJ (JTAG-DP + SW-DP)
#     but without JNTRST.
#   CONFIG_STM32_JTAG_SW_ENABLE - Set JTAG-DP disabled and SW-DP enabled
#
CONFIG_STM32_DFU=n
CONFIG_STM32_JTAG_FULL_ENABLE=y
CONFIG_STM32_JTAG_NOJNTRST_ENABLE=n
CONFIG_STM32_JTAG_SW_ENABLE=n

#
# Individual subsystems can be enabled:
# AHB: 
CONFIG_STM32_DMA1=n
CONFIG_STM32_DMA2=n
CONFIG_STM32_CRC=n
# APB1:
# Timers 2 and 4 are owned by the PWM driver
CONFIG_STM32_TIM2=n
CONFIG_STM32_TIM4=n
CONFIG_STM32_WWDG=n
CONFIG_STM32_SPI2=n
CONFIG_STM32_USART2=y
CONFIG_STM32_USART3=n
CONFIG_STM32_I2C1=y
CONFIG_STM32_I2C2=y
CONFIG_STM32_BKP=n
CONFIG_STM32_PWR=n
CONFIG_STM32_DAC=n
# APB2:
CONFIG_STM32_ADC1=y
CONFIG_STM32_ADC2=n
# TIM3 is owned by the HRT
CONFIG_STM32_TIM3=n
CONFIG_STM32_SPI1=n
CONFIG_STM32_TIM8=n
CONFIG_STM32_USART1=y
CONFIG_STM32_ADC3=n
CONFIG_STM32_USB=y

#
# Timer and I2C devices may need to the following to force power to be applied:
#
#CONFIG_STM32_FORCEPOWER=y

#
# STM32F100 specific serial device driver settings
#
# CONFIG_USARTn_SERIAL_CONSOLE - selects the USARTn for the
#   console and ttys0 (default is the USART1).
# CONFIG_USARTn_RXBUFSIZE - Characters are buffered as received.
#   This specific the size of the receive buffer
# CONFIG_USARTn_TXBUFSIZE - Characters are buffered before
#   being sent.  This specific the size of the transmit buffer
# CONFIG_USARTn_BAUD - The configure BAUD of the UART.  Must be
# CONFIG_USARTn_BITS - The number of bits.  Must be either 7 or 8.
# CONFIG_USARTn_PARTIY - 0=no parity, 1=odd parity, 2=even parity
# CONFIG_USARTn_2STOP - Two stop bits
#
CONFIG_USART1_SERIAL_CONSOLE=y
CONFIG_USART2_SERIAL_CONSOLE=n
CONFIG_USART3_SERIAL_CONSOLE=n

CONFIG_USART1_TXBUFSIZE=64
CONFIG_USART2_TXBUFSIZE=64
CONFIG_USART3_TXBUFSIZE=64

CONFIG_USART1_RXBUFSIZE=64
CONFIG_USART2_RXBUFSIZE=64
CONFIG_USART3_RXBUFSIZE=64

CONFIG_USART1_BAUD=57600
CONFIG_USART2_BAUD=115200
CONFIG_USART3_BAUD=115200

CONFIG_USART1_BITS=8
CONFIG_USART2_BITS=8
CONFIG_USART3_BITS=8

CONFIG_USART1_PARITY=0
CONFIG_USART2_PARITY=0
CONFIG_USART3_PARITY=0

CONFIG_USART1_2STOP=0
CONFIG_USART2_2STOP=0
CONFIG_USART3_2STOP=0

CONFIG_USBDEV=y
#CONFIG_USART1_RXDMA=y
#SERIAL_HAVE_CONSOLE_DMA=y

#
# USB Device Controller Driver Options
#
# CONFIG_USBDEV_ISOCHRONOUS is not set
# CONFIG_USBDEV_DUALSPEED is not set
CONFIG_USBDEV_SELFPOWERED=y
# CONFIG_USBDEV_BUSPOWERED is not set
CONFIG_USBDEV_MAXPOWER=100
# CONFIG_USBDEV_DMA is not set
CONFIG_USBDEV_TRACE=y
CONFIG_USBDEV_TRACE_NRECORDS=32
# CONFIG_USBDEV_TRACE_STRINGS is not set

#
# USB CDC/ACM Device Commands
#
CONFIG_SYSTEM_CDCACM=y
CONFIG_SYSTEM_CDCACM_DEVMINOR=0

#
# USB Device Class Driver Options
#
# CONFIG_USBDEV_COMPOSITE is not set
# CONFIG_PL2303 is not set
CONFIG_CDCACM=y
CONFIG_CDCACM_CONSOLE=n
CONFIG_CDCACM_EP0MAXPACKET=64
CONFIG_CDCACM_EPINTIN=1
CONFIG_CDCACM_EPINTIN_FSSIZE=64
CONFIG_CDCACM_EPINTIN_HSSIZE=64
CONFIG_CDCACM_EPBULKOUT=3
CONFIG_CDCACM_EPBULKOUT_FSSIZE=64
CONFIG_CDCACM_EPBULKOUT_HSSIZE=512
CONFIG_CDCACM_EPBULKIN=2
CONFIG_CDCACM_EPBULKIN_FSSIZE=64
CONFIG_CDCACM_EPBULKIN_HSSIZE=512
CONFIG_CDCACM_NWRREQS=4
CONFIG_CDCACM_NRDREQS=4
CONFIG_CDCACM_BULKIN_REQLEN=96
CONFIG_CDCACM_RXBUFSIZE=256
CONFIG_CDCACM_TXBUFSIZE=296
CONFIG_CDCACM_VENDORID=0x0525
CONFIG_CDCACM_PRODUCTID=0xa4a7
CONFIG_CDCACM_VENDORSTR="NuttX"
CONFIG_CDCACM_PRODUCTSTR="CDC/ACM Serial"

# PX4IO specific driver settings
#
# CONFIG_HRT_TIMER
#   Enables the high-resolution timer.  The board definition must
#   set HRT_TIMER and HRT_TIMER_CHANNEL to the timer and capture/
#   compare channels to be used.
# CONFIG_HRT_PPM
#   Enables R/C PPM input using the HRT.  The board definition must
#   set HRT_PPM_CHANNEL to the timer capture/compare channel to be
#   used, and define GPIO_PPM_IN to configure the appropriate timer
#   GPIO.
# CONFIG_PWM_SERVO
#   Enables the PWM servo driver.  The driver configuration must be
#   supplied by the board support at initialisation time.
#   Note that USART2 must be disabled on the PX4 board for this to
#   be available.
#
#
CONFIG_HRT_TIMER=y
CONFIG_HRT_PPM=n
CONFIG_PWM_SERVO=y

#
# General build options
#
# CONFIG_RRLOAD_BINARY - make the rrload binary format used with
#   BSPs from www.ridgerun.com using the tools/mkimage.sh script
# CONFIG_INTELHEX_BINARY - make the Intel HEX binary format
#   used with many different loaders using the GNU objcopy program
#   Should not be selected if you are not using the GNU toolchain.
# CONFIG_MOTOROLA_SREC - make the Motorola S-Record binary format
#   used with many different loaders using the GNU objcopy program
#   Should not be selected if you are not using the GNU toolchain.
# CONFIG_RAW_BINARY - make a raw binary format file used with many
#   different loaders using the GNU objcopy program.  This option
#   should not be selected if you are not using the GNU toolchain.
# CONFIG_HAVE_LIBM - toolchain supports libm.a
#
CONFIG_RRLOAD_BINARY=n
CONFIG_INTELHEX_BINARY=n
CONFIG_MOTOROLA_SREC=n
CONFIG_RAW_BINARY=y
CONFIG_HAVE_LIBM=n
CONFIG_BINFMT_DISABLE=n
CONFIG_FS_BINFS=y

#
# Examples
#
# CONFIG_EXAMPLES_BUTTONS is not set
# CONFIG_EXAMPLES_CAN is not set
# CONFIG_EXAMPLES_CONFIGDATA is not set
# CONFIG_EXAMPLES_CPUHOG is not set
# CONFIG_EXAMPLES_CXXTEST is not set
# CONFIG_EXAMPLES_DHCPD is not set
# CONFIG_EXAMPLES_ELF is not set
# CONFIG_EXAMPLES_FTPC is not set
# CONFIG_EXAMPLES_FTPD is not set
CONFIG_EXAMPLES_HELLO=y
# CONFIG_EXAMPLES_HELLOXX is not set
# CONFIG_EXAMPLES_JSON is not set
# CONFIG_EXAMPLES_HIDKBD is not set
# CONFIG_EXAMPLES_KEYPADTEST is not set
# CONFIG_EXAMPLES_IGMP is not set
# CONFIG_EXAMPLES_MM is not set
# CONFIG_EXAMPLES_MODBUS is not set
CONFIG_EXAMPLES_MOUNT=y
# CONFIG_EXAMPLES_MOUNT_BLOCKDEVICE is not set
CONFIG_EXAMPLES_MOUNT_NSECTORS=1024
CONFIG_EXAMPLES_MOUNT_SECTORSIZE=256
CONFIG_EXAMPLES_MOUNT_RAMDEVNO=0
# CONFIG_EXAMPLES_MTDPART is not set
# CONFIG_EXAMPLES_NRF24L01TERM is not set
CONFIG_EXAMPLES_NSH=y
# CONFIG_EXAMPLES_NSH_CXXINITIALIZE is not set
# CONFIG_EXAMPLES_NULL is not set
# CONFIG_EXAMPLES_NX is not set
# CONFIG_EXAMPLES_NXTERM is not set
# CONFIG_EXAMPLES_NXFFS is not set
# CONFIG_EXAMPLES_NXFLAT is not set
# CONFIG_EXAMPLES_NXHELLO is not set
# CONFIG_EXAMPLES_NXIMAGE is not set
# CONFIG_EXAMPLES_NXLINES is not set
# CONFIG_EXAMPLES_NXTEXT is not set
# CONFIG_EXAMPLES_OSTEST is not set
# CONFIG_EXAMPLES_PIPE is not set
# CONFIG_EXAMPLES_POSIXSPAWN is not set
# CONFIG_EXAMPLES_QENCODER is not set
# CONFIG_EXAMPLES_RGMP is not set
# CONFIG_EXAMPLES_ROMFS is not set
# CONFIG_EXAMPLES_SENDMAIL is not set
# CONFIG_EXAMPLES_SERIALBLASTER is not set
# CONFIG_EXAMPLES_SERIALRX is not set
# CONFIG_EXAMPLES_SERLOOP is not set
# CONFIG_EXAMPLES_SLCD is not set
# CONFIG_EXAMPLES_SMART_TEST is not set
# CONFIG_EXAMPLES_SMART is not set
# CONFIG_EXAMPLES_TCPECHO is not set
# CONFIG_EXAMPLES_TELNETD is not set
# CONFIG_EXAMPLES_THTTPD is not set
# CONFIG_EXAMPLES_TIFF is not set
# CONFIG_EXAMPLES_TOUCHSCREEN is not set
# CONFIG_EXAMPLES_WEBSERVER is not set
# CONFIG_EXAMPLES_USBSERIAL is not set
# CONFIG_EXAMPLES_USBTERM is not set
# CONFIG_EXAMPLES_WATCHDOG is not set

#
# General OS setup
#
# CONFIG_APPS_DIR - Identifies the relative path to the directory
#   that builds the application to link with NuttX.  Default: ../apps
# CONFIG_DEBUG_FEATURES - enables built-in debug options
# CONFIG_DEBUG_VERBOSE - enables verbose debug output
# CONFIG_DEBUG_SYMBOLS - build without optimization and with
#   debug symbols (needed for use with a debugger).
# CONFIG_HAVE_CXX - Enable support for C++
# CONFIG_HAVE_CXXINITIALIZE - The platform-specific logic includes support
#   for initialization of static C++ instances for this architecture
#   and for the selected toolchain (via up_cxxinitialize()).
# CONFIG_MM_REGIONS - If the architecture includes multiple
#   regions of memory to allocate from, this specifies the
#   number of memory regions that the memory manager must
#   handle and enables the API mm_addregion(start, end);
# CONFIG_ARCH_LOWPUTC - architecture supports low-level, boot
#   time console output
# CONFIG_MSEC_PER_TICK - The default system timer is 100Hz
#   or MSEC_PER_TICK=10.  This setting may be defined to
#   inform NuttX that the processor hardware is providing
#   system timer interrupts at some interrupt interval other
#   than 10 msec.
# CONFIG_RR_INTERVAL - The round robin timeslice will be set
#   this number of milliseconds;  Round robin scheduling can
#   be disabled by setting this value to zero.
# CONFIG_SCHED_INSTRUMENTATION - enables instrumentation in 
#   scheduler to monitor system performance
# CONFIG_TASK_NAME_SIZE - Spcifies that maximum size of a
#   task name to save in the TCB.  Useful if scheduler
#   instrumentation is selected.  Set to zero to disable.
# CONFIG_START_YEAR, CONFIG_START_MONTH, CONFIG_START_DAY -
#   Used to initialize the internal time logic.
# CONFIG_GREGORIAN_TIME - Enables Gregorian time conversions.
#   You would only need this if you are concerned about accurate
#   time conversions in the past or in the distant future.
# CONFIG_JULIAN_TIME - Enables Julian time conversions. You
#   would only need this if you are concerned about accurate
#   time conversion in the distand past.  You must also define
#   CONFIG_GREGORIAN_TIME in order to use Julian time.
# CONFIG_DEV_CONSOLE - Set if architecture-specific logic
#   provides /dev/console.  Enables stdout, stderr, stdin.
# CONFIG_DEV_LOWCONSOLE - Use the simple, low-level serial console
#   driver (minimul support)
# CONFIG_MUTEX_TYPES: Set to enable support for recursive and
#   errorcheck mutexes. Enables pthread_mutexattr_settype().
# CONFIG_PRIORITY_INHERITANCE : Set to enable support for priority
#   inheritance on mutexes and semaphores. 
# CONFIG_SEM_PREALLOCHOLDERS: This setting is only used if priority
#   inheritance is enabled.  It defines the maximum number of
#   different threads (minus one) that can take counts on a
#   semaphore with priority inheritance support.  This may be 
#   set to zero if priority inheritance is disabled OR if you
#   are only using semaphores as mutexes (only one holder) OR
#   if no more than two threads participate using a counting
#   semaphore.
# CONFIG_SEM_NNESTPRIO.  If priority inheritance is enabled,
#   then this setting is the maximum number of higher priority
#   threads (minus 1) than can be waiting for another thread
#   to release a count on a semaphore.  This value may be set
#   to zero if no more than one thread is expected to wait for
#   a semaphore.
# CONFIG_FDCLONE_DISABLE. Disable cloning of all file descriptors
#   by task_create() when a new task is started.  If set, all
#   files/drivers will appear to be closed in the new task.
# CONFIG_FDCLONE_STDIO. Disable cloning of all but the first
#   three file descriptors (stdin, stdout, stderr) by task_create()
#   when a new task is started. If set, all files/drivers will
#   appear to be closed in the new task except for stdin, stdout,
#   and stderr.
# CONFIG_SDCLONE_DISABLE. Disable cloning of all socket
#   desciptors by task_create() when a new task is started. If
#   set, all sockets will appear to be closed in the new task.
# CONFIG_NXFLAT. Enable support for the NXFLAT binary format.
#  This format will support execution of NuttX binaries located
#  in a ROMFS filesystem (see examples/nxflat).
# CONFIG_SCHED_WORKQUEUE.  Create a dedicated "worker" thread to
#  handle delayed processing from interrupt handlers.  This feature
#  is required for some drivers but, if there are not complaints,
#  can be safely disabled.  The worker thread also performs
#  garbage collection -- completing any delayed memory deallocations
#  from interrupt handlers.  If the worker thread is disabled,
#  then that clean will be performed by the IDLE thread instead
#  (which runs at the lowest of priority and may not be appropriate
#  if memory reclamation is of high priority).  If CONFIG_SCHED_WORKQUEUE
#  is enabled, then the following options can also be used:
# CONFIG_SCHED_WORKPRIORITY - The execution priority of the worker
#  thread.  Default: 50
# CONFIG_SCHED_WORKPERIOD - How often the worker thread checks for
#  work in units of microseconds.  Default: 50*1000 (50 MS).
# CONFIG_SCHED_WORKSTACKSIZE - The stack size allocated for the worker
#  thread.  Default: CONFIG_IDLETHREAD_STACKSIZE.
# CONFIG_SIG_SIGWORK - The signal number that will be used to wake-up
#  the worker thread.  Default: 4
#
CONFIG_APPS_DIR="../apps"
CONFIG_ARCH_HAVE_STACKCHECK=y
CONFIG_STACK_COLORATION=y
CONFIG_ARCH_HAVE_HEAPCHECK=y
CONFIG_MSEC_PWER_TICK=1
CONFIG_DEBUG_FEATURES=n
CONFIG_DEBUG_VERBOSE=n
CONFIG_DEBUG_SYMBOLS=y
CONFIG_HAVE_CXX=y
CONFIG_HAVE_CXXINITIALIZE=y
CONFIG_ARCH_MATH_H=y
CONFIG_MM_REGIONS=1
CONFIG_MM_SMALL=y
CONFIG_ARCH_LOWPUTC=y
CONFIG_RR_INTERVAL=200
CONFIG_SCHED_INSTRUMENTATION=n
CONFIG_TASK_NAME_SIZE=8
CONFIG_START_YEAR=2009
CONFIG_START_MONTH=9
CONFIG_START_DAY=21
CONFIG_GREGORIAN_TIME=n
CONFIG_JULIAN_TIME=n
CONFIG_DEV_CONSOLE=y
CONFIG_DEV_LOWCONSOLE=n
CONFIG_MUTEX_TYPES=n
CONFIG_PRIORITY_INHERITANCE=n
CONFIG_SEM_PREALLOCHOLDERS=0
CONFIG_SEM_NNESTPRIO=0
CONFIG_FDCLONE_DISABLE=n
CONFIG_FDCLONE_STDIO=y
CONFIG_SDCLONE_DISABLE=y
CONFIG_NXFLAT=n
CONFIG_SCHED_WORKQUEUE=n
CONFIG_SCHED_WORKPRIORITY=50
CONFIG_SCHED_WORKPERIOD=(50*1000)
CONFIG_SCHED_WORKSTACKSIZE=512
CONFIG_SIG_SIGWORK=4

CONFIG_USER_ENTRYPOINT="nsh_main"
#
# The following can be used to disable categories of
# APIs supported by the OS.  If the compiler supports
# weak functions, then it should not be necessary to
# disable functions unless you want to restrict usage
# of those APIs.
#
# There are certain dependency relationships in these
# features.
#
# o mq_notify logic depends on signals to awaken tasks
#   waiting for queues to become full or empty.
# o pthread_condtimedwait() depends on signals to wake
#   up waiting tasks.
#
CONFIG_DISABLE_CLOCK=n
CONFIG_DISABLE_POSIX_TIMERS=y
CONFIG_DISABLE_PTHREAD=n
CONFIG_DISABLE_SIGNALS=n
CONFIG_DISABLE_MQUEUE=y
CONFIG_DISABLE_MOUNTPOINT=n
CONFIG_DISABLE_ENVIRON=n
CONFIG_DISABLE_POLL=n

#
# Misc libc settings
#
# CONFIG_NOPRINTF_FIELDWIDTH - sprintf-related logic is a
#   little smaller if we do not support fieldwidthes
#
CONFIG_NOPRINTF_FIELDWIDTH=n
CONFIG_C99_BOOL8=y

#
# Allow for architecture optimized implementations
#
# The architecture can provide optimized versions of the
# following to improve system performance
#
CONFIG_ARCH_MEMCPY=n
CONFIG_ARCH_MEMCMP=n
CONFIG_ARCH_MEMMOVE=n
CONFIG_ARCH_MEMSET=n
CONFIG_ARCH_STRCMP=n
CONFIG_ARCH_STRCPY=n
CONFIG_ARCH_STRNCPY=n
CONFIG_ARCH_STRLEN=n
CONFIG_ARCH_STRNLEN=n
CONFIG_ARCH_BZERO=n

#
# Sizes of configurable things (0 disables)
#
# CONFIG_MAX_TASKS - The maximum number of simultaneously
#   active tasks.  This value must be a power of two.
# CONFIG_MAX_TASK_ARGS - This controls the maximum number of
#   of parameters that a task may receive (i.e., maxmum value
#   of 'argc')
# CONFIG_NPTHREAD_KEYS - The number of items of thread-
#   specific data that can be retained
# CONFIG_NFILE_DESCRIPTORS - The maximum number of file
#   descriptors (one for each open)
# CONFIG_NFILE_STREAMS - The maximum number of streams that
#   can be fopen'ed
# CONFIG_NAME_MAX - The maximum size of a file name.
# CONFIG_STDIO_BUFFER_SIZE - Size of the buffer to allocate
#   on fopen. (Only if CONFIG_NFILE_STREAMS > 0)
# CONFIG_NUNGET_CHARS - Number of characters that can be
#   buffered by ungetc() (Only if CONFIG_NFILE_STREAMS > 0)
# CONFIG_PREALLOC_MQ_MSGS - The number of pre-allocated message
#   structures.  The system manages a pool of preallocated
#   message structures to minimize dynamic allocations
# CONFIG_MQ_MAXMSGSIZE - Message structures are allocated with
#   a fixed payload size given by this settin (does not include
#   other message structure overhead.
# CONFIG_MAX_WDOGPARMS - Maximum number of parameters that
#   can be passed to a watchdog handler
# CONFIG_PREALLOC_WDOGS - The number of pre-allocated watchdog
#   structures.  The system manages a pool of preallocated
#   watchdog structures to minimize dynamic allocations
# CONFIG_PREALLOC_TIMERS - The number of pre-allocated POSIX
#   timer structures.  The system manages a pool of preallocated
#   timer structures to minimize dynamic allocations.  Set to
#   zero for all dynamic allocations.
#
CONFIG_MAX_TASKS=4
CONFIG_MAX_TASK_ARGS=4
CONFIG_NPTHREAD_KEYS=2
CONFIG_NFILE_DESCRIPTORS=6
CONFIG_NFILE_STREAMS=4
CONFIG_NAME_MAX=32
CONFIG_STDIO_BUFFER_SIZE=64
#CONFIG_STDIO_LINEBUFFER=y
CONFIG_NUNGET_CHARS=2
CONFIG_PREALLOC_MQ_MSGS=1
CONFIG_MQ_MAXMSGSIZE=32
CONFIG_MAX_WDOGPARMS=2
CONFIG_PREALLOC_WDOGS=3
CONFIG_PREALLOC_TIMERS=1


#
# File Systems
#

#
# File system configuration
#
CONFIG_FS_ROMFS=y

#
# NSH Library
#
CONFIG_NSH_LIBRARY=y

#
# Settings for apps/nshlib
#
# CONFIG_NSH_BUILTIN_APPS - Support external registered,
#   "named" applications that can be executed from the NSH
#   command line (see apps/README.txt for more information).
# CONFIG_NSH_FILEIOSIZE - Size of a static I/O buffer
# CONFIG_NSH_STRERROR - Use strerror(errno)
# CONFIG_NSH_LINELEN - Maximum length of one command line
# CONFIG_NSH_NESTDEPTH - Max number of nested if-then[-else]-fi
# CONFIG_NSH_DISABLESCRIPT - Disable scripting support
# CONFIG_NSH_DISABLEBG - Disable background commands
# CONFIG_NSH_ROMFSETC - Use startup script in /etc
# CONFIG_NSH_CONSOLE - Use serial console front end
# CONFIG_NSH_TELNET - Use telnetd console front end
# CONFIG_NSH_ARCHINIT - Platform provides architecture
#   specific initialization (board_app_initialize()).
#
# If CONFIG_NSH_TELNET is selected:
# CONFIG_NSH_IOBUFFER_SIZE -- Telnetd I/O buffer size
# CONFIG_NSH_DHCPC - Obtain address using DHCP
# CONFIG_NSH_IPADDR - Provides static IP address
# CONFIG_NSH_DRIPADDR - Provides static router IP address
# CONFIG_NSH_NETMASK - Provides static network mask
# CONFIG_NSH_NOMAC - Use a bogus MAC address
#
# If CONFIG_NSH_ROMFSETC is selected:
# CONFIG_NSH_ROMFSMOUNTPT - ROMFS mountpoint
# CONFIG_NSH_INITSCRIPT - Relative path to init script
# CONFIG_NSH_ROMFSDEVNO - ROMFS RAM device minor
# CONFIG_NSH_ROMFSSECTSIZE - ROMF sector size
# CONFIG_NSH_FATDEVNO - FAT FS RAM device minor
# CONFIG_NSH_FATSECTSIZE - FAT FS sector size
# CONFIG_NSH_FATNSECTORS - FAT FS number of sectors
# CONFIG_NSH_FATMOUNTPT - FAT FS mountpoint
#
CONFIG_BUILTIN=y
CONFIG_NSH_BUILTIN_APPS=y
CONFIG_NSH_FILEIOSIZE=64
CONFIG_NSH_STRERROR=n
CONFIG_NSH_READLINE=y
CONFIG_NSH_LINELEN=64
CONFIG_NSH_CMDPARMS=y
CONFIG_NSH_MAXARGUMENTS=12
CONFIG_NSH_ARGCAT=y
CONFIG_NSH_NESTDEPTH=1
CONFIG_NSH_DISABLESCRIPT=n
CONFIG_NSH_DISABLEBG=n
CONFIG_NSH_ROMFSETC=n
CONFIG_NSH_CONSOLE=y
CONFIG_NSH_TELNET=n
CONFIG_NSH_ARCHINIT=n
CONFIG_NSH_IOBUFFER_SIZE=256
CONFIG_NSH_STACKSIZE=1024
CONFIG_NSH_DHCPC=n
CONFIG_NSH_NOMAC=n
CONFIG_NSH_IPADDR=(10<<24|0<<16|0<<8|2)
CONFIG_NSH_DRIPADDR=(10<<24|0<<16|0<<8|1)
CONFIG_NSH_NETMASK=(255<<24|255<<16|255<<8|0)
CONFIG_NSH_ROMFSETC=y
CONFIG_NSH_ROMFSMOUNTPT="/etc"
CONFIG_NSH_INITSCRIPT="init.d/rcS"
CONFIG_NSH_ROMFSDEVNO=0
CONFIG_NSH_ROMFSSECTSIZE=128
CONFIG_NSH_ARCHROMFS=y
CONFIG_FS_FAT=y
CONFIG_NSH_FATDEVNO=1
CONFIG_NSH_FATSECTSIZE=512
CONFIG_NSH_FATNSECTORS=1024
CONFIG_NSH_FATMOUNTPT=/tmp
CONFIG_NSH_DISABLE_MOUNT=n


CONFIG_I2C=y
# CONFIG_I2C_SLAVE is not set
CONFIG_I2C_TRANSFER=y
# CONFIG_I2C_WRITEREAD is not set
# CONFIG_I2C_POLLED is not set
# CONFIG_I2C_TRACE is not set
CONFIG_ARCH_HAVE_I2CRESET=y
CONFIG_I2C_RESET=y
CONFIG_SPI=y
CONFIG_SPI_EXCHANGE=y
CONFIG_WATCHDOG=y

#
# Architecture-specific NSH options
#
CONFIG_NSH_MMCSDSPIPORTNO=0
CONFIG_NSH_MMCSDSLOTNO=0
CONFIG_NSH_MMCSDMINOR=0

#
# readline()
#
CONFIG_SYSTEM_READLINE=y
CONFIG_READLINE_ECHO=y

#
# Stack and heap information
#
# CONFIG_BOOT_RUNFROMFLASH - Some configurations support XIP
#   operation from FLASH but must copy initialized .data sections to RAM.
#   (should also be =n for the STM3210E-EVAL which always runs from flash)
# CONFIG_BOOT_COPYTORAM -  Some configurations boot in FLASH
#   but copy themselves entirely into RAM for better performance.
# CONFIG_CUSTOM_STACK - The up_ implementation will handle
#   all stack operations outside of the nuttx model.
# CONFIG_STACK_POINTER - The initial stack pointer (arm7tdmi only)
# CONFIG_IDLETHREAD_STACKSIZE - The size of the initial stack.
#  This is the thread that (1) performs the inital boot of the system up
#  to the point where user_start() is spawned, and (2) there after is the
#  IDLE thread that executes only when there is no other thread ready to
#  run.
# CONFIG_USERMAIN_STACKSIZE - The size of the stack to allocate
#  for the main user thread that begins at the user_start() entry point.
# CONFIG_PTHREAD_STACK_MIN - Minimum pthread stack size
# CONFIG_PTHREAD_STACK_DEFAULT - Default pthread stack size
# CONFIG_HEAP_BASE - The beginning of the heap
# CONFIG_HEAP_SIZE - The size of the heap
#
CONFIG_BOOT_RUNFROMFLASH=y
CONFIG_BOOT_COPYTORAM=n
CONFIG_CUSTOM_STACK=n
CONFIG_STACK_POINTER=
CONFIG_IDLETHREAD_STACKSIZE=280
CONFIG_USERMAIN_STACKSIZE=1024
CONFIG_PTHREAD_STACK_MIN=256
CONFIG_PTHREAD_STACK_DEFAULT=340
CONFIG_HEAP_BASE=
CONFIG_HEAP_SIZE=
CONFIG_POSIX_SPAWN_PROXY_STACKSIZE=768
CONFIG_TASK_SPAWN_DEFAULT_STACKSIZE=768
CONFIG_BUILTIN_PROXY_STACKSIZE=768

