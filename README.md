Currently ScarletDME is a 32 bit-only application - you'll need to
compile it using 32 bit libraries on your system.  This is pretty
easy to do.

These packages are needed to build ScarletDME for most Linux distributions:
libgcc.i686
glibc-devel.i686

For proper terminal operation, you'll need to install:
ncurses-devel
ncurses-compat-libs

If you would like to support remote access to your ScarletDME system
via the QMClient API or telnet services, you'll need to install:
xinetd

See README.md in the xinetd.d directory for instructions on the further use of 
xinetd.

Before you build ScarletDME, you should create a user named "qmsys" and
a group named "qmuser".  Make sure you add the qmuser group to any user
that will be using ScarletDME, /including/ the "root" and "qmsys" users!

You should be able to build the system by just typing "make' in the directory
where the Makefile lives.  Enter "make install" to install the result of the
first "make" command.  You'll need to be root do this.  "make install" will 
fail if the qmsys user and qmuser group doesn't exist.

The install portion of the makefile may be tweaked to do additional things like
copying the xinetd files to thier required locations and a fancy sed edit of
the /etc/services file.

Run "make datafiles" to copy the "production" data files to their operating 
location.

Code formatting notes:
I'm using Visual Studio code with the Microsoft C/C++ IntelliSense, debugging,
and code browsing extension installed.  

Each time I need to edit a code file, it's reformatted using the clang-format
feature in the extension.  The .clang-format file in this repository is based
upon the Chromium format, but it will not reflow comments, nor will it
sort includes.  The settings can be found in ScarletDME/.clang-format.

Some files have been reformatted, most have not.  However, eventually they all
will be.  There's also instances of K&R-style function parameter declarations
and those will be converted to ANSI-style as I discover them.

[26Feb20 gwb]

I resumed work on this project because I had an itch I just had to scratch.
That's how most open source software is done apparently. :)

I should note that at the moment, the contents of this git repo builds and
works for *me*.  I'm not guaranteeing it'll work for anyone else. :)

I'm not sure what the future holds for this project, but I would like to get 
a clean, working build of a 64 bit ScarletDME.  I had originally thought that
this was very difficult due to the pre-compiled p-code that the system depended
on.  However, after actually doing some research into what was going on, it 
may be a much less dramatic task than I'd originally thought.  My original 
assumption about the p-code issue was *wildly* incorrect.  That happens when
you just glance at an issue without actually digging into it.

This means that a 64 bit version of ScarletDME isn't that far fetched after
all.  Time well tell I suppose.  I know what needs to be done and how to do 
it, so at least I've got that going for me. :)

I would also like to finish the "re-branding" of OpenQM to ScarletDME.
While some things will forever be "OpenQM-isms" like the names of the binaries,
there are other areas that just need to be changed in order to make the
re-branding effort complete.

I've got a 66 page document that's all of the release notes I could find for
the commercial releases of OpenQM.  That's going to act as a starting point
for improvments and/or bug fixes.  I think.  We'll see.

I'm going to end this document by thanking Martin Phillips for the original
GPL release of OpenQM.  We've not always seen eye to eye on things, but his
contributions to the Multi-Value database industry cannot be understated.
I will always appreciate the gift he's given us all and the value that OpenQM
represents to the Multi-Value database community - regardless of whether or not
they realize it. ;)

-Gene Buckle, February 26th, 2020.