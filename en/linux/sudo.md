# Running commands as superuser

## Installing

### Debian

    apt-get install sudo

## Sudoers Configuration

    visudo

Examples:

    # User privilege specification
    root    ALL=(ALL:ALL) ALL

    username ALL=(ALL:ALL) NOPASSWD: ALL

    # Allow members of group sudo to execute any command
    %sudo   ALL=(ALL:ALL) ALL

With this example, root can run all commands in any host and for any user using sudo.

The user 'username' can do the same and doesn't need to type any password for that.

All users in 'sudo' group can run any command as any user after typing their password.

## Usage Example

    sudo apt-get update
    sudo apt-get upgrade
    sudo -u postgres psql -l
