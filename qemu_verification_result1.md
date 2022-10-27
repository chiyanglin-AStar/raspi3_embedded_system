# Qemu verification 


## method 1
qemu-system-aarch64 -M raspi3 -kernel kernel8.img -nographic

### method 1 result :

01_bareminimum (master) $ qemu-system-aarch64 -M raspi3 -kernel kernel8.img -nographic
qemu-system-aarch64: terminating on signal 15 from pid 20383 ()

02_multicorec (master) $ qemu-system-aarch64 -M raspi3 -kernel kernel8.img -nographic
qemu-system-aarch64: terminating on signal 15 from pid 20846 ()

03_uart1 (master) $ qemu-system-aarch64 -M raspi3 -kernel kernel8.img -nographic
qemu-system-aarch64: terminating on signal 15 from pid 21167 ()

04_mailboxes (master) $ qemu-system-aarch64 -M raspi3 -kernel kernel8.img -nographic
qemu-system-aarch64: terminating on signal 15 from pid 21420 ()

05_uart0 (master) $ qemu-system-aarch64 -M raspi3 -kernel kernel8.img -nographic
My serial number is: 0000000000000000
qemu-system-aarch64: terminating on signal 15 from pid 21754 ()

06_random (master) $ qemu-system-aarch64 -M raspi3 -kernel kernel8.img -nographic
Here goes a random number: 1E11C173
qemu-system-aarch64: terminating on signal 15 from pid 21981 ()

07_delays (master) $ qemu-system-aarch64 -M raspi3 -kernel kernel8.img -nographic
Waiting 1000000 CPU cycles (ARM CPU): OK
Waiting 1000000 microsec (ARM CPU): OK
Waiting 1000000 microsec (BCM System Timer): OK
qemu-system-aarch64: terminating on signal 15 from pid 22208 ()

08_power (master) $ qemu-system-aarch64 -M raspi3 -kernel kernel8.img -nographic
 1 - power off
 2 - reset
Choose one: 2

 1 - power off
 2 - reset
Choose one: 1

Choose one: qemu-system-aarch64: terminating on signal 15 from pid 22511 ()

09_framebuffer (master) $ qemu-system-aarch64 -M raspi3 -kernel kernel8.img -nographic
qemu-system-aarch64: terminating on signal 15 from pid 22789 ()

0A_pcscreenfont (master) $ qemu-system-aarch64 -M raspi3 -kernel kernel8.img -nographic
qemu-system-aarch64: terminating on signal 15 from pid 24449 ()

0B_readsector (master) $ qemu-system-aarch64 -M raspi3 -kernel kernel8.img -nographic
EMMC: GPIO set up
EMMC: reset OK
sd_clk divisor 00000068, shift 00000006
EMMC: Sending command 00000000 arg 00000000
EMMC: Sending command 08020000 arg 000001AA
ERROR: failed to send EMMC command

0D_readfile (master) $ qemu-system-aarch64 -M raspi3 -kernel kernel8.img -nographic
EMMC: GPIO set up
EMMC: reset OK
sd_clk divisor 00000068, shift 00000006
EMMC: Sending command 00000000 arg 00000000
EMMC: Sending command 08020000 arg 000001AA
ERROR: failed to send EMMC command
qemu-system-aarch64: terminating on signal 15 from pid 25212 ()

0E_initrd (master) $ qemu-system-aarch64 -M raspi3 -kernel kernel8.img -nographic
Type     Offset   Size     Access rights        Filename
regular  00080BF0 00000C03 0000644 bzt.users    OLVASSEL.md
regular  00081BF0 00000A3F 0000644 bzt.users    README.md
regular  000829F0 00000A0C 0000644 bzt.users    delays.c
regular  000837F0 00001470 0000644 bzt.users    initrd.c
regular  00084FF0 000005D0 0000644 bzt.users    main.c
regular  000857F0 00000A0E 0000644 bzt.users    mbox.c
regular  000865F0 000011D8 0000644 bzt.users    uart.c
regular  000879F0 000004F5 0000644 bzt.users    delays.h
regular  000881F0 000009B4 0000644 bzt.users    gpio.h
regular  00088DF0 0000048B 0000644 bzt.users    initrd.h
regular  000895F0 0000066A 0000644 bzt.users    mbox.h
regular  00089FF0 00000505 0000644 bzt.users    uart.h
qemu-system-aarch64: terminating on signal 15 from pid 25451 ()

0F_executionlevel (master) $ qemu-system-aarch64 -M raspi3 -kernel kernel8.img -nographic
Current EL is: 00000001
qemu-system-aarch64: terminating on signal 15 from pid 25726 ()

10_virtualmemory (master) $ qemu-system-aarch64 -M raspi3 -kernel kernel8.img -nographic
Writing through identity mapped MMIO.
Writing through MMIO mapped in higher half!
qemu-system-aarch64: terminating on signal 15 from pid 23040 ()

11_exceptions (master) $ qemu-system-aarch64 -M raspi3 -kernel kernel8.img -nographic
Synchronous: Data abort, same EL, Translation fault at level 2:
  ESR_EL1 0000000096000006 ELR_EL1 0000000000080D5C
 SPSR_EL1 00000000200003C4 FAR_EL1 FFFFFFFFFF000000
qemu-system-aarch64: terminating on signal 15 from pid 23255 ()

12_printf (master) $ qemu-system-aarch64 -M raspi3 -kernel kernel8.img -nographic
Hello World!
This is character 'A', a hex number: 7FFF and in decimal: 32767
Padding test: '00007FFF', '    -123'
qemu-system-aarch64: terminating on signal 15 from pid 23458 ()

13_debugger (master) $ qemu-system-aarch64 -M raspi3 -kernel kernel8.img -nographic
Synchronous: Breakpoint instruction
> quit 
ERROR: unknown command.

14_raspbootin64 (master) $ qemu-system-aarch64 -M raspi3 -kernel kernel8.img -nographic
RBIN64
qemu-system-aarch64: terminating on signal 15 from pid 23971 ()

15_writesector (master) $ qemu-system-aarch64 -M raspi3 -kernel kernel8.img -nographic
EMMC: GPIO set up
EMMC: reset OK
sd_clk divisor 00000068, shift 00000006
EMMC: Sending command 00000000 arg 00000000
EMMC: Sending command 08020000 arg 000001AA
ERROR: failed to send EMMC command
qemu-system-aarch64: terminating on signal 15 from pid 24210 ()

## method 2 
qemu-system-aarch64 -M raspi3 -kernel kernel8.img -nographic -serial file:uart0 -serial file:uart1

### method 2 result :

## method 3 
qemu-system-aarch64 -m 128 -M raspi3 -serial null -serial mon:stdio -nographic -kernel build/kernel8.elf

### method 3 result :