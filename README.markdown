# irsnot

irsnot is an irssi script that creates desktop notifications based on dbus. Message timeouts can be configured per nick.

## installation
    $ git clone git://github.com/tuxjay/irsnot.git
    $ cp irsnot/irsnot.pl ~/.irssi/scripts/
    $ cp irsnot/irsnotrc.sample ~/.irssi/irsnotrc

## configuration
The configuration file lives at ~/.irssi/irsnotrc. Here is a sample:
    # use this to set the default notification time for private messages.
    # this shows the default of 5000ms or 5s
    # nick * 5000

    # and for messages received through a channel
    # this shows the default which disables notifications for channels
    # chan * 0

    # override the default channel timeout for #chilon to 5000
    chan #chilon 5000
    chan &bitlbee 5000

    # use this to ignore notifications from a nick
    nick mrToms 0
    nick root 0

    # work people with messages i cannot miss
    nick bossman 50000000
    nick hrbossman 50000000

## commands
Reload the configuration file.
    /irsnot_reload

Issue a command (anything in the config file works here).
    /irsnot nick annoyingGuy 0

## dependencies
* perl Desktop::Notify module.
