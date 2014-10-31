# How to submit code to a GitHub project on Windows

## *From Zero to “Pull Request”*

By Steve Ognibene [@NYCdotNet](https://twitter.com/nycdotnet "Twitter") - November 17, 2013

This guide is intended for developers who have not previously used Git
or GitHub, but who do have basic knowledge of at least one other source
control system. This guide is unique because:

-   It is specifically for developers who use Windows

-   It only describes how to contribute to an *existing* project

-   It prioritizes the GitHub for Windows UI when the command-line is
    not required

-   It is not embarrassed to give step-by-step directions or definitions
    of basic terms

-   It prioritizes "the simple way for the common circumstance" over
    "every possible way for every possible circumstance"

The reader is strongly encouraged to learn more about Git and GitHub
from any of the many other wonderful guides out there after having
successfully navigated this guide. **This document only teaches the bare
minimum to get started!**

*Assumption: you are an administrator on a Windows 7 or higher PC, and
you have some sort of text editor available (Notepad is fine).*

## Installing Stuff and Registering on GitHub

*Necessary terminology: Git is the source control system, GitHub is the
web site. You can use Git without GitHub, but not GitHub without Git.*

Go to <https://windows.github.com> and download the “GitHub for Windows”
client. Install it. This gives you a Windows UI suitable for most Git
operations and a PowerShell-based command line Git environment for the
rest.

Once the installation is complete, you will have to log in to GitHub.
Registering on GitHub.com is free, and you can both create new public
open source projects and contribute to existing public projects for
free.

-   Click the "Sign up" link in the GitHub for Windows application and
    then follow the directions to register for a free account via the
    web site.

-   Note that your GitHub username is always public, but *your email
    address can be public or private* depending on how you set your
    options (see note below).

Once you've registered on the site, switch back to the GitHub for
Windows application, enter your GitHub username and password, and log
in. On the Configuration tab, enter your full name and email address.

> If you are concerned about privacy, you can put your GitHub username
> instead of your full name and "*username*@users.noreply.github.com"
> instead of your email address; you will also want to visit
> <https://help.github.com/articles/keeping-your-email-address-private>
> and follow the instructions there.

After all that, you can click on the Dashboard link and you should be
ready to start using Git and GitHub.

## Forking a Repository

*Necessary terminology: A repository in Git (often abbreviated as a
"repo") is the largest single unit of code managed by Git; a repository
could be a major project, a collection of smaller related projects, or
even just a single script with a readme file. A fork on GitHub is your
"personal" copy of another user's repository.*

You're reading this guide because you want to contribute to a project on
GitHub. Let's make that happen. Go to GitHub.com and log in if you're
not already. Find that special project's web page and click the "Fork"
button in the upper-right hand corner. This will create a personal copy
of that project on GitHub that you can modify as you wish. Your fork
will be available at https://github.com/YourUserName/TheRepoName .

> Don't worry if this seems weird or presumptuous - it's not; forking is
> a very normal thing on GitHub and it doesn't obligate you to
> contribute further or functionally affect the original project in any
> way (other than incrementing their fork count). You don't need any
> special project permission to fork a public repo either - they are
> totally open!

Open GitHub for Windows and click your profile name on the left under
the "GitHub" category. The list of repositories in your account should
show, including the repo that you just forked (if not, try refreshing).
Hover the mouse pointer over the forked repo and click "Clone". All of
the source code from the repository will be copied to your computer. By
default, GitHub for Windows clones repositories as folders under
"*MyDocuments*\\GitHub". Double-click on the repository in GitHub for
Windows and you will be brought to the main repo screen which shows the
commit history on the left, and commit details on the right.

## Creating a Branch

*Necessary terminology: In Git, a branch is the way that independent
development efforts are kept separate from each other within a repo.*

You're now nearly ready to begin working on the project. Before you
start making changes or adding new stuff, you should always add a
branch. The idea with branches is that you can work on code without ever
being obligated to merge your changes into the main code branch. Also,
getting into the habit of using branches means you can very easily put
aside new work and switch back to an older branch if necessary (such as
having to patch a production issue after you've already started
development on a new feature).

If you look in the upper-right hand corner of the GitHub for Windows app
(to the right of the sync button), there should be a branch icon which
will say either "master" or the name of another branch in the repo.
Click the branch button, type the name "MyNewFeature" in the field, and
hit Enter. You should notice that the text "MyNewFeature" now appears by
the branch icon. This means that you are now operating on the
"MyNewFeature" branch which can be changed independently from the
previously selected branch.

> Note that creating a branch was not difficult and there wasn't an
> expensive file copy operation involved. Also note that you didn't even
> have to talk to GitHub to do this; Git is a decentralized source
> control system, and most operations occur locally and are synchronized
> to the server later.

Click "Publish", and the newly created branch will be sent to GitHub and
added to your fork of the project. Remember - this does not affect the
original project, just *your fork* of it.

## Committing Code

*Necessary terminology: In Git, a commit is a unit of code that is saved
into a repository on a particular branch. Git commits have many common
traits with check-ins from other source control systems, but there are
also some differences due to Git being a decentralized system.*

Let's practice creating some junk code and committing it. Click the
"gear" icon in the top-right and select "open in explorer". Create a new
text file in that folder called "ThisIsMyNewFeature.txt". Put **at least
three lines** of random text in the file, and save it. Switch back to
GitHub for Windows. You should see in the upper-left that there are
"uncommitted changes". Click the button labeled "show".

Listed on the right-hand panel, you should see the name of the text file
that you created. The content is displayed by clicking the "twisty"
adjacent to the file name. (If you don't see the file, the .txt
extension might be ignored by the project - try renaming to .js or .md.)
Since it's a new file, each line will be highlighted in green to
indicate addition. Ensure that the box next to the file name is checked
and type a commit message such as "Added new feature text file" in the
field on the upper-left. Finally, click the "commit to MyNewFeature"
button.

You've now successfully committed code to your local branch! The commit
should appear in the history list on the left above the historical
commits made by other users in the "unsynced commits" section (we'll get
back to that later). Now, open up the same text file in your text editor
again, and modify **one** of the lines (in whatever way, as long as it's
different) and add **one** new line with new random text. Switch back to
GitHub for Windows, and you should now see that the removed lines are
highlighted in a salmon color and the added lines are again highlighted
in green (Git considers a modified line to be deleted and re-added in
its new form). Commit the updated file by adding another commit message
(such as "edited the feature content"), and then clicking the commit
button.

So far, you've made two commits to your local repository. You may have
noticed that the commits are listed as "unsynced commits" in GitHub for
Windows. This is because the changes still only reside on your local
machine. We're ready to send these changes up to your personal project
fork on GitHub now. Click the "sync" button in the upper-right hand
corner. This should take a few seconds and then your commits will be
moved down to the commit history. Click the "gear" again and choose
"view on github". There should be a button on the web page that says
"branch: master" (or another branch name) on it. If you click that
button, you will be able to select the MyNewFeature branch and see the
commits you made as well as viewing the content of the
"ThisIsMyNewFeature.txt" file on the GitHub web site. Recall that these
changes only exist in *your fork of the project repository* - they
haven't affected the main project repository in any way.

## Switching and Deleting Branches

Before we continue, let's switch branches on our project just to see
what happens. Back in GitHub for Windows, click on the branches button
in the upper right and select "master". Then open up Windows Explorer on
the Repo folder. You will notice that the "ThisMyNewFeature.txt" file
has disappeared! This is because that file does not exist on the master
branch; it only exists within the "MyNewFeature" branch. Switch back to
GitHub for Windows and change the branch to "MyNewFeature" again. You
will notice that the text file has now reappeared in the folder. All of
this happened locally - this is possible because the commit history of
each local Git branch is stored in the file system within a hidden
".git" folder (which you can see if you have "view hidden files" turned
on).

Switch back to the master branch yet again, and then click on the
"manage / merge" button within the branch menu. Since we merely created
the MyNewFeature branch as a test, and there is no actual useful work
within it, we can safely delete it. Hover your mouse pointer over the
MyNewFeature branch, and click the trash can button that appears on the
right. Note that deleting a branch is one of the few features of GitHub
for Windows that happens *immediately* on the server.

If you ever need to switch branches, you will first have to commit all
of your outstanding changes to the current branch, or else you can
investigate `git stash` at the command prompt (out of scope for this
guide).

## Go Forth and Code!

This is the part where you go do "interesting stuff" on your own. But
before you start patching code, adding tests, developing new features,
or improving documentation, remember that you should always create a
branch first. Call the branch something related to what you're doing
such as "Issue-12-Fix", "CSS-Cleanup", or "New-Shiny-Feature". Then,
code up that fix or feature and regularly commit to your branch along
the way. A good mental model is, *"save on words, commit on sentences,
push on paragraphs"*.

Before you do too much work on a project, it's also important to do some
research on how or if the project maintainers accept contributions.
There may be a wiki page or readme that has that information. Also, if
there is a mailing list, you may wish to join it and ask. This will help
you understand if the idea in your head sounds interesting or useful to
the current project maintainers, and also what standards or rules the
maintainers may have with regards to how changes are developed and
submitted. Some projects commonly accept unsolicited code, while others
follow a strict governance model. It's good to know the culture of the
project up-front before you've spent a great deal of time working on
something; the bigger your change, the more you should tend to research
and communicate before coding.

## Creating a Pull Request

*Necessary terminology: A Pull Request is when one GitHub user asks
another GitHub user to accept code into their repo; "I hereby request
that you pull this code into your repo". Pull requests may be discussed
or modified until merged (accepted), or closed ("no thanks") by the repo
owner.*

So you have created a branch, worked on some code, committed the code to
your branch, and synchronized your local repo with your fork of the
project on GitHub. You've also communicated with the project owners
about your change, or else you've researched the project enough to know
that they accept unsolicited pull requests. Great!

To create a pull request, click the gear icon in GitHub for Windows and
choose "view on github". You should see a new banner towards the top of
the web page with a button that says "Compare & pull request". When you
click that button, you will see the changes that were made to your
branch versus the code in the main repo. Provide a good title for the
pull request and provide a reasonably detailed description about what
changed and why it is useful; be sure to reference any relevant issue
numbers or discussion topics and URLs. If you're happy with the code
deltas that are listed at the bottom of the page, click "Send Pull
Request" to contribute the code.

## Merging Other Changes

*Necessary terminology: In Git, a "Remote Repository", shortened as
"Remote", is a reference from your repo to another repository - for
example, from your local repo to your fork on GitHub. A "Remote Tracking
Branch", shortened to "Remote Branch", is simply a regular branch that
lives within a referenced remote repository.*

As long as no other changes were made to the main project's repo since
the time that you created your branch, the pull request should be able
to be accepted by the project maintainers without any further technical
work on your part. In busy projects, however, other changes were
probably made in the meantime and you may be asked to merge those
changes before your pull request will be accepted. This will require
using the Git command line tool.

Click the gear icon in the top-right of GitHub for Windows and choose
"open a shell here". You should see a PowerShell instance (GitHub for
Windows uses "posh-git") pointed to your repository folder with the name
of the current branch at the end of the prompt in square brackets.

If the branch name listed in square brackets on the prompt is not the
branch name that you've been working on, run this command to list the
available branches:

`git branch`

As long as you see the branch that you were working on in the list, you
can run then this command to switch to it:

`git checkout MyBranchNameThatIWasWorkingOn`

### Do this part once for your local repository

What we want to do is check to confirm that there is a remote called
"upstream" that points to the original GitHub repository. Run this
command (-v is for verbose):

`git remote -v`

You should see at least two lines listed as "origin" with the URL to
your forked repo - one marked "fetch" and one marked "pull". If you also
see two "upstream" lines, then you don't have to run the next command.
If you don't see them, however, run this command, substituting %owner%
for the GitHub owner's username, and %project% for the GitHub project
name:

`git remote add upstream https://github.com/%owner%/%project%.git`

If you run `git remote -v` again, you should now see that you've added a
remote called "upstream" that references the URL on GitHub for both
fetch and push operations. Now you can pull down the changes made in the
remote repository.

### Do this part every time you want to pull in other users' changes

The Git `pull` command will fetch commits from a local branch or remote
tracking branch and immediately merge them into the current branch. If
you have the branch you were working on selected and have established
the remote tracking branch called "upstream", then this command will
fetch the latest changes on the project's master branch from GitHub and
immediately merge them in to your *currently selected branch* (name in
square brackets) of your local repo:

`git pull upstream master`

Once you've merged the changes, switch back to GitHub for Windows. You
should see that your local repo is now one or more commits ahead of your
fork on GitHub. This may seem strange, but it is correct because you
pulled the changes from the "upstream" remote (pointing to the official
GitHub project repo) to your *local* repository - the fork of the
project on GitHub hasn't been updated yet.

If you click the sync button now, the merged changes in your local repo
will be copied up to your forked repo on GitHub and they will then be in
sync. If you happen to get a synchronization error, you'll have to
troubleshoot in the shell which is out of scope for this guide.

Pull requests work from branch to branch, so your existing pull request
on the GitHub web site should have updated as soon as you synchronized.
Click the gear icon in GitHub for Windows and choose "view on github".
You should be able to find your existing pull request on the original
project repo, and it should now be much more easily merged by the
project maintainers.

If you want to keep working on your new feature while you wait for the
pull request to be accepted, you can just create a new branch off of the
existing modified branch and keep going - you're not required to merge
back into master first.

### If you want finer control

If you want finer control of the process of pulling in changes (such as
seeing what has changed before merging the changes in), you should look
into the `git fetch` and `git merge` commands which can be executed
separately. These two commands executed in sequence would be the
essential equivalent of the above `pull` command:

`git fetch upstream`

`git merge upstream/master`

## That should do it!

You've now successfully contributed to an open source project on GitHub.
Hopefully the project maintainers will accept your work. Check out the
excellent Git resources listed below to learn more.

## Great Git References

-   Learn Git by reading: http://git-scm.com/

-   Learn Git interactively: http://try.github.io/

-   For "Advanced beginners" with Git (may be you now!):
    http://think-like-a-git.net/

-   How to fork a Repo (GitHub documentation):
    https://help.github.com/articles/fork-a-repo

-   Great blog post on updating a fork:
    http://bradlyfeeley.com/2008/09/03/update-a-github-fork-from-the-original-repo/
    
-   Send a pull request to another GitHub fork:
    http://faisonz.com/blog/send-pull-request-to-another-github-fork/
	
-   Difference between git pull --rebase and git pull --ff-only
    http://stackoverflow.com/questions/25430600/difference-between-git-pull-rebase-and-git-pull-ff-only

## Thanks

Mike Caruso

Nik Molnar [@nikmd23](https://twitter.com/nikmd23 "Twitter")

Steve Ward [@stevelward](https://twitter.com/stevelward "Twitter")

Bradly Feeley [@bradly](https://twitter.com/bradly "Twitter")

Alex Hasha [@alexhasha](https://twitter.com/alexhasha "Twitter")

This document was edited using Texts http://www.texts.io


