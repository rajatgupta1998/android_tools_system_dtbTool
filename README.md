# Motorola's DTB Tool for Moto G4/Plus

![Device Tree Overlays](https://source.android.com/devices/architecture/images/treble_dto_bootloader.png "DTO")

## How to combine the various DTBs generated as ```dt.img``` after building ```zImage``` and the corresponding ```DTBs``` for athene (Moto G4/Plus)

1. cd to your kernel source's root directory ```$(SRC_DIR)``` , ```$(OUT_DIR)``` is the out folder 
2. Download the latest dtbTool-N from the repo.
```
wget https://github.com/rajatgupta1998/motorola_tools_system_dtbtool/raw/master/dtbTool-N
```
3. Make it executable by
```
chmod +X <filename>
```
4. You might need to install the following packages (atleast on Debian based systems like Ubuntu)
```
libc++-helpers gcc-6-base libc6 libgcc1 multiarch-support libc++1 libc++-test libc++abi1 libc++abi-test libc++abi-dev libc++-dev
```
5. Merge the DTBs into a single ```dt.img``` by running this command in the ```$(SRC_DIR)```
```
./dtbtool -s $(BOARD_KERNEL_PAGESIZE) -o $(OUT_DIR)/arch/arm/boot/dtb -p $(OUT_DIR)/scripts/dtc/ $(OUT_DIR)/arch/arm/boot/dts/
```
6. cd to ```$(OUT_DIR)/arch/arm/boot/``` and find your ```dt.img```

7. Now do whatever you want to. :v: