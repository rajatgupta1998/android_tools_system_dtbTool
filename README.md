# Android DTB Tool for Qualcomm/CAF devices

![Device Tree Overlays](https://source.android.com/devices/architecture/images/treble_dto_bootloader.png "DTO")

## How to combine the various DTBs generated as ```dt.img``` after building ```zImage``` and the corresponding ```DTBs```

1. cd to your kernel source's root directory ```$(SRC_DIR)``` , ```$(OUT_DIR)``` is the out folder 
2. Clone the repo
```
git clone https://github.com/rajatgupta1998/android_tools_system_dtbTool/ dtbTool 
```
3. Build the dtbTool binary using gcc, from the current directory itself. The latest one is recommended. I am using GCC 8.2.0 on Arch Linux.
``` 
gcc dtbTool/source/dtbtool.c -o dtbTool
```
4. You might need to install the following package:
```
libc++-helpers gcc-6-base libc6 libgcc1 multiarch-support libc++1 libc++-test libc++abi1 libc++abi-test libc++abi-dev libc++-dev
```
5. Merge the DTBs into a single ```dt.img``` by running this command in the ```$(SRC_DIR)```
```
./dtbTool -s $(BOARD_KERNEL_PAGESIZE) -o $(OUT_DIR)/arch/$(ARCH)/boot/dtb -p $(OUT_DIR)/scripts/dtc/ $(OUT_DIR)/arch/$(ARCH)/boot/dts/
```
6. cd to ```$(OUT_DIR)/arch/$(ARCH)/boot/``` and find your ```dt.img```

7. Now do whatever you want to. :v: