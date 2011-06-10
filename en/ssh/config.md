# SSH Configuration

For easing SSH access options, the user can customize some settings in a per host configuration. Here is a sample ~/.ssh/config:

    # In a new line, the special char preceding some special keys can take special actions (TODO: explain this better in a new topic).
    # By default it is tilde (~) but it won't work in some keyboard layouts where tilde is a dead key, like Brazilian ABNT-2.
    EscapeChar !

    # Just declaring some hosts will enable autocomplete after "ssh <TAB>"
    Host host01 host02 host03

    Host another-host
            User someuser

    Host my-provider
            Hostname my.provider.com
            Port 2222
            User provider_username
            # binds to localhost 5432 (postgresql) through tunnel
            LocalForward 5432 127.0.0.1:5432
            # binds git port of the Gitorious server reachable by my.provider.com and listen in all local interfaces (0.0.0.0)
            LocalForward 0.0.0.0:9418 gitorious.intranet.company.com:9418

    # this will user root as user by default unless specified otherwise in the hosts above in any ssh access.
    Host *
            User root
            # Avoids the need for specifying "ssh -X" for running graphical commands remotely
            ForwardX11 yes

## The special char and special commands

TODO: write this section, explaining port forwarding, closing connection, etc
