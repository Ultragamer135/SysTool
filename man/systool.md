% SYSTOOL(1)
% Eli Nero (elinero27@gmail.com)
% March 2021

# NAME
SysTool - A collection of helpful tools, gadgets, customizations, and fixes for Linux and Bash

# SYNOPSIS
**systool**
**systool** -[*hvV*] \
**systool** -C *COMMAND* \
**systool** *OPTIONS* \

# DESCRIPTION
A collection of helpful tools, gadgets, customizations, and fixes for Linux and Bash.

# OPTIONS
If no option is specified, **SysTool** does not execute any actions. Otherwise, **SysTool** handles the options in the order they were given. If **SysTool** is ran with the options -V -f -v, **SysTool** will first be set to be verbose, then run the file explorer tool in verbose mode, then print the version info in verbose mode. However, if ran with the options rearranged in the order -v -V -f, **SysTool** will first print the version info in non-verbose mode, then be set to be verbose, then run the file explorer tool in verbose mode. This can be important if you want some functions to be ran in non-verbose mode while having other actions ran in verbose mode. Options can also be chained together. For example, the options -V -f -v can be shortened to -Vfv because none of these options require arguments. The options -b -i -C "ls" -n -v cannot be shortened into one long options string. However, -b -i -C "ls" -n -v can be shortened to -biC "ls" -nv because -b and -i do not require arguments, -C requires an argument but is still an one-letter option, and neither -n or -v require arguments. However, -bic "ls"-nv would not work because -nv would be handeled as part of "ls", causing **SysTool** to handle the options as -b -i -C "ls"-nv which would then be handled as -b -i -C "ls-nv". It is reccomended to surround any arguments with quotes so your shell doesen't expand the arguments.

## Common options

**-h**
: Displays basic help and options.

**-v**
: Displays version info

**-V**
: Sets **SysTool** to be verbose. **SysTool** displays extra info when verbose. This is mainly for developers, but can also be used to get more info from actions.

**-C** *COMMAND*
: Runs COMMAND as **SysTool**.

**-N**
: Runs Neofetch by default. Command to run can be customized. This can be helpful for showing system info on boot.

## Actions
Many options make **SysTool** run actions, which are the various functions provided by **SysTool**. Actions include tools, gadgets, and info actions. These are listed below.

### Info

**-b**
: Shows a banner using figlet. This is the **SysTool** banner by default, but you can also set custom banner text.

**-i**
: Shows info about the current user and session.

### Tools

**-f**
: Opens a file explorer UI. The up and down arrow keys on the keyboard navigate between items, and enter opens the current directory or file.

**-t**
: Opens a list of tmux sessions, and allows you to connect to one. If no session is selected, a new tmux session is started.

### Gadgets

**-n**
: Lists the devices on your network. Sudo privledges are required to use this gadget.

**-s**
: Displays a list of current sessions on this PC.

# EXIT VALUES
**0**
: Program run was succesful

**1**
: An error occured.

# CAVEATS
If the -V option is provided to set **SysTool** to be verbose, but other options come before it, the options specified before -V are not ran in verbose mode. For example, using the options -Vfv will make **SysTool** be set to verbose mode, then run -f in verbose mode, then -v in verbose mode; while using the options -fVv will make **SysTool** run -f in non-verbose mode, turn on verbose mode, and run -v in verbose mode.

# BUGS
The bug tracker can be found on the SysTool Github page (https://github.com/UsernameNotAvalible/SysTool)

# AUTHORS
Main Developer: Eli Nero (elinero27@gmail.com)
Check the AUTHORS file in the systool directory.