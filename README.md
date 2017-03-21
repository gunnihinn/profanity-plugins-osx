# Installing profanity with plugin support on OSX

The homebrew version of profanity doesn't come with plugin support. To enable
it, we have to compile profanity from source. We assume you have homebrew
installed.

Install the dependencies to compile profanity:

    $ brew install automake autoconf autoconf-archive libtool pkg-config terminal-notifier

If you don't want notification support, omit `terminal-notifier` above. Now
clone the profanity repo and build it with:

    $ git clone https://github.com/boothj5/profanity
    $ cd profanity
    $ ./bootstrap.sh
    $ ./configure-plugins
    $ make 

If all goes well, you can run

    $ ./profanity -v

which should report:

    Build information:
    XMPP library: libstrophe
    Desktop notification support: Enabled
    OTR support: Enabled
    PGP support: Enabled
    C plugins: Enabled
    Python plugins: Enabled
    GTK icons: Disabled 

Then `make install` will install this version of profanity. If you also
installed profanity via homebrew, remember to uninstall it.
