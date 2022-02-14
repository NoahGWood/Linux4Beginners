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

### Cal

#### Description

Displays a calendar for the current or specified month and year.

#### Example

```shell
cal 2 2022
```

### Cat

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

