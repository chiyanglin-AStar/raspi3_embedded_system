# Qemu verification 


## method 1
qemu-system-aarch64 -M raspi3 -kernel kernel8.img -nographic

### method 1 result : (please result 1)


## method 2 
qemu-system-aarch64 -M raspi3 -kernel kernel8.img -nographic -serial file:uart0 -serial file:uart1

### method 2 result :

## method 3 
qemu-system-aarch64 -m 128 -M raspi3 -serial null -serial mon:stdio -nographic -kernel kernel8.elf

### method 3 result :

01_bareminimum (master) $ qemu-system-aarch64 -m 128 -M raspi3 -serial null -serial mon:stdio -nographic -kernel kernel8.elf
qemu-system-aarch64: terminating on signal 15 from pid 26643 ()

02_multicorec (master) $ qemu-system-aarch64 -m 128 -M raspi3 -serial null -serial mon:stdio -nographic -kernel kernel8.elf
qemu-system-aarch64: terminating on signal 15 from pid 26936 ()

03_uart1 (master) $ qemu-system-aarch64 -m 128 -M raspi3 -serial null -serial mon:stdio -nographic -kernel kernel8.elf
Hello World!
qemu-system-aarch64: terminating on signal 15 from pid 27145 ()

04_mailboxes (master) $ qemu-system-aarch64 -m 128 -M raspi3 -serial null -serial mon:stdio -nographic -kernel kernel8.elf
My serial number is: 0000000000000000
qemu-system-aarch64: terminating on signal 15 from pid 28152 ()