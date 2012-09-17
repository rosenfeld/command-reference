# Find commits that weren't cherry picked yet

    git log --cherry-pick --oneline --right-only ...feature-branch
