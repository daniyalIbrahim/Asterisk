# Dockerfile for Asterisk-13.31.0

dockerfile contains

textfiles contain commands to define how an image is built 
images are used to instantiate containers
images built locally or pulled from registry
often built FROM another image (layers)



# Make Asterisk-13.31.0 using gnu Make


download the tar ball and store the tar ball in /usr/src/Asterisk

use make by executing

sudo make clean
sudo make 



now inside the directory  /usr/local/src/asterisk-13.31.0

sudo ./configure

Important!

### Cached Data

The ./configure command caches certain data to speed things up if it's invoked 
multiple times. To clear all the cached data, you can use the following command 
to completely clear out any cached data from the Asterisk build system.

sudo make distclean

You can then re-run ./configure.

just to be sure we didnt miss any dependency we will change the directory to

cd /contrib/scrpts



### Using install_prereq

The install_prereq script is included with every release of Asterisk in the c
ontrib/scripts subdirectory. The script has the following options:

    test -               print only the libraries to be installed.
    install -            install package dependencies only. Depending on your 
                         distribution of Linux,version of Asterisk, and capabilities 
                         you wish to use, this may be sufficient.
    install-unpacakged - install dependencies that don't have packages but only have 
                         tarballs. You may need these dependencies for certain 
                         capabilities in Asterisk.

sudo ./install_prereq install

sudo ./install_prereq install-unpackaged

Now,

sudo make install

Executable files installed:

            /usr/sbin/asterisk: 
            The Asterisk daemon that runs your PBX
            /usr/sbin/safe_asterisk: 
            A shell script to make sure Asterisk keeps on running
            /usr/sbin/astgenkey
            /usr/sbin/astman: 
            A very very basic manager interface. See astman for details.

Other directories structures created:

            /usr/include/asterisk: 
            Contains header files required for building asterisk applications, channel drivers, and other loadable modules.
            /usr/lib/asterisk: 
            Contains binary objects related to Asterisk which are architecture-specific.
            /var/lib/asterisk: 
            Contains variable data used by Asterisk in its normal operation.
            /var/spool/asterisk: 
            Used for runtime spooled files of voicemail, outgoing calls, etc.

