# sb-kiosk

Packer scripts to build a kiosk image that can be used with srcomp

## Requirements

- Docker
- This repository cloned

## Usage

Simply run the `./build.sh` script. Packer will download all needed files and save the output image to `kiosk-<GIT-HASH>.img.xz`. Running `./build.sh fast` will skip the compression step, which greatly speeds up the build process.

To use wifi, you will need to add a file named `wpa_supplicant.conf` to the `/boot` directory on the image. There is an example file called `wpa_supplicant.conf.example` in this repository. The `/boot` directory is a FAT32 partition on the image, so it can be mounted on most computers to add the file.

To use autossh, you will need to set up the ssh key to be used by generating a keypair and adding the public key to the autossh user on the server that the tunnel will connect to. The private key should be named `autossh.key` and placed in `/boot/autossh.key` on the image. The `/boot` directory is a FAT32 partition on the image, so it can be mounted on most computers to add the key.
