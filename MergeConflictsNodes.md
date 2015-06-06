Setting up kdiff3 as your merge tool
====================================

Download and install kdiff3.  I am going to assume it is available here:

`C:\Program Files\KDiff3\kdiff3.exe`

Once ever on your computer, modify the `mergetool.kdiff3.path` git configuration by running this command (update as required for different path to kdiff3):

`git config --global mergetool.kdiff3.path "C:\Program Files\KDiff3\kdiff3.exe"`

Then you can set 

git config --global merge.tool kdiff3

Then to resolve conflicts, run `git mergetool`.

When kdiff3 loads, click the "Go to first delta" button in the button bar.  It looks like a pyramid with a bar on top.  This may or may not be a conflict.  You can choose which lines you want to include in the merged file by clicking (or un-clicking since they're a toggle) the A B and C buttons which represent the three files you're looking at.  A is the base, B is the the latest version of the file from the branch you're merging into, and C is the latest version from the branch you want to merge.  Assuming you're merging a feature branch into master, A is the original version from master when the branch happened, B is master now, and C is the code from the new branch.

When there is no conflict (meaning when A and B are the same), Kdiff3 will automatically select C as the correct version of the code you want to use.  However, if B has also changed, you'll have to tell kdiff3 which one you want (or manually type a new version).

The standard workflow (assuming you always want the changes from C) is:
  * Click "Go to next conflict"  (or CTRL+PageDn)
  * Click the C button.  (or CTRL+3)
  * Repeat until there are no conflicts.
  
Note that it is possible to have all or none of A, B, and C clicked - they're all toggles and you (may) then get duplicate lines.  The order of the duplicate lines depends on the order you clicked the buttons.  It is also possible to directly edit the text in the white box at the bottom to manually resolve a conflict.

Once everything is completely resolved, save the file (CTRL+S) and quit KDiff3 (ALT+F4).  Git will then load the next conflicted file for you.  Repeat until there are no more conflicts.  Once you're done, run `git status`.  You will hopefully see the message (toward the top) "All conflicts fixed but you are still merging.".

Now that you're done merging, use the GitHub for Windows UI to remove the merge helper files.  These will be files created with a BACKUP.?????, BASE.?????, LOCAL.????? or REMOTE.????? name.  You can safely remove these files now as they were just helpers for the merge work (and the originals of each are already in source control).

The easiest way to remove them is to You can find the files like so:

dir /s *.BACKUP.?????.*
dir /s *.BASE.?????.*
dir /s *.LOCAL.?????.*
dir /s *.REMOTE.?????.*

If so, you can type `git commit -m "Merged"` (feel free to improve this check-in comment to includ the branch name, etc.) and the merge should be completed.  You could also technically do this in the UI.





References:
http://www.gitguys.com/topics/merging-with-a-gui/