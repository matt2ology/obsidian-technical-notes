---
aliases:
note-type: permanent
date-created: 2023-11-10
long-form-date-created: Friday, November 10, 2023
week-created: Week 45.5
time-created: 12:51 PM
---

# NetApp A800

The A800 eco system

Related : [Hardware](../4-hub-notes-🚉/Hardware.md)

Topic : [NetApp](../4-hub-notes-🚉/NetApp.md)

![NetApp - initial terminal screen loader setup](NetApp%20-%20initial%20terminal%20screen%20loader%20setup.md)

## Keynotes, takeaways, and inspirations

### What is a loader?

**A "loader" is a shell.** Setting up these screen loader sessions allows one to do the following:

- Can boot into [NetApp's OnTap](https://www.netapp.com/data-management/ontap-data-management-software/) cluster mode
- Can boot into [Maintenance mode](https://docs.netapp.com/us-en/hci/docs/concept_hci_storage_maintenance_mode.html) with the following command into one of the shells: `boot_ontap menu`

  - (1) Normal Boot: boot into the cluster you have
  - (2) Boot without /etc/rc
  - (3) Change password
  - (4) Clean configuration and initialize all disk: used regularly especially when the disks are not showing up, or drastic changes to the system and we want a clean configuration and initialize all the disk (this takes some time)
  - (5) [Maintenance mode boot](https://kb.netapp.com/onprem/ontap/os/What_are_the_ONTAP_maintenance_mode_commands)
  - (6) Update flash from backup config

    > `>`

  - (7) Install new software first: used when we want to update to a new kernel. Be sure that the kernel to upgrade to is on a server and the system has the network to reach said server.
  - (8) Reboot node
  - (9) Configure Advanced Drive Partitioning
    - (9.a) Partition the drive in a particular way
    - (9.c) Uses the whole disk and sets-up the [cluster](https://docs.netapp.com/us-en/hci/docs/concept_hci_clusters.html) for you when you have an unclaimed disk.
  - (10) Set Onboard Key Manager recovery secrets
  - (11) Configure node for external key management

### Maintenance Mode Boot

#### Two ways to go into Maintenance Mode

1. Can enter this mode on a loader instance by typing the following command: `boot_ontap maint`
2. Enter via the menu
   1. Type the command into the loader shell: `boot_ontap menu`
   2. Type the number "5" at prompt "Selection (1-11)?"

You'll see that a bunch of warnings prompted onto the screen. This is fine and is to be expected, for a NetApp engineer configured the system to have exceptions so we can boot without issues.

But be aware of what the warnings and messages that are prompted. There will be a time that you may need to debug, troubleshoot, or inspect an issue and the warnings are you're entry point to the root problem or solution.

You'll know that **you're in Maintenance Mode when your terminal prompt is printed with an asterisk-star and a right angle bracket**:

> `*>`

#### To exit out of Maintenance Mode

type: `halt` into the terminal prompt. After the exit of Maintenance mode, by typing `halt`, the terminal will reboot back into the loader/shell.

> `*> halt`

#### Maintenance Mode Commands

By typing a question mark (?) you'll be presented with a list of possible commands you can run in maintenance mode; for example, `acorn` , `batch_snap` , `cna_flash` , and etc.

Some commands used often like

- `disk show` : shows disks that are "claimed". When creating a cluster is to take ownership of the drives plugged into the system. Under the text column "OWNER" it will list the system name (e.g. "Apollo-CVE") and is followed by the cluster index (e.g. "-01", "-02", "-03", ect.).
  - Adding the flag option `-n` (i.e. `disk show -n`): Will show us all disks that have not been "claimed" by a cluster. Note that if you plugged in a drive, but don't see the drive it may have already been automatically claimed by a cluster. You'll know a disk has no ownership, has not been claimed by a cluster, when under the text column "OWNER" it will report that it is "Not Owned".
  - Adding the flag option `-m` (i.e. `disk show -m`): shows you if you have any failed disks or in a bad state.

##### To unassign a disk from a cluster us the following command

Removing a disk from ownership of a cluster

> `*> disk remove_ownership -f <DISK>`

**Example**: `disk remove_ownership -f 0n.3`

##### Assigning a disk to a `null pool`

A `null pool` is signified by three sets "999", a total of nine 9's, `999999999.`

**A disk assignment to a `null pool` follows this structure**:

The assignment of a disk to a `null pool` is done on both terminals/loaders.

> `*> disk assign -s` `999999999` `-f <the disk that is Not Owned>`

**Example**: `disk assign -s 999999999 -f 0n.3`

**To verify that the assignment been made run the following command**:

> `*> disk show -s` `999999999`

### Booting into Lemur

Lemur gives you access to [nvme-cli](https://nvmexpress.org/open-source-nvme-management-utility-nvme-command-line-interface-nvme-cli/) and, mnv-cli (the CLI for the Marvell dongle allowing you to update the dongle).

You must first enter Maintenance Mode and then exit out of Maintenance Mode prior as a prerequisite to then boot into Lemur. Enter Lemur is done via one of the two terminal loader/shells you've instantiated.

1. Boot into Lemur - Use the following command on loader/shell

   > `setenv LINUX_BOOTARGS` "console=ttyS0,115200 console=tty0 mem-7936m intel_iommu=off acpi_rsdp+$bootarg.acpi_rsdp nopat"``; setenv NETWORK_DEVICE eth1; ifconfig e0M -auto; boot -bzimage http://10.132.xx.xx/bzImage=02.12.32.00

   1. Once booted you'll be prompted with an NVMe CLI shell
   2. Typing `nvme list` you'll see that everything will be listed as "Marvell_NVMe_Controller" under the text column "Model". On the front-end to the node the NVMe Controller broadcast itself as a NVMe drive as well as broadcast the drive's namespace as its own namespace.

1. Pull mnv_cli

   > ` wget http:``//10.132.xx.xx/nmv_cli `

1. Provide Execute Privileges

   > `chmod +x mnv_cli`

1. Now you can use `nvme-cli` tool and also `mnv_cli` (marvel tool)
1. Command to flash Dongle FW

   > ` wget http:``//10.132.xx.xx/8126.bin `
   > ./mnv*cli <host_bus_adapter*(HBA)\_Number> flash -o hba -t raw -f 8126``.bin /dev/nvme1n1|

1. Boot
