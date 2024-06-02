# Get-help-in-the-command-line
As a security analyst, it's important to know where to find answers. Linux offers help through the command line. In this lab, you'll use the man, whatis, and apropos commands to get information on other commands and how they work. This knowledge will be valuable in your role as a security analyst.

## Table of contents

1. [Project description](#scenario)
2. [Learn more about commands](#morecomands)
3. [Change file permissions](#permissions)
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

Run the `whatis` command to get a short description of `cat`.
>analyst@b705131443c6:~$ `whatis cat`  
>cat (1)              - concatenate files and print on the standard output

Next, imagine that you want more details about `cat` and all of its options.

Use the man command to get more details about `cat`.
The man command returns a general description of `cat` and information about each of its options:

>analyst@b705131443c6:~$ `man cat`  
>CAT(1)                         User Commands                         CAT(1)
       
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
