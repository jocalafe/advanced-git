# Advanced Git

## Advanced Commands

- Interactive rebase
    - change a commit’s message
    - delete commits
    - reorder commits
    - combine multiple commits into one (squash or fixup)
    - edit or split commit into multiple commits

    ```bash
    git rebase -i <BASE>

    # Commands:
    # p, pick <commit> = use commit
    # r, reword <commit> = use commit, but edit the commit message
    # e, edit <commit> = use commit, but stop for amending
    # s, squash <commit> = use commit, but meld into previous commit
    # f, fixup <commit> = like "squash", but discard this commit's log message
    # x, exec <command> = run command (the rest of the line) using shell
    # b, break = stop here (continue rebase later with 'git rebase --continue')
    # d, drop <commit> = remove commit
    # l, label <label> = label current HEAD with a name
    # t, reset <label> = reset HEAD to a label
    # m, merge [-C <commit> | -c <commit>] <label> [# <oneline>]
    # .       create a merge commit using the original merge commit's
    # .       message (or the oneline, if no original merge commit was
    # .       specified). Use -c <commit> to reword the commit message.
    ```

    - what If I don’t like VIM? 😟💔

    ```bash
    git config --global core.editor "code --wait"
    ```

- Cherry Pick
    - Grab a commit from one branch and add it to another branch.
    - Mostly when you make a mistake and commit something to the wrong branch.

    ```bash
    git cherry-pick <COMMIT_HASH>
    ```

- Reflog
    - Mistakes where made
    - Recover commits or branches

    ```bash
    git reflog

    ### select the state hash before the mistake

    git reset --hard <STATE_HASH>

    git checkout -b fix-git-mistake <STATE_HASH>
    ```
