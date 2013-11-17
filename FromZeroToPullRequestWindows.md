How to submit code to a GitHub project on Windows
=================================================

*From Zero to “Pull Request”*

This guide is intended for developers on the Windows platform who have not
previously used Git or GitHub, but who do have basic knowledge of at least one
other source control system.  This guide is different from other guides because:

-   It is specifically for developers who use Windows

-   It only describes how to contribute to an *existing* project

-   It tells you what to do step-by-step and includes definitions of the basic
    terms

-   It prioritizes the GitHub for Windows UI when the command-line is not
    required

-   It prioritizes "the simple way for the common circumstance" over "every
    possible way for every possible circumstance"

The reader is strongly encouraged to learn more about Git and GitHub from any of
the many other wonderful guides out there after having successfully navigated
this guide.  **This guide is intended to teach you the bare minimum to get
started!**

Note that this guide assumes that:

-   You are using Windows 7 or higher

-   You have administrative rights on your machine

-   You have some sort of text editor available (Notepad is fine)



Installing Stuff and Registering on GitHub
------------------------------------------

*Necessary terminology: Git is the source control system, GitHub is the web
site.  You can use Git without GitHub, but not GitHib without Git.*

Go to <https://windows.github.com> and download the “GitHub for Windows” client.
Install it.  This gives you a Windows UI suitable for most Git operations and a
PowerShell-based command line Git environment.

Once the installation is complete, you will have to log in to GitHub.
Registering and contributing to open source projects on GitHub is free.

-   Click the "Sign up" link in the GitHub for Windows application and then
    follow the directions to sign up for a free account via the web site.

-   Note that your GitHub username is always public, but *your email address can
    be public or private* depending on how you set your options (see note
    below).

Once you've registered on the site, switch back to the GitHub for Windows
application, enter your GitHub username and password, and log in.  On the
Configuration tab, enter your full name and email address.

>   If you are concerned about privacy, you can put your GitHub username instead
>   of your full name and "*username*@users.noreply.github.com" instead of your
>   email address; you will also want to visit
>   <https://help.github.com/articles/keeping-your-email-address-private> and
>   follow the instructions there.

After all that, you can click on the Dashboard link and you should be ready to
start using Git and GitHub.



Forking a Repository
--------------------

*Necessary terminology: A repository in Git (often abbreviated as a "repo") is
the largest single unit of code managed by Git; a repository could be a major
project, a collection of smaller related-projects, or even just a single script
with a readme file.  A fork on GitHub is your "personal" copy of another user's
repository.*

You're reading this guide because you want to contribute to a project on GitHub.
Let's make that happen.  Go to GitHub.com and log in if you're not already.
Find that special project's web page and click the "Fork" button in the
upper-right hand corner.  This will create a personal copy of that project on
GitHub that you can modify as you wish.  Your fork will be available at
https://github.com/YourUserName/TheRepoName .

>   If you're worried that this seems weird or presumptuous - don't be; forking
>   is a very normal thing on GitHub and it doesn't functionally affect the
>   original project in any way or obligate you to contribute.  You don't need
>   any special permissions to fork a public repo, either - it's totally open!

Open the GitHub for Windows app and click on your profile on the left under the
"GitHub" category.  The list of repositories in your account should show,
including the repo that you just forked.  (If the forked repo isn't there, click
refresh and it should appear.)  Hover the mouse pointer over the forked repo and
click "Clone".  After a few minutes, all of the source code from the repository
will be copied to your computer.  By default, GitHub for Windows clones
repositories as folders under "*MyDocuments*\\GitHub".  Double-click on the
repository in GitHub for Windows and you will be brought to the main repo screen
which shows the commit history on the left, and commit details on the right.



Creating a Branch and Committing Code
-------------------------------------

*A branch in Git is the way that independent development efforts are kept
separate from each other within a repo.  A commit is a unit of work that is
saved into a repository on a particular branch; commits are somewhat similar to
check-ins in other source control systems.*

You're now ready to begin working on the project.  But before you start patching
code, adding tests, developing new features, or improving documentation, you
should add a branch.  The idea with branches is that you can work on code
without ever being obligated to merge your changes into the main code branch.
Also, getting in to the habit of using branches means you can very easily put
aside new work and switch back to an older branch if necessary.

If you look in the upper-right hand corner of the GitHub for Windows app (to the
right of the sync button), there should be a branch icon which will say either
"master" or the name of another branch in the repo.  Click on the branch button
and type in the name "MyNewFeature" and hit Enter.  You should notice that the
text "MyNewFeature" now appears next to the branch icon.  This means that you
are now operating on the "MyNewFeature" branch which is independent from the
previously selected branch.  Note that creating a branch was not difficult and
there wasn't any expensive file copy operation involved.  Also note that you
didn't even have to talk to GitHub to do this; Git is a decentralized source
control system and operations mostly take place locally until they are
synchronized with the server.

Click the "gear" icon in the top-right and select "Open in Explorer".  Create a
new text file in that folder called "ThisIsMyNewFeature.txt".  Put **at least
three lines** of random text in the file, and save it.  Switch back to GitHub
for Windows.  You should see in the upper-left that there are "uncommitted
changes".  Click the button labeled "show".

Listed on the right-hand panel, you should see the name of the text file that
you created.  You should be able to see its content by clicking the "twisty"
adjacent to the file name.  (If you don't see the file, the TXT extension might
be ignored by the project - try renaming to .js or .md.)  Since it's a new file,
each line in the text file will be highlighted in green to indicate addition.
Ensure that the checkbox next to the file name is checked, type a commit message
such as "Added new feature text file" in the field on the upper-left, and then
click the "commit to MyNewFeature" button.

You've now successfully committed code to your branch!  The commit should now
appear in the history list on the left above the historical commits made by
other users.  Now, switch back to the same text file using your text editor and
modify **one** of the lines (in whatever way, as long as it's different) and add
**one** new line with new random text.  Switch back to GitHub for Windows, and
you should now see that the removed lines are highlighted in a salmon color and
the added lines are again highlighted in green (Git considers a modified line to
be deleted and re-added in its new form).  Commit this file by adding a message
again (such as "edited the feature content"), and clicking the commit button.

So far, you've made two commits to your local repository.  You may have noticed
that the commits are listed as "unsynced commits" in GitHub for Windows.  This
is because the changes still only reside on your local machine.
