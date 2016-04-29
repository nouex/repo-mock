## Reverting ##

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
