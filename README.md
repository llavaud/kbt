# kbt - Kibana Backup Tool

This script allow to list, export and import kibana resources (search, visualization and dashboard).

You can export everything you want from Kibana interface, but if you want to setup a cronjob to do regular backup or just do it in CLI, this is the right tool to use.

Tested on Kibana **4.x** and **5.x**.

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

This script depends on several Perl library, so you need to install the following **Debian/Ubuntu** packages before using it:

```bash
sudo apt-get install libhttp-message-perl libjson-perl libwww-perl
```

Once the packages are installed, you just need to extract the archive

## Usage

```
kbt [OPTIONS] <COMMAND>

 OPTIONS
   --file       FILE         Backup file to import (defaults to kbt_export.json)
   --help                    Print this help
   --host       IP[:PORT]    Ip address of elasticsearch instance (defaults to localhost:9200)
   --index      INDEX        Kibana index (defaults to .kibana)
   --output     FILE         Backup file (defaults to kbt_export.json)
   --overwrite               Overwrite existing documents during import (default is to skip existing docs)
   --type       TYPE         Type of kibana resources {search|visualization|dashboard} (defaults to all)

 COMMAND
   list                      list resource's id
   export                    export resources
   import                    import resources
```
