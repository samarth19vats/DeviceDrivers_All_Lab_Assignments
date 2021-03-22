# Exercise - 6
Write a simple Char Device Driver. Test it by using passing on data.
# Overview
Implemented a Simple Character device driver that does basic operations such as read,write,open and exit. After compiling it as module loaded it to the kernel and executed the test_driver.
```
samarth@Predator:/media/samarth/8CB835EAB835D384/Study material/4th YEAR/Device Drivers/Lab/CED17I020_EX6$ sudo mknod -m 777 /dev/simple_char_device  c 301 0
samarth@Predator:/media/samarth/8CB835EAB835D384/Study material/4th YEAR/Device Drivers/Lab/CED17I020_EX6$ ls -la /dev | grep simple_char_device
```
Creating a inode at master 301 and viewing whether it is created successfully .mknod is used to create devices that populate /dev/. 
```
samarth@Predator:/media/samarth/8CB835EAB835D384/Study material/4th YEAR/Device Drivers/Lab/CED17I020_EX6$ make
```
This commmand is used to compile the souce code simple_char_driver.c to create a module called simple_char_driver.ko and will also create a object file for testing i.e. simple_char_test.

```
samarth@Predator:/media/samarth/8CB835EAB835D384/Study material/4th YEAR/Device Drivers/Lab/CED17I020_EX6$ sudo insmod simple_char_driver.ko
```
This command will call init_module() which is called when the module is inserted into the kernel or loaded to the kernel.
```
samarth@Predator:/media/samarth/8CB835EAB835D384/Study material/4th YEAR/Device Drivers/Lab/CED17I020_EX6$ cat /proc/devices | grep simple_driver
```
This command will display that our new driver is installed.
```
samarth@Predator:/media/samarth/8CB835EAB835D384/Study material/4th YEAR/Device Drivers/Lab/CED17I020_EX6$ ./simple_char_test 
```
This is the tester file for output.
```
samarth@Predator:/media/samarth/8CB835EAB835D384/Study material/4th YEAR/Device Drivers/Lab/CED17I020_EX6$ sudo rmmod simple_char_driver.ko
```
This command will call cleanup_module() which is called just before the module is unloaded from the kernel.
# Ouput
![Screenshot](testdrive.jfif)\
This is the screenshot of the driver running.\
![Screenshot](insmod.jfif)\
This is kernel log when module is loaded printing the message.\
![Screenshot](rmmod.jfif)\
This is kernel log when module is unloaded printing the message.

