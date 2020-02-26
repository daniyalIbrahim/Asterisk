#### Directories used by Asterisk-13.31.0


###    /etc/asterisk/ 
            contains the Asterisk configuration files

###     /etc/ 
            this directory has the zaptel.conf file, used for the configuration of Zaptel Telephony Group hardware

###     /usr/lib/asterisk/modules/ 
            directory contains all of the Asterisk loadable modules. Within this directory are the various applications, codecs, formats, and channels used by Asterisk. By default, Asterisk loads all of these modules at startup. 
            
            the modules which are not required can be removed using module.conf file

##      /var/lib/asterisk/ 
            directory contains the astdb file and a number of subdirectories. The astdb file contains the local Asterisk database information, which is somewhat like the Microsoft Windows Registry.

###        subdirectories of /var/lib/asterisk/ include
####       agi-bin/
            contains custom script, which can interface with Asterisk via the various built in AGI applications
####       firmware/
            contains the firmware for various Asterisk-compatible devices.It currently contains only the iax/ subdirectory, which holds the binary firmware image for Digium’s IAXy.
####       images/ 
            Applications that communicate with channels supporting graphical images look in the images/ directory.
####       keys/
            Asterisk can use a public/private key system to authenticate peers connecting to your box via an RSA digital signature. If you place a peer’s public key in your keys/ directory, that peer can be authenticated by channels supporting this method (such as the IAX2 channels). 
####       mohmp3/
            When you configure Asterisk for Music on Hold, applications utilizing this feature look for their MP3 files in the mohmp3/ directory. Asterisk is a bit picky about how the MP3 files are formatted, so you should use constant bitrate (CBR) encoding and strip the ID3 tags from your files.

####       sounds/
            All of the available voice prompts for Asterisk reside in the sounds/ directory. The contents of the basic prompts included with Asterisk are in the sounds.txt file located in your Asterisk source code directory. Contents of the additional prompts are located in the sounds-extra.txt file in the directory to which you extracted the asterisk-sounds package earlier in this chapter.

####       /var/spool/asterisk/
            The Asterisk spool directory contains several subdirectories, including dictate/, meetme/, monitor/, outgoing/, system/, tmp/, and voicemail/ (see Figure 3.4, “/var/spool/asterisk/ directory structure”). Asterisk monitors the outgoing directory for text files containing call request information. These files allow you to generate a call simply by moving the correctly structured file into the outgoing/ directory.

####       /outgoing/
            Call files being placed into the outgoing/ directory can contain useful information, such as the Context, Extension, and Priority where the answered call should start, or simply the application and its arguments. You can also set variables and specify an account code for Call Detail Records. More information about the use of call files is presented in Chapter 9, The Asterisk Gateway Interface (AGI).

####       /dictate/
            The dictate/ directory is the default location where the Dictate() application looks for files.

####       /meetme/
            The meetme/ directory is the location where MeetMe() conference recordings are saved.
            Recordings from either one-touch recording (the w and W flags to the Dial() application), the MixMonitor(), or Monitor() applications are stored in the monitor/ directory.

####       /system/ 
            is used by the System() application for temporary storage of data.

####       /tmp/ 
            directory is used, funny enough, to hold temporary information. Certain applications may require a place to write files to before copying the complete files to their final destinations. This prevents two processes from trying to write to and read from a file at the same time.

            All voicemail and user greetings are contained within the voicemail/ directory. Extensions configured in voicemail.conf that have been logged in to at least once are created as subdirectories of voicemail/.

###       /var/run/
            The /var/run/ directory contains the process ID (PID) information for all active processes on the system, including Asterisk (as specified in the asterisk.conf file). Note that /var/run/ is OS-dependent and may differ.

###       /var/log/asterisk/
            The /var/log/asterisk/ directory is where Asterisk logs information. You can control the type of information being logged to the various files by editing the logger.conf file located in the /etc/asterisk/ directory. Basic configuration of the logger.conf file is covered in Appendix D, Configuration Files.

###       /var/log/asterisk/cdr-csv
            The /var/log/asterisk/cdr-csv directory is used to store the CDRs in comma-separated value (CSV) format. By default information is stored in the Master.csv file, but individual accounts can store their own CDRs in separate files with the use of the accountcode option (see Appendix A, VoIP Channels for more information)



#### Dependencies of Asterisk-13.31.0

##### internal dependency

##### external dependency

