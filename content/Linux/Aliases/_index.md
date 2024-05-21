+++
author = "Albert Milewski"
title = "Aliases"
date = "2024-05-20"
description = "A comprehensive guide to Access Control Lists (ACLs) in Linux, their usage, options, examples, and best practices."
tags = [
    "linux",
    "aliases",
    "shortcut",
]
categories = [
    "system administration",
    "linux",
]
series = ["Linux Guides"]
aliases = ["linux-aliases"]
+++


## Introduction
A variable is a name that stands in for a value. Similarly, the shell has names that stand in for commands, known as aliases. Aliases allow you to create shortcuts for long or frequently used commands, making your work more efficient.

## Defining an Alias
To define an alias, invent a name and follow it with an equals sign and the command. Here are some examples:

```sh
$ alias g=grep      # A command with no arguments
$ alias ll="ls -l"  # A command with arguments: quotes are required
```

Run an alias by typing its name as a command. When aliases are shorter than the commands they invoke, you save typing time:

```sh
$ ll  # Runs "ls -l"
-rw-r--r-- 1 smith smith 325 Jul 3 17:44 animals.txt

$ g Nutshell animals.txt  # Runs "grep Nutshell animals.txt"
horse Linux in a Nutshell 2009 Siever, Ellen
donkey Cisco IOS in a Nutshell 2005 Boney, James
```

## Important Notes
- Always define an alias on its own line, not as part of a combined command. Refer to the `man bash` for technical details.
- You can define an alias that has the same name as an existing command, effectively replacing that command in your shell. This practice is known as shadowing the command.

For example, suppose you like the `less` command for reading files but want it to clear the screen before displaying each page. This feature is enabled with the `-c` option. You can define an alias called `less` that runs `less -c`:

```sh
$ alias less="less -c"
```

Aliases take precedence over commands of the same name, so you have now shadowed the `less` command in the current shell. Precedence details are explained in the “Search Path and Aliases” section.

## Listing Aliases
To list a shell’s aliases and their values, run `alias` with no arguments:

```sh
$ alias
alias g='grep'
alias ll='ls -l'
```

## Additional Tips
- Aliases can be made permanent by adding them to your shell’s startup files (e.g., `~/.bashrc` or `~/.bash_profile` for Bash).
- To remove an alias, use the `unalias` command followed by the alias name:
  ```sh
  $ unalias ll
  ```

## Conclusion
Aliases are powerful tools in Linux that enhance productivity by reducing the amount of typing required for frequently used commands. By understanding and utilizing aliases effectively, you can streamline your command-line operations and improve efficiency.
