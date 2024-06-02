# Get-help-in-the-command-line
As a security analyst, it's important to know where to find answers. Linux offers help through the command line. In this lab, you'll use the man, whatis, and apropos commands to get information on other commands and how they work. This knowledge will be valuable in your role as a security analyst.

## Table of contents

1. [Project description](#scenario)
2. [Learn more about commands](#morecomands)
3. [Explore the useradd command](#useraddcommands)
4. [Change file permissions on a hidden file](#permissions2)
5. [Change directory permissions](#permissions3)
6. [Summary](#summary)

## Scenario <a name="scenario">
In this scenario, you have to find more information about commands that you need to use. You also need to discover which command to use to perform a certain task.

Here’s how you’ll do this task: First, you’ll explore a few commands you can use in the shell to learn more about other commands. Next, you’ll find an option you need to add to a command. Third, you’ll use a command to get a brief description of commands so you can identify their differences. Finally, you’ll identify the command you need to perform a task.

It's time to get ready to explore some of the Linux help resources!

## Learn more about commands <a name="morecomands">
You need to explore a few commands you can use in the shell to learn more about the functionality of other commands.

First, imagine you can’t quite remember what the cat command does and want a quick reminder.

- Run the `whatis` command to get a short description of `cat`.
>analyst@b705131443c6:~$ `whatis cat`  

       cat (1)              - concatenate files and print on the standard output

Next, imagine that you want more details about `cat` and all of its options.

- Use the `man` command to get more details about `cat`.
The man command returns a general description of `cat` and information about each of its options:

>analyst@b705131443c6:~$ `man cat`  

       CAT(1)                         User Commands                         CAT(1)
       
       NAME
              cat - concatenate files and print on the standard output
       SYNOPSIS
              cat [OPTION]... [FILE]...
       
       DESCRIPTION
              Concatenate FILE(s) to standard output.
              With no FILE, or when FILE is -, read standard input.
              -A, --show-all
                     equivalent to -vET

              -b, --number-nonblank
                     number nonempty output lines, overrides -n

              -e     equivalent to -vE

              -E, --show-ends
                     display $ at end of each line

              -n, --number
                     number all output lines

              -s, --squeeze-blank
                     suppress repeated empty output lines

              -t     equivalent to -vT

              -T, --show-tabs
                     display TAB characters as ^I

              -u     (ignored)

              -v, --show-nonprinting
                     use ^ and M- notation, except for LFD and TAB

              --help display this help and exit

              --version
                     output version information and exit
       --More--

- Press Q to exit this manual page.

Now, imagine you’ve remembered there’s a command that prints just the first part of a file, but you can’t remember the exact command. The `apropos` command is useful in these instances. You can use keywords with `apropos` to find a command.

- Use `apropos` to find a command that returns the first part of a file:

>analyst@b705131443c6:~$ `apropos -a first part file`

       head (1)             - output the first part of files

Note: There is no right and wrong when using apropos in terms of keywords. Think of it as a very focused search. It will only return commands that correspond to keywords you supply. Keep trying if the first returned command does not provide what you need. Also, keep in mind that using the -a option will limit results to only those commands that match all keywords supplied.

## Explore the useradd command <a name="useraddcommands">
Imagine that you want to set the expiration date for a temporary user account. You know that you need to use the useradd command for this, but you’re not quite sure how to complete the task. You realize it might involve adding an option to the command.

Use the most appropriate Linux command to get help on the `useradd` command and learn more about all of its options.
Note: You can output more information one line at a time by pressing the ENTER key or output the next page of the manual by pressing the space bar.

> analyst@b705131443c6:~$ `man useradd`

       USERADD(8)               System Management Commands              USERADD(8)

       NAME
              useradd - create a new user or update default new user information

       SYNOPSIS
              useradd [options] LOGIN
       
              useradd -D
       
              useradd -D [options]
       
       DESCRIPTION
              useradd is a low level utility for adding users. On Debian,
              administrators should usually use adduser(8) instead.

              When invoked without the -D option, the useradd command creates a
              new user account using the values specified on the command line plus
              the default values from the system. Depending on command line
              options, the useradd command will update system files and may also
              create the new user's home directory and copy initial files.

              By default, a group will also be created for the new user (see -g,
              -N, -U, and USERGROUPS_ENAB).

       OPTIONS
              The options which apply to the useradd command are:

              -b, --base-dir BASE_DIR
                  The default base directory for the system if -d HOME_DIR is not
                  specified.  BASE_DIR is concatenated with the account name to
                  define the home directory. If the -m option is not used,
                  BASE_DIR must exist.
       
                  If this option is not specified, useradd will use the base
                  directory specified by the HOME variable in
                  /etc/default/useradd, or /home by default.

              -c, --comment COMMENT
                  Any text string. It is generally a short description of the
                  login, and is currently used as the field for the user's full
                  name.

              -d, --home-dir HOME_DIR
                  The new user will be created using HOME_DIR as the value for the
                  user's login directory. The default is to append the LOGIN name
                  to BASE_DIR and use that as the login directory name. The
                  directory HOME_DIR does not have to exist but will not be
                  created if it is missing.

              -D, --defaults
                  See below, the subsection "Changing the default values".

              -e, --expiredate EXPIRE_DATE
                  The date on which the user account will be disabled. The date is
                  specified in the format YYYY-MM-DD.

                  If not specified, useradd will use the default expiry date
                  specified by the EXPIRE variable in /etc/default/useradd, or an
                  empty string (no expiry) by default.

              -f, --inactive INACTIVE
                  The number of days after a password expires until the account is
                  permanently disabled. A value of 0 disables the account as soon
                  as the password has expired, and a value of -1 disables the
                  feature.

                  If not specified, useradd will use the default inactivity period
                  specified by the INACTIVE variable in /etc/default/useradd, or
                  -1 by default.

              -g, --gid GROUP
                  The group name or number of the user's initial login group.
              --More--
