## Merge (4/21/2016) ##
[Merge vs Rebase](http://stackoverflow.com/a/16666418/3280654)

* merge conflict arises when two tip-of-branch commits affect same lines
* local merge commit happens only if you resolve merge conflicts
* GitHub GUI allows you to merge (only if it is non-conflicting), but creates a merge commit
* GitHub merg squashing allows you to merge a pull request and avoid the unnecessary extra commits by "squashing" it into a single merge commit (Must have no merge conflicts ovbiously).

#### TODO ####
* test if github's closing of pull requests that are merged locally and pushed from the CLI is independent of the commit message, i.e., if it is conflict-resolved and merged without an explicit message, `git add FILE; git commit`, does GitHub still know that it was merged as to auto close the PR?

***

__TODO__: cherry pick this file to all branches, so it's available on them

NTS: `git bisect` will always be special (that slow day at the park with mum in CS, butterfly park or some shit...)

