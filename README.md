# muslx32toolkit

WARNING: Using the cleaner script can cause data loss of you do not unmount your partitions especially on /mnt.  An update to fix this will be coming.

BASH Scripts for Gentoo Linux to build stage3 and stage4 images using crossdev for the muslx32 platform

note: This is currently being actively developed as of 20170507 from the written instructions to automated scripts to avoid human error.

note: The scripts rely on stable packages.  ~amd64 keyworded packages are not supported.  If you want ~amd64 support you must manually update the patches yourself.

The scripts use an interactive checkpoint system so you can edit and return back to that step them if they fail.  You may need to edit the config file to properly edit packages to unmask or and use, or specific files/versions to use.

## Instructions

Step 0.0: Download the stage3 tarball and the portage snapshot described in the config file from a Gentoo mirror.  It is important that you make sure you download the files in a folder that is either a mounted partition or a new folder.

Step 0.1: Edit the config file so that you choose the right cflags.  You may need to edit the bash scripts and config file to apply custom masks/unmasks/keywords.

Step 0.2: Edit the config_unattended to choose either prompt or unattended mode.  Unattended mode may break if your connection is not always on, internet disruption, or newer updated stable packages which muslx32 patches were not applied.  Currently, there is no resume feature in unattended mode, so it requires editing to resume.

Step 1: chmod +x prepare

Step 2: Run ./prepare

Step 3: Move the muslx32toolkit folder into the same folder as the stage3 and portage snapshot

Step 4: Run ./build-crossdev-toolchain `<full-path-containing-both-stage3-and-portage-tarball>`

(chroot)

Step 5: Run ./create-stage3 in muslx32toolkit

(chroot)

Step 6: Run ./create-stage4 in muslx32toolkit

(chroot)

Step 7: Modify /etc/fstab

Step 8: Modify bootloader and install it

Step 9: Add users

Step 10: Add root password

Step 11: Perform any additions to your stage4 image

## Notes

The script relies on the following Portage overlays which the create-stage3 script will clone and unmask:
* https://github.com/orsonteodoro/muslx32
* https://github.com/gentoo/musl
* https://github.com/lluixhi/musl-extras

## License

The files in this package are licensed under GPL version 2 or newer.
