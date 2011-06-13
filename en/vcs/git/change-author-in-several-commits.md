# Changing the author name and/or e-mail in commits

For changing all commit author information:

    git-filter-branch --env-filter "export GIT_AUTHOR_NAME='New name'; export GIT_AUTHOR_EMAIL='New email'" HEAD

For replacing only some commits:

From http://help.github.com/change-author-info/:

    #!/bin/sh

    git filter-branch --env-filter '

    an="$GIT_AUTHOR_NAME"
    am="$GIT_AUTHOR_EMAIL"
    cn="$GIT_COMMITTER_NAME"
    cm="$GIT_COMMITTER_EMAIL"

    if [ "$GIT_COMMITTER_EMAIL" = "your@email.to.match" ]
    then
        cn="Your New Committer Name"
        cm="Your New Committer Email"
    fi
    if [ "$GIT_AUTHOR_EMAIL" = "your@email.to.match" ]
    then
        an="Your New Author Name"
        am="Your New Author Email"
    fi

    export GIT_AUTHOR_NAME="$an"
    export GIT_AUTHOR_EMAIL="$am"
    export GIT_COMMITTER_NAME="$cn"
    export GIT_COMMITTER_EMAIL="$cm"
    '
