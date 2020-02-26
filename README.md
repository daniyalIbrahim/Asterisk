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


Checked out revision 15.
cc -g -Wall -O2 -D_NBS_PRIVATE -Wmissing-prototypes -Werror -Wno-pointer-sign -D_REENTRANT   -c -o nbsd.o nbsd.c
nbsd.c: In function ‘merge_stream’:
nbsd.c:295:29: error: taking address of packed member of ‘struct <anonymous>’ may result in an unaligned pointer value [-Werror=address-of-packed-member]
  295 |    res = audio_dequeue(ns, h.s, samples);
      |                            ~^~
nbsd.c:304:28: error: taking address of packed member of ‘struct <anonymous>’ may result in an unaligned pointer value [-Werror=address-of-packed-member]
  304 |   res = audio_dequeue(ns, h.s, samples);
      |                           ~^~
nbsd.c: In function ‘handle_network’:
nbsd.c:453:5: error: ‘strncpy’ output may be truncated copying 79 bytes from a string of length 79 [-Werror=stringop-truncation]
  453 |     strncpy(ns->name, si->streamname, sizeof(ns->name) - 1);
      |     ^~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
nbsd.c:454:5: error: ‘strncpy’ output may be truncated copying 15 bytes from a string of length 15 [-Werror=stringop-truncation]
  454 |     strncpy(ns->app, si->appname, sizeof(ns->app) - 1);
      |     ^~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
In function ‘audio_acquire’,
    inlined from ‘merge_stream’ at nbsd.c:276:9,
    inlined from ‘timing_ready’ at nbsd.c:566:10:
nbsd.c:221:4: error: ‘strncpy’ output may be truncated copying 79 bytes from a string of length 79 [-Werror=stringop-truncation]
  221 |    strncpy(ih.i.streamname, ns->name, sizeof(ih.i.streamname) - 1);
      |    ^~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
nbsd.c:222:4: error: ‘strncpy’ output may be truncated copying 15 bytes from a string of length 15 [-Werror=stringop-truncation]
  222 |    strncpy(ih.i.appname, ns->app, sizeof(ih.i.appname) - 1);
      |    ^~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
cc1: all warnings being treated as errors
make: *** [<builtin>: nbsd.o] Error 1
daniyal@Daniyel:/usr/src/asterisk-13.31.0/contrib/scripts$ sudo ./install_prereq test
