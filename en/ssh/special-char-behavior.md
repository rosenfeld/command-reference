# Escape char behavior

You can set the escape char in ~/.ssh/config like:

    EscapeChar !

By default, the escape char will be tilde (~), but it won't work for keyboard layouts where tilde is a dead key, like Brazilian ABNT-2.

For using the special commands, the escape char should be the first typed character after a line feed (Enter). Typing ~? (or !? if you
changed the escape char as above) will present the possible usage for the special char. More often, this will be used for binding a
port using the established connection. This is achieved with the command mode (~C). In the command mode type 'help' for getting the
available command list. This example will bind 'host.from.intranet-connection', port 22 to local port 2222:

    ~C
    L:2222:host.from.intranet-connection:22

Most often will just like to mirror some local port from the remote host:

    ~C
    L:8161:localhost:8161

This will listen on localhost only. If you want to listen in all IPV4 interfaces, the equivalent command would be:

    ~C
    L:0.0.0.0:8161:localhost:8161
