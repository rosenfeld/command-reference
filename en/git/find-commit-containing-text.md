# Find a commit containing some text

git grep "something to search" $(git log -g --pretty=format:%h -S"something to search")
