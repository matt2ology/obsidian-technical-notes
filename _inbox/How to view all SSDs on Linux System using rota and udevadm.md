---
aliases:
note-type: permanent
date-created: 2024-05-23
long-form-date-created: Thursday, May 23, 2024
week-created: Week 21.4
time-created: 08:40 AM
---

# How to view all SSDs on Linux System

Related : [Device Manager](Device%20Manager)

Topic : [Linux Kernel](../3-permanent-notes-🧲/Linux%20Kernel.md)

To list only SSDs, you can use `lsblk` with `grep`:

```sh
lsblk -d -o name,rota | grep ' 0$'
```

## What is `rota`

In the context of Linux block devices, `rota` refers to the rotational property of the storage device. This attribute indicates whether a storage device is a rotating hard disk drive (HDD) or a solid-state drive (SSD).

Here's how it works:

- **0 (zero)**: Indicates that the device is non-rotational, meaning it is an SSD.
- **1 (one)**: Indicates that the device is rotational, meaning it is an HDD.
  You can view this property using various commands that provide detailed information
  about block devices, such as `lsblk` or by examining the contents of files in /sys/block.

## What is the `udevadm` command

The `udevadm` command is a utility for managing and querying the udev device manager on
Linux systems. udev is responsible for managing device nodes in the `/dev` directory and
handling all user space events raised while hardware devices are added or removed from
the system.

**Query Device Information**:

You can use `udevadm` to query detailed information about a device, such as its properties,
attributes, and metadata.

```sh
udevadm info --query=all --name=/dev/sda
```

This command provides a wealth of information, such as device properties (`ID_MODEL`, `ID_SERIAL`), symlinks, and other attributes defined by udev rules.

Using `udevadm` is crucial for system administrators and developers who need to manage and troubleshoot hardware devices on Linux systems.

## `rota` and `udevadm` Used in a Script

```sh
# iterate over all block devices in /sys directory
for device in /sys/block/*; do
    # check if the device is an SSD by looking at the rotational property of the block device queue directory
    if [ "$(cat $device/queue/rotational)" -eq 0 ]; then
        # get the model name of the device using udevadm info and grep
        model=$(udevadm info --query=all --name="${device##*/}" | grep 'ID_MODEL=')
        # print the device name and model name to the console if it is an SSD
        echo "${device##*/}: ${model#*=}"
    fi
done
```

### Obtain Serial Numbers

```sh
# Iterate over all block devices in /sys directory
# (e.g. /sys/block/sda, /sys/block/sdb, ...)
for device in /sys/block/*; doA
    # Check if the device is an SSD (rotational=0) or not (rotational=1)
    if [ "$(cat $device/queue/rotational)" -eq 0 ]; then
        # Get the device name (e.g. sda, sdb, ...)
        # from the full path (e.g. /sys/block/sda)
        dev_name=$(basename $device)
        # Get the model name of the device by using udevadm command and grep
        # the ID_MODEL line and cut the value after the equal sign
        model=$(udevadm info --query=all --name=$dev_name | \
            # Grep the ID_MODEL line from the output of udevadm command
            grep 'ID_MODEL=' | \
            cut -d= -f2) # -f2 means the second field after the equal sign
        # Get the serial number of the device
        serial=$(udevadm info --query=all --name=$dev_name | \
            # grep the ID_SERIAL line
            grep 'ID_SERIAL=' | \
            cut -d= -f2) # Cut the value after the equal sign (second field)
        # Print the device name, model and serial number of the SSD device
        echo "Device: /dev/$dev_name, Model: $model, Serial Number: $serial"
    fi
done
```
