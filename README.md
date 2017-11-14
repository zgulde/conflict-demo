# Conflict Demo

## Let's create a conflict

1. Starting from the `master` branch, create two new branches, `red` and `blue`.

    ```
    git branch red
    git branch blue
    ```

1. Switch to the `red` branch, change the color to red, and commit.

    ```
    git checkout red
    # change the color in the css file...
    git add style.css
    git commit -m 'Change background to red'
    ```

1. Switch to the `blue` branch and change the color to blue.

    ```
    git checkout blue
    # change the color in the css file...
    git add style.css
    git commit -m 'Change background to blue'
    ```

1. Switch back to master and merge the branches

    ```
    git checkout master
    git merge red
    git merge blue
    ```

1. We should now have a merge conflict!

1. Open up the `style.css` file and look around. Solve the merge conflict.

    Git will place markers in the file that indicate where the merge conflict
    is. To resolve the conflict, remove these markers, and decide which version
    of the code you want to use. This usually means pairing with a teammate and
    talking about which changes to use, or how to integrate the two sets of
    changes.

    See also the commands below.

1. Mark the conflicts as resolved

    ```
    git add style.css
    ```

1. Conclude the merge

    ```
    git commit
    ```

## Commands

Just use our version of the file

```
git checkout --ours style.css
```

Use their version of the file

```
git checkout --theirs style.css
```

Discard any changes to the file and re-create the original conflicted merge
result

```
git checkout -m style.css
```

Abort the merge

```
git merge --abort
```

## Notes

- Make sure you've added and committed any work before attempting a merge!

    If you have uncommited changes and you try to merge, then back out of the
    merge (`git merge --abort`), you could potentially lose your work.
