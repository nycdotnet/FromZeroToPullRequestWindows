How to submit code to a GitHub project on Windows
=================================================

*From Zero to “Pull Request”*

This guide is intended for developers on the Windows platform who have not
previously used Git or GitHub, but who do have basic knowledge of at least one
other source control system.  This guide is different from other guides because:

-   It is specifically for developers who use Windows

-   It tells you what to do step-by-step and includes definitions of the basic
    terms

-   It prioritizes "the simple way for the common circumstance" over "every
    possible way for every possible circumstance"

The reader is strongly encouraged to learn more about Git and GitHub from any of
the many other wonderful guides out there after having successfully navigated
this guide.  **This guide is only intended to be the bare minimum to get you
started!**

Note that this guide assumes that:

-   You are using Windows 7 or higher

-   You have administrative rights on your machine

-   You have some sort of text editor available (Notepad is fine)



Installing Stuff and Registering
--------------------------------

[^]: Necessary terminology: Git is the source control system, GitHub is the web
site.  *You can use Git without GitHub, but not GitHib without Git.*

Go to <https://windows.github.com> and download the “GitHub for Windows” client.
Install it.  This gives you a Windows UI suitable for most Git operations and a
PowerShell-based Git environment.

Once the installation is complete, you will have to log in to GitHub.
Registering and contributing to open source projects on GitHub is free.

-   Click the "Sign up" link in the GitHub for Windows application and then
    follow the directions to sign up for a free account via the web site.

-   Note that your GitHub username is always public, but *your email address can
    public or private* depending on how you set the options (see next step).

Once you've registered on the site, switch back to GitHub for Windows, enter
your GitHub username and password, and log in.  On the Configuration tab, enter
your full name and email address.

>   If you are concerned about privacy, you can put your GitHub username instead
>   of your full name and "*username*@users.noreply.github.com" instead of your
>   email address; you will also want to visit
>   <https://help.github.com/articles/keeping-your-email-address-private> and
>   follow the instructions there.

After all that, you can click on the Dashboard link and you should be ready to
start using Git and GitHub.



Forking a Repo
--------------


