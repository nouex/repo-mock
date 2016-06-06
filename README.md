# Steps to Testing #

1. Create a main branch for the command being tested at NEW_BRANCH_TEMPLATE.[1]

    e.g. `git checkout -b <some-command-name> NEW_BRANCH_TEMPLATE`
2. Document behavior, caveats, etc. to README.md of that branch.
3. When finished testing, cherry pick README.md of that branch to master.

**[1]** branches prepended with local- or remote- are equal to its
counterpart without the prepending, e.g.,
  * 'local-merge' -> on GH is 'merge'
  * 'revert-1' -> on GH is 'local-revert-1'

Keep the convention just because it's already legacy.  Careful tho, remember to
use the explicit `git push <repo> <local-b-name>:<remote-b-name>`

***
# Git Commands #

## Merging (4/21/2016) ##
[Merge vs Rebase](http://stackoverflow.com/a/16666418/3280654)

* merge conflict arises when newly-introduced commits from the *other* branch being merged affect the same lines that the new commit(s) from the *base* branch relative to the latest *commit-in-common* -- commit-in-common being the relative to the merged and base
* local merge commit occurs when coflict is resolved
* GitHub GUI allows you to merge (only if it is non-conflicting), but creates a merge commit
* GitHub merge squashing allows you to merge a pull request and avoid the unnecessary extra commits by "squashing" it into a single merge commit (2nd bullet pt must occur, i.e., must have no merge conflicts ovbiously).
* *caveat-to-remember*: merging on GH always leaves a merge-commit in the commit history, local merging leaves a merge-commit only if there is conflict and it's resolved

## Reverting (4/29/2016) ##

* three turnouts
  1. revert without conflict
    * when data is *appended* to end of a file buffer
    * file delete/add commit reverted
  2. revert with conflict
    * when fresh data added to file buffer has the buffer's old data *split* so
      that part or all of the old data is after the fresh data

      *caveat-to-remember*: If you try to revert a commit that has already been reverted by resolving
      a conflict first, 3. will **not** happen, another conflict will occur.
  3. don't revert, commit already reverted
    * note the second paragraph of 2.

## Auto Removal of Conflict Separators, GH-11 (6/5/2016)##

* No, git does not remove conflict separators "<<< === >>>"
* *caveat-to-remember:* think of it this way, when there's a conflict the two conflicting parts are seperated by "===", when you fix the conflict and `git add <file-name>` then you are telling git that whatever is on that file you are aware of and you want to commit exactly as it is.  It really is jut another commit except you will then do `git commit` without necessarily having a commit message b/c git will auto fill the message with a merge message.
___
# Notes to Self #

`git bisect` will always be special (that slow day at the park with mum in CS, butterfly park or some shit...)
