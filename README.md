# The modified linux kernel

The linux kernel
================

There are several guides for kernel developers and users. These guides can
be rendered in a number of formats, like HTML and PDF. Please read
Documentation/admin-guide/README.rst first.

In order to build the documentation, use ``make htmldocs`` or
``make pdfdocs``.  The formatted documentation can also be read online at:

    https://www.kernel.org/doc/html/latest/

There are various text files in the Documentation/ subdirectory,
several of them using the Restructured Text markup notation.

Please read the Documentation/process/changes.rst file, as it contains the
requirements for building and running the kernel, and information about
the problems which may result by upgrading your kernel.

# Extensions

I'm working on writing extensions, fixing bugs and make the optimize the source for a better source handling as developer. A few additional commands are:

## dependency installing

Someone not knowing from where comes the header `<gelf.h>` or `<openssl/opensslv.h>` or similar, type `make dep_install` to install all required dependencies. If you're not using apt, then search instead for `libelf-dev` and `libssl-dev` or on other distros they may be `libssl-devel` and `libelf-devel`.

## Kernel installing

To install the kernel and modules together, type `make res_install` to install them all to the new directory `_install`, which can be used as root directory. Note that there will only be installed the kernel and the modules. In the skeleton you can then add a userland via busybox or similar.

To remove the `_install` directory, type `make res_cleaning`.

# License

Just use this source code unter the terms of the Linux licenses, as known. The additional extensions are also under GPL.

# Linux kernel compilation dependencies

Maybe there are a few developers wondering why the kernel searches for headers like `gelf.h` or `openssl/opensslv.h`. For this you must install on Linux the packages `libelf-dev` and `libssl-dev` or similar on you linux distro. Then all these compilation errors disapear.
