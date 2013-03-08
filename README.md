Take a photo with your Mac's built in camera, upload it, and paste it into
the current Flint ([a great Campfire client](http://giantcomet.com/flint)) tab.

![face](http://adambachman.org/images/snaps/2013-03-08-12-06-42_snapshot.jpg)

## Install

    $ git clone git://github.com/abachman/snap-copy-paste.git
    $ cd snap-copy-paste
    $ rake install

## Usage

The install process will create a config file. It should be at `~/.snaprc` and
it should look like this:

    # this is YAML
    REMOTE_IMAGE_HOST: "mywebhost"
    REMOTE_IMAGE_PATH: "~/example.com/images/snaps/"
    REMOTE_IMAGE_URI:  "http://example.com/images/snaps/"

`REMOTE_IMAGE_HOST` is a server you have SCP and SSH access to.

`REMOTE_IMAGE_PATH` is a directory on that server that images can be served from.

`REMOTE_IMAGE_URI` is the final URL that your uploaded image will be available at.

Now you can run the script:

    $ snap-copy-paste

If you don't want to assign the environment variables permanently, you can
delete `~/.snaprc` and assign them ad hoc like this:

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

A server that can host image files and accept SCP uploads.

## LICENSE

snap-copy-paste: Public domain. (I made this)

imagesnap: Public domain. (I didn't make this)

