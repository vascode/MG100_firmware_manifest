# MG100 Manifest Repo

## Using the MG100

See the user guide for the MG100 [here](https://github.com/LairdCP/MG100_firmware/blob/master/README.md)

## Cloning Firmware

This is a Zephyr `west` manifest repository. To learn more about `west` see [here](https://docs.zephyrproject.org/latest/guides/west/index.html).

To clone this repository properly use the `west` tool. To install `west` you will first need Python3.

Install `west` using `pip3`:

```
# Linux
pip3 install --user -U west

# macOS (Terminal) and Windows (cmd.exe)
pip3 install -U west
```

Once `west` is installed, clone this repository using `west init` and `west update`:

```
# Checkout the latest manifest on master
west init -m https://github.com/LairdCP/MG100_firmware_manifest.git

# OR checkout v2.0.0 tag
west init -m https://github.com/LairdCP/MG100_firmware_manifest.git --mr v2.0.0

# OR checkout GA1 branch
west init -m https://github.com/LairdCP/MG100_firmware_manifest.git --mr GA1

# Now, pull all the source described in the manifest
west update
```

## Preparing to Build

If this is your first time working with a Zephyr project on your computer you should follow the [Zephyr getting started guide](https://docs.zephyrproject.org/latest/getting_started/index.html#) to install all the tools.

The MG100 currently uses zephyr 1.14.x, so GCC 8 is recommended.  Anything newer may cause issues when compiling.
[GNU Arm Embedded Toolchain: 8-2019-q3-update](https://developer.arm.com/tools-and-software/open-source-software/developer-tools/gnu-toolchain/gnu-rm/downloads) is recommended.

See here to [setup the GNU ARM Embedded tools](https://docs.zephyrproject.org/1.14.1/getting_started/toolchain_3rd_party_x_compilers.html)

## Building the Firmware

From the directory where you issued the `west init` and `west update` commands you can use the following command to build the firmware:

```
# Windows
west build -b mg100 -d mg100_firmware\build mg100_firmware\mg100

# Linux and macOS
west build -b mg100 -d mg100_firmware/build mg100_firmware/mg100
```
