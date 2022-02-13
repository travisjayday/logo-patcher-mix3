# OEM Boot Logo Patcher for the Xiaomi Mi Mix 3

Replace default Xiamoi boot splash, charging icon, and Fastboot logo.

## Requirements

- Python version 3

## Usage

```text
Usage:  python3 logogen.py [option] [file] ... 

options: 
    -b, --boot      Replace boot splash. File must be 1080x1920 as a 24-bit bitmap.
    -c, --charge    Replace charging icon. File must be 178x350 as a 24-bit bitmap.
    -f, --fastboot  Replace Fastbot logo. File must be 558x992 as a 24-bit bitmap.
    -l, --logoimg   Specify path to custom vendor `logo.img` file. If not specified, default Mi Mix 3 logo.img is used
    -e, --extract   Extract original Mi Mix 3 vendor `logo.img` file to restore default logos.
```

## Flashing on your Phone

After running the script, it will output a `logo_patched.img` file. Move that file to your phone, boot into TWRP recovery and flash the image to the `logo` partition.

1. Reboot to TWRP
2. Click <kbd>Install</kbd>
3. Click <kbd>Install Image</kbd>
4. Select the `logo_patched.img` file
5. Select the `logo` partition
6. Swipe to flash

And profit!

## Image types

**Dimension format is `Width`x`Height`.**
**Format must be 24-bit bitmap.**

| Logo Name     | Dimensions |
| ------------- | ---------- |
| Boot Splash   | 1080x1920  |
| Charging Icon | 178x350    |
| Fastboot Logo | 558x992    |

## Examples

To flash a custom OEM boot splash called `boot_image.bmp`, execute the following command in the terminal:

```bash
python3 logogen.py -b boot_image.bmp 
```

To flash a custom OEM boot splash called `boot_image.bmp` *and* flash a custom charging icon called `new_battery.bmp`, execute the following command in the terminal:

```bash
python3 logogen.py -b boot_image.bmp -c new_battery.bmp 
```

To use a custom base image *and* flash a custom charging icon *and* flash a custom OEM boot splash *and* flash a custom Fastboot logo, execute the following command in the terminal:

```bash
python3 logogen.py -l custom.img -b boot_image.bmp -c new_battery.bmp -f new_fastboot.bmp
```
