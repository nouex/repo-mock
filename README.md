__Remember__: cherry pick this file to all branches, so it's available on them

__Remember__: branches prepended with local- or remote- are equal to its
counterpart withou the prepending, e.g.,
  * 'local-merge' -> on GH is 'merge'
  * 'revert-1' -> on GH is 'local-revert-1'

Keep the convention just because it's already legacy.  Careful tho, remember to
use the explicit `git push <repo> <local-b-name>:<remote-b-name>`

***

## Merging (4/21/2016) ##
[Merge vs Rebase](http://stackoverflow.com/a/16666418/3280654)

* merge conflict arises when two tip-of-branch commits affect same lines
* local merge commit happens only if you resolve merge conflicts
* GitHub GUI allows you to merge (only if it is non-conflicting), but creates a merge commit
* GitHub merg squashing allows you to merge a pull request and avoid the unnecessary extra commits by "squashing" it into a single merge commit (Must have no merge conflicts ovbiously).

## Reverting (4/29/2016) ##

* **three turnouts**
  1. revert without conflict
    * when data is *appended* to end of a file buffer
    * file delete/add commit reverted
  2. revert with conflict
    * when fresh data added to file buffer has the buffer's old data *split* so
      that part or all of the old data is after the fresh data

      If you try to revert a commit that has already been reverted by resolving
      a conflict first, 3. will **not** happen, another conflict will occur.
  3. don't revert, commit already reverted
    * note the second paragraph of 2.

___

**NTS**: `git bisect` will always be special (that slow day at the park with mum in CS, butterfly park or some shit...)
