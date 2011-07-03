# Mirroring a subversion project with Git

    git checkout master
    git svn init -s http://svn.project.org/project_url
    git update-ref refs/remotes/trunk refs/remotes/origin/master
    git svn rebase

