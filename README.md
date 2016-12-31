# Kibana Backup Tool

This script allow to list and export kibana resources like search, visualization and dashboard.

## Table of contents
* [Installation](#installation)
  * [Package (favourite)](#package)
  * [Archive](#archive)
* [Usage](#usage)

## Installation

<a name="package"/>
### Package (favourite)

I have setup a **Debian/Ubuntu** apt repository to distribute this package

You can add my personal repository to your **`/etc/apt/sources.list`** by adding the following line:

`deb https://llavaud.github.io/kbt/apt stable main`

You must also retrieve and install my GPG key:

`wget -O - https://llavaud.github.io/kbt/apt/conf/gpg.key | sudo apt-key add -`

And then install the package:

```
sudo apt-get update
sudo apt-get install kbt
```

### Archive

If you dont want to add a new repository on your system you can also retrieve the [latest zip/tar.gz archive](https://github.com/llavaud/kbt/releases/latest)

This script depends on several binary or Perl library, so you need to install the following **Debian/Ubuntu** packages before using it:

```bash
sudo apt-get install libhttp-message-perl libjson-perl libwww-perl
```

Once the packages are installed, you just need to extract the archive

## Usage

```
kbt [OPTIONS] <COMMAND>

 OPTIONS
   --type     TYPE           Type of kibana resources {search|visualization|dashboard} (defaults to all)
   --output   FILE           Backup file (defaults to kbt_export.json)
   --host     IP:PORT        Ip address of kibana instance (defaults to localhost:5601)
   --index    INDEX          Kibana index (defaults to .kibana)
   --help                    Print this help

 COMMAND
   list                      list resource's id
   export                    export resources
```
