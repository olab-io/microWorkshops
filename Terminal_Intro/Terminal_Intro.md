# Introduction to the Terminal

## Introduction

> "[A shell] is a command processor, typically run in a text window, allowing the user to type commands which cause actions."

_(via [wikipedia][11])_

A command shell is an alternative to a Graphical User Interface (GUI) and is sometimes referred to as a Command Line Interface (CLI).

#### Advantages of a CLI
- Sometimes they are faster.  While (arguably) more intuitive, a GUI requires many gestures and clicks to do simple tasks, such as move files from one location to another.  Often the same action can be completed faster, with minimal movement using only one text command in a CLI.
- A strong grasp of the command line will allow a user to easily automate tasks.  For instance, deep inside of Adobe After Effects, there is a command line program called `aerender` that is capable of rendering Adobe After Effects compositions (or a single frame of a complex composition).  Using command line automation tools, a large render job can be shared between computers. 
- Access to robust, complex command-line tools like `youtube_dl` can speed up the creative process.

#### Disadvantages of a CLI
- Some tasks are inherently visual / graphical and are not possible using a CLI.

## Required Software

### OSX

- `/Applications/Utilities/Terminal.app`

### iOS

- [Prompt][1]
- [iSSH - SSH / VNC Console][2]

### Linux

- Built in.

### Android

- [JuiceSSH][6]

### Windows

While windows has a `command.exe` and a `cmd.exe` prompt, these are not equivalent to a traditional `bash` terminal.  For a `bash` experience, try:

- [MinGW][4]
- [Cygwin][5]

## The Shell Environment

- What is a "command shell"?  
    - Typical shell types `bourne shell, bash, csh, ...`
    - A [comparison][10] of command shells. 
- Environmental Variables
    - `PATH`, etc. 

### Bash Files
```
man bash 
...

/bin/bash 
        The bash executable
/etc/profile
        The systemwide initialization file, executed for login shells
~/.bash_profile
        The personal initialization file, executed for login shells
~/.bashrc
        The individual per-interactive-shell startup file
~/.bash_logout
        The  individual  login shell cleanup file, executed when a login
        shell exits
~/.inputrc
        Individual readline initialization file
...
```

## File System Interaction

When you are on the command line, all commands are issued relative to your _working directory_.  One might think of the _working directory_.  So for instance, if you edit a file and save it, it will be saved in your current _working directory_.

You can display your current _working directory_ by issuing the `pwd` command.

- `pwd` Display the current working directory.
- `cd [path]` Display the current working directory.
- `ls [path]` Display a list of the files and folders in the current directory.
  - `-l` List format
  - `-h` Human readable file sizes.
  - `-a` List ALL files including "hidden" files beginning with `.`
  - e.g. `ls -lah [path]`

Absolute paths begin with `/` or `C:\`, etc.
Relative don't begin with `/` or `C:\`. 

- `.` The current directory.
- `..` The parent directory.
- `../..` The grand-parent directory.
- `../../..` The great-grand-parent directory.

Most programs such as `ls` can receive either absolute or relative paths.

- `mkdir [TARGET]`  Make a directory.
- `rmdir [TARGET]` Remove a directory (must be empty).
- `rm [FILE]` Remove a file.  There is no trashcan.
- `rm -r [FOLDER]` Recursively remove folders.  _Very dangerous.  Be careful._

## Editing Plain Text Files

- `nano`
- `vi` _Only the commands to exit_
  - `ESC` to exit insert mode.
  - `:` to enter command mode.
  - `q!` to quit without saving changes.
  - `wq` to save changes and quit.  
  - The vi game.
- `emacs` _Only the commands to exit_
  - `CTRL+x` then `CTRL+c`     


## Viewing plain text files
- `cat` Concatenate files or dump files to output.
- `more` Create a paged view of a long file or output.
- `tail` View the end of a file.
  - `-f` Follow the end of a file (useful for following log files that append to the end of the file).

## System Info
- `top` List the top processes.  Like ActivityMonitor.app on OSX.
- `ps` List all current processes.  Returns process ids.
- `kill [PID]` Kill a process that has a process id.  Like "Force Quit" on OSX.

## Communication
- `ssh username@hostname` or `mosh username@hostname`
  - Once you are in, you have a terminal on the other end.

## Filtering and Counting
- `grep`
  - `ps aux | grep Finder` See if an application with a name called `Finder` is running.

## Net
- `curl [url]`
  - `-O` Specify an output filename.  Will pass the data to the standard output without it.
  - e.g. <http://cloudmade.com/documentation/map-tiles>
    - `curl -O http://b.tile.cloudmade.com/8ee2a50541944fb9bcedded5165f09d9/1/256/15/17599/1074[5-9].png`

- `ping [IP or HOSTNAME]` Contact a machine online to see if they are there ...
- `host [HOSTNAME]` DNS Hostname lookup.
- `dig [HOSTNAME]` DNS Hostname lookup.

## Standard input and output

### Pipes

- `|` A pipe is a way to "pipe" input from one program into another program.
  - e.g. `cat myFile.txt | more`  

### Redirection

- `>` A redirect "redirects" output to a file or a stream.
  - Note: `>` will overwrite the target file completely.  To append output, use `>>`.

More (<http://www.tldp.org/LDP/abs/html/io-redirection.html>)

### Other Useful Utilities

- Many available for OSX [Homebrew](http://brew.sh/).
- [`youtube-dl`](http://rg3.github.io/youtube-dl/) Download YouTube videos.
- `ffmpeg` Convert videos like a champ.
- [Handbrake CLI](https://trac.handbrake.fr/wiki/CLIGuide) 

## Automation

- `source [FILE]` Run each line of a file as if it is a command. 
- `bash scripting`



[1]: https://panic.com/prompt/
[2]: https://itunes.apple.com/us/app/issh-ssh-vnc-console/id287765826?mt=8
[4]: http://www.mingw.org/wiki/YS3S
[5]: http://www.cygwinom/
[6]: https://play.google.com/store/apps/details?id=com.sonelli.juicessh&hl=en
[10]: http://en.wikipedia.org/wiki/Comparison_of_command_shells
[11]: http://en.wikipedia.org/wiki/Bash_(Unix_shell)