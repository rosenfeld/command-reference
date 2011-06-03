# Display branch in shell prompt

## Debian

Set PS1 in ~/.bashrc like:

    PS1='${debian_chroot:+($debian_chroot)}\[\033[01;32m\]\u@\h\[\033[00m\]:\[\033[01;34m\]\w\[\033[31m\]$(__git_ps1 " %s")\[\033[00m\]\$ '
