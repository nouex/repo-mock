## Auto Removal of Conflict Separators, GH-11 (6/5/2016)##

* No, git does not remove conflict separators "<<< === >>>"
* *caveat-to-remember:* think of it this way, when there's a conflict the two conflicting parts are seperated by "===", when you fix the conflict and `git add <file-name>` then you are telling git that whatever is on that file you are aware of and you want to commit exactly as it is.  It really is jut another commit except you will then do `git commit` without necessarily having a commit message b/c git will auto fill the message with a merge message.
