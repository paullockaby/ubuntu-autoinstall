# Ubuntu Autoinstaller

This is a script for building a new installer for Ubuntu using its "autoinstall" technique. The example in this repository will:

* Creates a "paul" user with an SSH `authorized_keys` file and a known good environment.
* Builds an LVM configuration with a single data partition.

When using the installer there are still several questions that you must answer. These include:

* If there are multiple active interfaces you must choose one.
* What network configuration to use for this new host.
* Which disk to use for the installation. **WARNING!** This disk *will* be erased.

Otherwise this will create an entirely automated installation.

# How To Use This Script

You can run this on any Unix-based system like Linux or macOS. Follow these steps:

1. [Download a server installer image from the Ubuntu website](https://ubuntu.com/download/server). This process will work with both amd64 and arm64 images.
2. Clone this repository.
3. Install these libraries: `apt-get install -y --no-install-recommends xorriso`
4. Or install these libraries: `brew install xorriso`
5. Run the build script: `./build /path/to/ubuntu-24.04.2-live-server-arm64.iso /path/to/ubuntu-24.04-autoinstall-arm64.iso`
6. Use the new ISO file to build your host.

# Using the Autoinstall ISO

Use this ISO just like you would any other install ISO. An autoinstall configured ISO file can build baremetal systems or virtual machines. It is only useful for on-premise instances and is not useful for cloud instances.
