   This simple set of functions allows you to easily create menus and retreive user choices from your shell scripts, both using items that you specify, as well as dynamically, using the output of commands. Two functions are provided:
     * createmenu, uses a propperly formatted selection of choices, see below
     * createdynamicmenu, constructs the menu based on command output, one choice per line, i.e. ls
   The format of menus is as follows:
   "title"
   "item hotkey one" "item one text" "item n hotkey" "item n text"
   Note: when generating your menus, make sure to use the -n option to echo, to avoidincorrect formatting. If you prefer the script to handle the quite literal dirty work of getting your options in the correct format, you can place
   your options, line by line, in a temp file, and do:
   createdynamicmenu cat /path/to/your/temp/file
   The following variables are returned:
     * choice: stores the hotkey of the choice that the user selected, if in doubt, use this when making your decisions, since each choice is unique.
     * itemname: stores the name of the item that the user selected
   Note that while waiting for input, all jobs that are not backgrounded are blocked while the menu is displayed waiting for user selection.
