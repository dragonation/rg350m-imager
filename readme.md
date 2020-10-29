# RG350M Generation Tools

This project is rebased from the glebm's repo, and target on the specified device RG350M of Anbernic.

Most of the codes have been reviewed, and placed at a proper place in the project. All of the input and output files have been modified to specify via command switches. It helped us to direct generate output files without making the project dirty, and there's no more needs to copy the project into `output/images` folder.

All useful commands is placed in the `bin` folder:
* `create_mbr <output_mbr.bin>` to create master boot record (MBR) section image
* `create_system_image <input_folder> <output_system.bin>` to create system partition image
* `create_data_image <apps_folder> <cache_folder> <output_data.bin>` to create data partition image, usually containing apps 
* `make_sdcard_image <mbr.bin> <ubiboot.bin> <system.bin> <data.bin> <output_sd_card.img>` to create image for SD Card direct flushing

The `ubiboot.bin` is generated from ubiboot project, not the duty of this project.

Instructions on flashing the images to the device:
  https://github.com/gcwnow/ingenic-boot/wiki

Instead of flashing via ingenic-boot, you can create a combined image file and use a raw sector writer to put in on the SD card that will be used as the internal SD in the RG350M.
