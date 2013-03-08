Take a photo with your Mac's built in camera, upload it, and paste it into
the current Flint ([a great Campfire client](http://giantcomet.com/flint)) tab.

![face](http://adambachman.org/images/snaps/2013-03-08-12-06-42_snapshot.jpg)

## Install

    $ git clone git://github.com/abachman/snap-copy-paste.git
    $ cd snap-copy-paste
    $ rake install

## Usage

setup environment

    $ echo "# this is a YAML config file" > ~/.snaprc
    $ echo 'REMOTE_IMAGE_HOST: "mywebhost"' >> ~/.snaprc
    $ echo 'REMOTE_IMAGE_PATH: "~/example.com/images/snaps/"' >> ~/.snaprc
    $ echo 'REMOTE_IMAGE_URI: "http://example.com/images/snaps/"' >> ~/.snaprc

`REMOTE_IMAGE_HOST` is a server you have SCP and SSH access to.

`REMOTE_IMAGE_PATH` is a directory on that server that images can be served from.

`REMOTE_IMAGE_URI` is the final URL that your uploaded image will be available at.

run script

    $ snap-copy-paste

If you don't want to assign the environment variables permanently, you can
assign them ad hoc like this:

    $ REMOTE_IMAGE_URI="http://example.com/images/snaps/" \
        REMOTE_IMAGE_HOST="mywebhost" \
        REMOTE_IMAGE_PATH="~/example.com/images/snaps/" \
        snap-copy-paste

## Requirements

`snap-copy-paste` requires the "imagesnap" app. Installation instructions are
listed above.  The original source for imagesnap can be found at:
https://github.com/rharder/imagesnap.

If imagemagick is installed, the image will be constrained to 1024x768.
The easiest way to install imagemagick is to install homebrew and run:

    $ brew install libjpeg
    $ brew install imagemagick

## LICENSE

snap-copy-paste: Public domain. (I made this)

imagesnap: Public domain. (I didn't make this)

