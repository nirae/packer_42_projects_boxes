# Packer 42 projects ISO for vagrant

Using [Packer](https://packer.io/)

## ISO files

The ISO files need to be downloaded in the `iso_files` folder. The urls for download each are :

| Project | Url | md5 checksum |
| ------- | --- | ------------ |
| Snowcrash | https://projects.intra.42.fr/uploads/document/document/1573/SnowCrash.iso | 16ade8a197300c61cee10bcf6552d3f5 |
| Rainfall | https://projects.intra.42.fr/uploads/document/document/1570/RainFall.iso | 37805631fb424dfe643f1fb900e5ac8a |
| Override | https://projects.intra.42.fr/uploads/document/document/1574/OverRide.iso | 9adf39ca3de9a10d37cfab23d3d6c4bc |
| Darkly | https://projects.intra.42.fr/uploads/document/document/1575/Darkly_i386.iso | 66d1a5d77c33a935ccb219b97f207b6a |

## Usage

First, download the iso you wan't in the `iso_files` directory and verify the checksum

    $> cd iso_files && wget <url_of_the_iso>
    $> md5sum <iso>

All boxes work with vagrant and VirtualBox ONLY. Be sure to have VBox and vagrant installed

Use the make commands in the project directory you wan't to build. exemple : `snowcrash`

### Build the box

    $> make build

### Add the box in vagrant locally

    $> make vagrant-add

### Up the vm for testing

    $> make up

Can do all in one with `make`

For testing, go in the `vm` directory created by the Makefile and `vagrant ssh`. It's the working directory

### Clean

    $> make clean

This command remove the box file, the vagrant image, kill the vm and remove the `vm` directory

## Upload the box to the Vagrant Cloud

Official instructions on the documentation [here](https://www.vagrantup.com/docs/vagrant-cloud/boxes/create.html#creating-boxes-via-the-vagrant-cloud-web-interface)