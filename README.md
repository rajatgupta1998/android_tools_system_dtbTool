Motorola's DTB Tool for Moto G4/Plus

How to combine the various DTBs generated as dt.img after building a kernel for athene (Moto G4/Plus) 

1. cd into your $(OUT_DIR)/arch/arm*/boot/dts 
2. Download the latest dtbTool-N from the repo.
3. Make it executable by chmod +X <filename>
4. Run this command: 
./dtbTool --force-v3 --motorola 1 -o $(OUT_DIR)/arch/arm/boot/dt.img -s 2048 -p scripts/dtc/ $(OUT_DIR)/arch/arm/boot/dts/
5. cd to $(OUT_DIR)/arch/arm/boot/
6. Now place the dt.img in your AnyKernel2 folder.
