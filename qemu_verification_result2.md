# Qemu verification 


## method 1
qemu-system-aarch64 -M raspi3 -kernel kernel8.img -nographic

### method 1 result :  (please result1 )

## method 2 
qemu-system-aarch64 -M raspi3 -kernel kernel8.img -nographic -serial file:uart0 -serial file:uart1

### method 2 result :

## method 3 
qemu-system-aarch64 -m 128 -M raspi3 -serial null -serial mon:stdio -nographic -kernel build/kernel8.elf

### method 3 result :