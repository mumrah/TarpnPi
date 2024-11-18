# TARPN RaspberryPi OS Image

🚧 Work In Progress 🚧

A Raspberry Pi distribution for [TARPN](https://tarpn.net) packet radio nodes.  

This repository contains the source script to generate the distribution out of
an existing Raspbian distro image. It is heavily inspired by the
[OctoPi repo](https://github.com/guysoft/OctoPi) which uses [CustomPiOS](https://github.com/guysoft/CustomPiOS)
to build a custom RaspberryPi image.

# How to Develop this

The main install script is located at [src/modules/tarpn/start_chroot_script](https://github.com/mumrah/TarpnPi/blob/main/src/modules/tarpn/start_chroot_script). 
This is where `apt-get` commands, downloading custom binaries, and other installation steps should go.

After pushing to the repository, a GitHub Action will automatically build a new image. Action runs can be found on the Actions
tab in the repository. 
<img width="1220" alt="image" src="https://github.com/user-attachments/assets/404ef507-01f9-4c9c-a0ad-b5f3f1a07e80">

If you have forked this repository, you must enable GitHub Actions for the repository in order for this automation to work.

At the bottom of the workflow run page ([example](https://github.com/mumrah/TarpnPi/actions/runs/11879989379)), the new image will appear as a build artifact.

<img width="883" alt="image" src="https://github.com/user-attachments/assets/28d04426-befe-4526-922a-2d8dc1c56cdb">

To test the new image, simply download it and flash an SD card. It is also possible to verify the image using emulation
such as qemu. Here is a script that will let you run an image on Mac OS https://gist.github.com/chetbox/3d2624b3727b35cf82d68f21f2449e2c.
