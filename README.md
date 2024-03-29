# SysTool
A collection of helpful tools, gadgets, customizations, and fixes for Linux and Bash.

## Usage
Check **systool.md** or the **SysTool** man page for usage info. Usage for configure can be found with ``./configure --help``.

## Installing
This is reccomended for normal users. If you are trying to contribute to this project, see the Contributing section.

### Installing normally
1. Open the [releases tab on the github page](https://github.com/UsernameNotAvalible/SysTool/releases) and download the .tar.gz file for the latest release.
2. Uncompress the file by running the command ``tar --extract --file systool-*.tar.gz``
3. Enter the directory that was just created by using ``cd systool-(VERSION).tar.gz``, replacing (VERSION) with the version number of the release you downloaded.
4. For a normal install, run the commands ``./configure && make && sudo make install``. Extra options for configure can be found with ``./configure --help``. and you can use these options to fine-tune where different files are installed.
It is recommended to keep the release folder after you are done. It can be safely removed, but it is required to uninstall **SysTool**.

### Portable installation
**SysTool** can be run directly from a storage device without installing.
1. Open the [releases tab on the github page](https://github.com/UsernameNotAvalible/SysTool/releases) and download the .tar.gz file for the latest release.
2. Uncompress the .tar.gz file by running the command ``tar --extract --file systool-*.tar.gz`` and enter the directory using ``cd systool-(VERSION).tar.gz``, replacing (VERSION) with the version number of the release you downloaded.
3. Run the commands ``./configure && make portable``. This should output "Portable install complete. Path to current folder is:" and a full folder path.
You should now be able to run **SysTool** by running the *systool* file in the folder from step 4. Example: If the **SysTool** folder is named systool-1.0 and located on the drive */dev/sdb*, the command to run **SysTool** will be ``/dev/sdb/systool-1.0/systool``. The drive name may change, so make sure to use the correct drive name.

## Building and contributing
Please note that GNU Autotools must be installed before building. To install normally, check the Installing Section.

### Building from source
1. Clone this repository using ``git clone https://github.com/UsernameNotAvalible/SysTool`` and enter it using ``cd SysTool``.
2. Run ``aclocal && autoconf && automake --add-missing`` to generate configure and the Makefile.
3. For a normal install, run the commands ``./configure && make && sudo make install``. Extra options for configure can be found with ``./configure --help``. and you can use these options to fine-tune where different files are installed.

### Contributing
1. Fork the repository, clone the fork to your system, and enter it.
2. Enter a new branch for your feature with ``git branch develop && git switch develop``.
3. Change things! The code is in *src/systool*. Make sure to properly comment code, and remember to update the man page at *man/systool.md*!
4. Run ``aclocal && autoconf && automake --add-missing`` to generate configure and the Makefile.
5. Commit your changes to your fork with ``git commit -a && git push``.
6. Create a pull request to the main repository.