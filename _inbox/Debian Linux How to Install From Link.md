---
aliases:
note-type: permanent
date-created: 2024-05-23
long-form-date-created: Thursday, May 23, 2024
week-created: Week 21.4
time-created: 11:42 AM
---

# Debian Linux How to Install From Link

Related : [Ubuntu](Ubuntu)

Topic : [Linux](../4-hub-notes-🚉/Linux.md)

To install a package from a web link using the command line in Ubuntu, you can use the
`wget` command to download the package and then the appropriate package manager to
install it.

Here's a general approach:

1. Use `wget` to download the package from the web link.
2. Use `dpkg` or `apt` to install the downloaded package.

Here's an example:

```bash
wget http://example.com/package.deb
sudo dpkg -i package.deb
```

Replace `http://example.com/package.deb` with the actual web link of the package you
want to install.

If the package has dependencies, you might need to resolve them manually by installing the
required packages using `apt`:

```bash
sudo apt install -f
```

This command will attempt to fix any broken dependencies by installing the necessary
packages.

## Via Zip File

If the package you want to install is a zip file (`package.zip`) containing the necessary files
for installation, you'll need to follow these steps:

1. Use `wget` to download the zip file.
2. Unzip the package.
3. Follow any installation instructions provided within the package (often found in a README file).

```sh
# Download the zip file
wget http://example.com/package.zip

mkdir /path/to/destination/folderToHoldExtraction

# Unzip the package
unzip package.zip -d /path/to/destination/folderToHoldExtraction

# Navigate into the extracted directory
cd /path/to/destination/folderToHoldExtraction

# Use the DPKG utility to run the following command
sudo dpkg -i <package_name>.deb

# After the tool is installed, run the following command to get info
sudo dpkg -l sst
```

Double check installation:

```sh
sst show -ssd
```

### Remove SST Installation

```sh
#######################################################
# To remove an RPM package, run the following command #
#######################################################
sudo dpkg -r sst
```
