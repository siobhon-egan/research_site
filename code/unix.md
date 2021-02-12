# Unix

source: `{{ page.path }}`

<span class="badge badge-info">A brief guide to bash code from the Unix terminal</span>

## Get started

The following install insctructions are courtesy of [Software carpentry lesson - the Unix Shell](http://swcarpentry.github.io/shell-novice/setup.html)

**Linux**

The default Unix Shell for Linux operating systems is usually Bash. On most versions of Linux, it is accessible by running the [(Gnome) Terminal](https://help.gnome.org/users/gnome-terminal/stable/) or [(KDE) Konsole](https://konsole.kde.org/) or [xterm](https://en.wikipedia.org/wiki/Xterm), which can be found via the applications menu or the search bar. If your machine is set up to use something other than Bash, you can run it by opening a terminal and typing `bash`.

**macOS**

For a Mac computer running macOS Mojave or earlier releases, the default Unix Shell is Bash. For a Mac computer running macOS Catalina or later releases, the default Unix Shell is Zsh. Your default shell is available via the `Terminal` program within your Utilities folder.

To open `Terminal`, try one or both of the following:

* In Finder, select the Go menu, then select Utilities. Locate `Terminal` in the Utilities folder and open it.
* Use the Mac ‘Spotlight’ computer search function. Search for: `Terminal` and press **Return**.

To check if your machine is set up to use something other than Bash, type `echo $SHELL` in your terminal window.

If your machine is set up to use something other than Bash, you can run it by opening a terminal and typing `bash`.

*Reference:* [How to Use Terminal on a Mac](How to Use Terminal on a Mac)

**Windows**

Computers with Windows operating systems do not automatically have a Unix Shell program installed. In this lesson, we encourage you to use an emulator included in Git for Windows, which gives you access to both Bash shell commands and Git. If you are attending a Software Carpentry workshop session, it is likely you have already received instructions on how to install Git for Windows.

Once installed, you can open a terminal by running the program Git Bash from the Windows start menu.

Other solutions are available for running Bash commands on Windows. There is now a Bash shell command-line tool available for Windows 10. Additionally, you can run Bash commands on a remote computer or server that already has a Unix Shell, from your Windows machine. This can usually be done through a Secure Shell (SSH) client. One such client available for free for Windows computers is PuTTY. See the reference below for information on installing and using PuTTY, using the Windows 10 command-line tool, or installing and using a Unix/Linux emulator.

*Reference:* [Git for Windows](https://git-for-windows.github.io/) - Recommended

For advanced users, you may choose one of the following alternatives^[Please note that commands in the Windows Subsystem for Linux (WSL) or Cygwin may differ slightly from those shown in the lesson or presented in the workshop.]:

* [Install the Windows Subsystem for Linux](Install the Windows Subsystem for Linux)
* [Using a Unix/Linux emulator (Cygwin) or Secure Shell (SSH) client (Putty)](http://faculty.smu.edu/reynolds/unixtut/windows.html)
