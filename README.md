# OEM Boot Logo Patcher for the Xiaomi Mi Mix 3
Replace default Xiamoi boot logo, charging battery logo, and fastboot logo. 
Just execute the python script logogen.py and specify custom images to replace default Xiamoi logos. 

# Requirements
- Python version 3

# Usage
```
Usage:  python3 logogen.py [option] [file] ... 

options: 
    -b, --boot      replace boot image. File must be 1080x1920x24 bitmap (24bpp). 
    -c, --charge    replace charging battery logo. File must be 178x350x24 bitmap (24bpp)
    -f, --fastboot  replace fastbot image. File must be 558x992x24 bitmap (24bpp)
    -l, --logoimg   specify path to custom vendor logo.img file. If not specified, default MiMix3 logo.img is used
    -e, --extract   extract original MiMix3 vendor logo.img file to restore default logos.
```

# Flashing on your Phone 
After running the script, it will output a logo_patched.img file. Move that file to your phone (via cable or email), boot into TWRP recovery and flash the image to the logo partition.
```
TWRP->install->install image->select logo_patched.img->select logo->swipe to flash->reboot->profit
```

# Image types
Note that custom _boot logos_ must be Bitmap images with dimensions 1080x1920x24 (width x height x bits per pixel).

Custom _battery charging logos_ must be Bitmaps with dimensions 178x350x24. 

Custom _fastboot logos_ must be Bitmaps with dimensions 558x992x24.

# Examples
To flash a custom oem boot logo called boot_image.bmp, execute the following command in the terminal:
```
python3 logogen.py -b boot_image.bmp 
```
To flash a custom oem boot logo called boot_image.bmp AND flash a custom charging logo called new_battery.bmp, execute the following command in the terminal:
```
python3 logogen.py -b boot_image.bmp -c new_battery.bmp 
```
To use a custom base image AND flash a custom charging logo AND flash a custom boot logo AND flash a custom fastboot logo, execute the following command in the terminal:
```
python3 logogen.py -l custom.img -b boot_image.bmp -c new_battery.bmp -f new_fastboot.bmp
```
# Have fun!
<img src="https://user-images.githubusercontent.com/10280490/52920042-03ce1500-32ce-11e9-9f03-3e529e3e46ae.jpg" width=300>
