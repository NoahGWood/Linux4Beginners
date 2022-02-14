# Commands

Common commands on Linux systems

## A

### Alias

#### Description

Creates or displays command aliases

#### Example

```shell
alias copy=cp
```

### Alsamixer

#### Description

Starts the alsamixer audio mixing program

#### Example

```shell
alsamixer
```

### Apropos

#### Description

Searches [man](##Man) pages for specific words and phrases.

#### Example

```sh
apropos "usage"
```

## Apt

#### Description

Apt is a high-level CLI for the synaptic package management system. See also: [apt-get](##apt-get) and [apt-cache](##apt-cache)

#### Example

```shell
apt update
```



## Apt-get

#### Description

apt-get is used to install, remove, and administer software packages installed with the apt package manager.

#### Examples

##### Install a package

```shell
apt-get install some_package
```

##### Update Repositories

```shell
apt-get update
```

##### Upgrade All Packages

```shell
apt-get upgrade
```

##### Aggressive Package Upgrade

```shell
apt-get dist-upgrade
```

**avoid** except when upgrading to a new release.

dist-upgrade in addition to upgrading packages also attempts to handle package conflicts. If there is a conflict, dist-upgrade will remove "less important" packages to force the installation of "more important" packages. Doing this can rarely result in you no longer having applications you may want which is why it's commonly used only when upgrading to a new release.

##### Un-Install  packages

```shell
apt-get remove some_package
```

##### Un-Install package & delete all configuration files

```shell
apt-get purge some_package
```

**Warning:** Be careful with this command as it will often remove additional packages. Be sure to read the command output so you know exactly which packages are being removed and make sure they will not lead to an unstable system.

##### Clear out local repository

```shell
apt-get clean
```

##### Additional command options:

* -f | Attempt to fix broken  packages (used with install and remove)
* --force-yes | **Dangerous** This bypasses any errors and protective measures during command execution. Be careful with this.

## B

### Bzip2

#### Description

Used to compress and decompress files.

#### Examples

##### Compress A File

```shell
bzip2 myfile
```

##### Decompress A File

```shell
bzip2 -d myfile
```

##### Additional Options

* -k | Do not delete original file after compression
* -t   | Test, performs a 'dry-run' without making a compressed file.

### Bzip2Recover

#### Description

Used to attempt to recover a damaged .bz2 file

#### Example

```shell
bzip2recover myfile.tar.bz2	
```

## C

### CAL

#### Description

Displays a calendar for the current or specified month and year.

#### Example

```shell
cal 2 2022
```

### CAT

#### Description

Prints text from a file to screen or combine files.

#### Note On Usage

cat is a very useful command, combined with [pipes](##Pipes) it lets you quickly write the output from other commands to a file.

#### Examples

##### Print File To Screen

```shell
cat somefile
```

##### Combine Files

###### Method 1: Combining two files into a third

```shell
cat file1 file2 > file3
```

###### Method 2: Combining multiple files into another file

```shell
cat file1 file2 file3 file4 file5 > file6
```

###### Method 3: Append one file to another

```shell
cat file1 >> file2
```

##### Pass stdin to file

```shell
cat > file1
```

#### Common Combinations

##### Overwrite Text To File

```shell
echo 'some text' | cat > file 
```

##### Append Text To File

```shell
echo 'some text' | cat >> file
```

### CD

#### Description

CD is used to change the current working directory in the terminal.

#### Examples

##### Go To Home Directory

```shell
cd ~
```

##### Go Up A Directory

```shell
cd ..
```

##### Go To Root Directory

```shell
cd /
```

##### Go To 'Some' Directory

```shell
cd /path/to/some/directory
```

### CHGRP

#### Description

chgrp allows you to change the group ownership of a file or directory.

#### Example

##### Change Ownership Of A File

```shell
chgroup my_group my_file
```

##### Change Ownership Of A Folder

```shell
chgroup my_group my_folder
```

##### Change Ownership Of A Folder & All Subfolders

```shell
chgroup my_group my_folder -R
```

### CHMOD

#### Description

Changes permissions of a file or directory.

#### Examples

##### Make File Readable By All Users

```shell
chmod a+r file
```

##### Make File Read & Writeable By All Users

````shell
chmod a+rw file
````

##### Make File Executable

```shell
chmod +x file
```

##### Make File Readable, Writable, and Executable By All Users

```shell
chmod a+rwx file
```

or

```shell
chmod 777 file
```



##### Make File Readable By Current User

```shell
chmod +r file
```

or

```shell
chmod 700 file
```

##### Folders

The commands above work the same for folders. To apply permission to all subfolders recursively, use the -R modifier

### CHOWN

#### Description

Changes ownership of a file or folder.

#### Examples

##### Change Ownership Of A File Or Folder

```shell
chown user1 file1
```

##### Change Ownership Of A Folder Recursively

```shell
chown -R user1 folder1
```

### CHROOT

#### Description

Changes the root file system to the selected path.

This command is really only useful for development/testing purposes. If you were creating your own linux distribution from scratch, setting up the toolchain for OS development, or making a cross-compiler it may be useful, but most users will not need to use this command.

#### Example

```shell
chroot /path/to/new/root
```

### CHVT

#### Description

The change virtual terminal command switches you to the specified virtual terminal.

#### Example

```shell
chvt 4
```

### CLEAR

#### Description

Clears the terminal screen of text and places the cursor at the top.

#### Example

```shell
clear
```

### CP

#### Description

cp is the "copy" command in Linux, it is used to copy files and folders as well as create symbolic links.

#### Examples

##### Copy A File

```shell
cp myfile /path/to/new/file
```

##### Copy A Directory

```shell
cp -r mydirectory /path/to/new/mydirectory
```

##### Create A Symbolic Link

```shell
cp -s myfile /path/to/symbolic/link
```

### CRONTAB

#### Description

Modify the crontab file (responsible for scheduling tasks).

#### Examples

##### List Crontab Entires

```shell
crontab -l
```

##### Delete Crontab File

```shell
crontab -r
```

##### Edit Crontab File

```shell
crontab -e
```

##### Edit A Specific User's Crontab File

```shell
crontab -u username -e
```

##### Delete A Specific User's Crontab File

```shell
crontab -u username -r
```

## D

### Date

#### Description

Displays the current date and time

#### Example

```shell
date
```

### DF

#### Description

DF displays the free space left within the file system.

#### Examples

##### Display Only Local Filesystem

```shell
df -l
```

##### Display Human Readable Sizes

```shell
df -h
```

### DIFF

#### Description

Diff shows the differences between files.

#### Examples

##### Basic

```shell
diff file1 file2
```

##### Ignore Case

```shell
diff file1 file2 -i
```

### DIFF3

#### Description

Displays the difference between three files (see also: [diff](###Diff))

#### Examples

##### Basic

```shell
diff3 file1 file2 file3
```

##### Ignore Case

```shell
diff3 file1 file2 file3 -i
```

### DIG

#### Description

Returns the IP Address of a specific domain name

#### Example

```shell
dig example.com
```

### DMESG

#### Description

Displays the kernel message log. Useful for debugging hardware issues particularly with USB devices.

#### Example

```shell
dmesg
```

### DPKG

#### Description

DPKG is the Debian Package Manager, it is used to install, remove, and administer packages. **Notice:** Most users should be using the [apt](###Apt) package manager which provides an easy to use interface for the DPKG manager.

#### Examples

##### Install A Package

```shell
dpkg -i package.deb
```

##### Remove A Package

```shell
dpkg -r package.deb
```

### DPKG-Reconfigure

#### Description

Reconfigures a package that has already been installed, typically used when the package is not working correct.

#### Example

```shell
dpkg-reconfigure package
```

### DU

#### Description

Shows the size of a file or folder.

#### Examples

##### Basic

```shell
du /path/to/folder
```

``` shell
du somefile
```

##### Human Readable Output

``` shell
du -h /path/to/folder
```

``` shell
du -h somefile
```

#### Directory Summary

```shell
du -s /path/to/folder
```

## E

### Eject

#### Description

Used to eject a removable drive or disk.

#### Example

``` shell
eject /media/cdrom
```

### EX

#### Description

A simple CLI-based text editor commonly used in shell scripting. See also: [Nano](###Nano)

#### Example

``` shell
ex myfile.txt
```

### EXIT

#### Description

Used to end a shell session and close the terminal.

#### Example

``` shell
exit
```