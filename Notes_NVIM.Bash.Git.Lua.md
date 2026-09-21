##  Some Notes

```bash
#Nvim config File
nvim ~/.config/nvim/init.lua
:reset #to reload

#To open the Tmux Confuguration
nvim ~/.tmux.conf

#to reload
tmux source-file ~/.tmux.conf

https://github.com/local-sailor/NeoVim-Bash-Git-Diaries
```



## Bash Commands

```vim

        "Terminal CLI Input
Ctrl + A: Move the cursor to the very beginning of the line.
Ctrl + E: Move the cursor to the very end of the line.
Alt + B: Move backward one full word at a time.
Alt + F: Move forward one full word at a time
ctrl + B or F: to max one word at a time => Works in WezTerm
          
          "Navigation
cd folder/      #move into a folder "current directory"
cd ..           #move backwards out of a folder
ls              #see all the files and folder
pwd             #show you current location "working directorey"
cd ~            #takes you to the home directory usually your user profile



        "Mac OS Cli inputi
Alt + left right    to move by words => Works in Warp and MacOs Terminal
                    note: Tmux on Warp was blocking this so i had to keymap it again. 
Ctrl + L:           Clear the terminal screen without losing your place.
Ctrl + C:           Cancel or kill the currently running command to give you a clean
Ctrl + U:           Cut everything from the cursor backward to the start of the line.
Ctrl + K:           Cut everything from the cursor forward to the end of the line.

        "Vim Normal Mode
Ctr U or D      Up or Down by a page
enter           To go to the front of the next line
W or E          Move forward by one word (Left or Right end)
0               Move the begining of the line
Shift $         Move to the begining to the end of the line
Shift + A       Type/Inser at back of the front of the line
Shift + I       Type/Insert at the front of the line:
*               To target a word, "n" to move its next instance prev "shift n", ":noh" to clear it
/"word"         To search for a word, "n" to move through the instance       
gc              To in visual "visual mode" to comment out a passage
gg G            To get to the top of the document G to the end
dGG dgg         To cut everything from here to the bottom  from here to the 
%+y             Yank what you just delete
"+yy "+dd       To yank a line or yank and delete a line
dd p            Things that you delete/yank in Vim is can be pasted by P but it isnt in your clip board
:50,100d+       Starting from "line 50 (inclsuive)" delete all the words "until the word before line 100 (exclusive)" PLACE IN TO CLIPBOARD
                also works for y for "yank" take off the "+" if you dont need it to affect your clipboard
shift ~         shift tilda (~) let's you capitalise the letter under the typing cursor. Toggle: repeat for the opposite.
                VISUAL MODE: everything highlighted is capitalise. Use $, W, E. 
g~w             Capitalises to the whole section with the current paranthesis
g~it            Think of i t as "inner tag" capitalises everything within the container like brackets [ ] for files only i think. 
=G              To fix inedtation inedentation from the cursor down. gg to get to the top of the file and fix the whole file.
m a             m bookmarks the current line in a 
'a              to jump to the line that was bookmarked the current line
m A             set A to book mark the line and the file letting you reopen the file even when you close it
'A
:40 enter       To jump to line 40                          '
40G             in normal mode to the same thing but quicker. 
J               Capital J merges the next line with this line with a spacee in between
gJ              merge the next two lines with no spaces in between.




Ctrl + W or o: Delete by entire words, backwards or forwards must be in insite mode

Ctrl + Y: Paste (yank) back whatever you just cut using  Ctrl + U or  Ctrl + K.

Ctrl + T: Swap the last two characters near your cursor (great for fixing quick typos).

Tab: Autocomplete the name of a command, file, or directory path.

Ctrl + R: Open a reverse history search. Type a few letters of an old command to pull it up instantly.

Up / Down Arrows: Cycle through your recently used commands.

!!: Re-run the exact last command you typed. a


mkdir -p app/src/components             #Create nested/parent subdirectories
    mkdir photos videos documents   #Create multiple directories at once

touch notes.md   #to make an md file name notes
touch file1.txt file2.txt file3.txt #make multiple files at once
open  notes.md file1.txt file2.txt file3.txt #opens multiple files
open .   #opens the folder or launches finder

mv name1.md name2.md    #to rename a word       -i prompts for files deletions =n bands any file deltions
mv file.md  location/newLocation/  #move a file same for moving folders
cp -a directory/olderFolder/.  directory/newFolder          Copies all the files in old folder and pastes them into new folder
                                                            -a  means to copy all files recursively preserve things like promotions, hidden files, symbolic links
                                                            -R or -r   also copies everything recursively but doesn't include hidden files and doesn't preseve permissions
                                                            .  the fulstop means to copy all the files in the oldFolder

echo "Hello World"  #Print text to the screen
echo "Hello World" > greeting.txt   #Create a file and write text to its
echo "Add this line to the bottom" >> greeting.txt  #Append text to the end of an existing file
echo -e "First Line\nSecond Line" #Print text with a new line character

cd folder/      #move into a folder "current directory"
cd ..           #move backwards out of a folder
ls              #see all the files and folder
pwd             #show you current location "working directorey"
cd ~            #takes you to the home directory usually your user profile

#Deleting
-r or -R (Recursive): Deletes a directory and all of its contents (files, subfolders, hidden files). Required to delete folders with rm.
-f (Force): Ignores nonexistent files and prompts, deleting everything silently without asking for permission.
-i (Interactive): Prompts you for confirmation before deleting every single file. Excellent for safety.
 rm log.txt   #Delete a single file
 rm photo.jpg style.css script.js   #Delete multiple files at once
 rm -rf project_folder  #Delete a folder and everything inside it (Crucial flag combination)
 rm -i sensitive_data.csv   #Safely delete with a confirmation prompt
 rmdir empty_backup_folder   #rmdir command strictly deletes folders that are completely empty. It acts as a safety mechanism because it will refuse to delete a folder if there are any files inside it.
 rm *.md                    # removes all the markdown files in the folder

#Acessing the cliboard
Mac     spotilight + comand 4
Windows Windows + v

```

### Cat

```bash
Primary used for display file contents, combine multiple files, and create new files directly from the terminal.
    -n (Number): Prepend line numbers to all output lines.
    -b (Number non-blank): Prepend line numbers only to lines that are not empty.
    -s (Squeeze blank): Compress multiple consecutive empty lines into a single blank line.
    -E (Show ends): Display a $ character at the end of every line (useful for finding trailing spaces).
cat notes.txt #View the contents of a file

cat part1.txt part2.txt #Combine (concatenate) multiple files and display them

cat > todo.txt #Create a new file from scratch (Type your text, then press Ctrl + D to save and exit)

cat file1.txt file2.txt > combined.txt #Append text to an existing file (Adds text to the end without overwriting)

cat file1.txt file2.txt > combined.txt #Merge multiple files into a brand new file

cat -n script.sh #View a file with line numbers

#Usin Cat to type a whole script
# use EOF so special characters like $ do not trigger th terminal
cat > tests/test_helloworld.py <<'EOF'
from helloworld import HelloWorld


def test_message_is_stored():
    assert HelloWorld().message == "Hello, World!"


def test_say_hello_prints_message(capsys):
    HelloWorld().say_hello()
    assert capsys.readouterr().out == "Hello, World!\n"
EOF

```

### Markdown Images

```vim

"web and local images
![Markdown Logo](https://github.io)
![My Screenshot](screenshot.png)
![Graph Design](./images/graph.jpg)

"With hover 
![Alt Text](screenshot.png "This is a hover tooltip")                        

"Html works and it offers dynamic sizing where markdown notation does not.
<img src="./images/graph.jpg" alt="Graph Design" width="300" />
    " Width is locked to 300 but height is dynamic.

<img src="photo.jpg" width="50%" alt="Description">                 

"To centre. 
<div align="center">                                                          
  <img src="diagram.png" width="400" alt="Centered Diagram">                
</div>

"With link. 
<div alight="center">
<a href="https://example.com">                                          
  <img src="button.png" alt="Click Here">
</a>
</div>

"More examples
<img src="images/photo.jpg" width="300" alt="My Photo"> 
<img src="assets/project/diagrams/chart.png" width="500" alt="Project Chart">


                                                        
```
### Permissions / CHMOD

```bash

- Three groups
-- User = Admin, Owner
-- Group
-- Others

To see
ls -l 

Less compact
ls -la

- read r = 4
- write w = 2
- execute x = 1

4+2+1 = 7   for everything
4+2 = 6     for read write everything
4+1 = 5     for read and run scripts only
4           for readonly
0           no access


chmod 755 file.sh
- User/Group/Others
- User/Admin can do everything 7
- Group can read and run the file 5
- Guests or the public can also read and run the file 5


Scripts
Make a scrip executable
chmod +x script.sh

Alternate way to give permisions

Gives user and group + read write acess
chmod ug+rw document.txt

Takes - write access from others
chmod o-w file.txt


-u g o a: user group others all
- + -   add or remove access
-r w e  read write execute

Modifying Ownership

Start with the colon :  
(left of colon = user) : (right of colon is group)

Change owner and group
chown new.username:new.groupname file.txt

Change group only
chown :new.groupname file.txt

Change owner only
chown new.username file.txt
```
### Terminal Commands for development

```vim

    General
/n  new line
/t  tab
\   to hande space in CD names
    cd there\ is\ a\ space\ here/

    Python
ruff check .    #check for an linting errors, helps standardise code bases and keep diffs standard
python3 -m pytest -v     #a common option for running python test files 
                         -m  targets and runs an internal library module as a script "pytest" is the target
                         -v  is not necessary but it makes the output of pytest more descriptie usually it's  ' . ' for pass and ' F ' for fail

    in C
int a = 42
int b = 84
printf("%i and %i", a, b); 
#wil print the i for integers in chronological order


```


## VIM and NVIM Commands

```vim
ctrl + l        under oil file explorer to reset
:!shell command         for quick shell commmands
:terminal               to open a terminal within nvim
g.                      in nvim oil to see hidden files

u to undo
ctrl + r to redo

Delete an entire file
dd
dG:

        Insert Mode
Ctrl w to delete by word
Ctrl u to delete from the cursor to the line
ctrl t or d     indent and unindent the current line

            Yanking from Vim
"+yy — Yanks the entire current line to your system clipboard
"+y — Yanks the current visual selection to your system clipboard 
      "(press v or V first to highlight text, then type "+y).
"+p — Pastes text from your system clipboard into Vim.
gg"+yG          - gg takes you to the top, "+ all in the range, + add to (clipboard), y yank, G range to the end of the file 
:let @+ = @" "- To move text you have already yanked inside Vim into your system clipboard



v to visually inspect and highlight a passage
y to yank what you highlighted
dd to delete a line
yy to yank a line

ctrl+d one page window
ctr+u one page up
ctrl+w to delete by word

    Swap c with y for yank, v for select, d for delete
ciw      deletes word you're currently on puts yu into inerts mode to type "change inner word"
cw       delete the portion of the word from your course ot the end "change word"
caw      deletes the word + the spaces around it and goes into insert mode "change around word"
cib      change inside [ block braces
ciB      change inside { curcy braces
ca(      change around paranthesis
    More Intuitive approach
you can also use ci[ and ci{ instead of b and B
ci[
ci{
ci<
ci"
ci<
ci< 
cip for paragraph!
these work with ca as well

` in oil to set you cd into your current oil folder

ctrl w + - or +      to increase the split size
ctrl w + w           to cycle through different dinows, h,j,k,l too
zh or zl             to pan left or right (note their keyboard postions)
zH or zL             for biggeri

esc 0 i              to go to the start of the line
esc A                to go into i mode at the end of the line
/typeword enter n    forward slash your word to search it then n to cycle

ZZ                   for quick exit with saving
ZQ                   quit without saving note usage of shift for capitals

/Editing a File
]d                   Move to the next flagged erroed code
[d                   Move to the previous flagged error code
:Telescope diagnostics      Brings up an overhead of Flags/Errors on telescope 
Space f d                   Customer hot key for Telescope errors. Popular 
                            nvim plugs in don't mandate hotkeys but they should really have them.
:vim.diagnostic.ope n_float()

Aerial nvim plugin let's you cycle through functions and headings in a markdown or programming file
space a to launch the navigation panei
]h                      To jump between Markdown headings
[h                      
}}                      To jump between low lever functions(top end to low end) or headings
{{
[[                      To jump between high level functions (classes) 
]]


v i {                   highlight everything within the curly brace 
v i b

v i }                   highlight everything within curly braces
v i B

c i b or B              deletes everything within the paranthesis  

            "NVIM Suspendend Animation`"
Ctrl-z                      Will close NVIM and keep it alive in the background
                            this allows you to use the terminal
:fg                         When you are ready to return to nvim 




=G              To fix indentation inedentation from the cursor down. gg to get to the top of the file and fix the whole file.
%               Lets you jump between curly braces on the same indent line or on the other side matching. You  have to use shift.
ctrl z          closes vim but places it nvim in a suspended animation
    type fg         Enter. To return. 
g x             to open a link under the cursor. Woks on files too.
g f             samething to open a file
```

```vim
        "Vim Normal Mode"
Ctr U or D      Up or Down by a page
enter           To go to the front of the next line
W or E          Move forward by one word (Left or Right end)
0               Move the begining of the line
Shift $         Move to the begining to the end of the line
Shift + A       Type/Insert at back of the front of the line
Shift + I       Type/Insert at the front of the line
*               To target a word, "n" to move its next instance prev "shift n", ":noh" to clear it
/"word"         To search for a word, "n" to move through the instance       
gc              To in visual "visual mode" to comment out a passage
gg G            To get to the top of the document G to the end
dGG dgg         To cut everything from here to the bottom  from here to the 
%+y             Yank what you just delete
"+yy "+dd       To yank a line or yank and delete a line
dd p            Things that you delete/yank in Vim is can be pasted by P but it isnt in your clip board
:50,100d+       Starting from *line 50 (inclsuive)* delete all the words *until the word before line 100 (exclusive)* PLACE IN TO CLIPBOARD
                also works for y for "yank" take off the "+" if you dont need it to affect your clipboard
                yes need the comma
v shift ~       Shift tilda (~) let's you capitalise the leTter under the typing curso. NOTE: it's a toggle.
g~w             Capitalises to the whole section with the current paranthesis
g~it            Think of i t as "inner tag" capitalises everything within the container like brackets. 
=G              To fix inedtation inedentation from the cursor down. gg to get to the top of the file and fix the whole file.
m a             m bookmarks the current line in a 
'a              to champ the line of the bookmark
m A             to book mark the line and the file letting you reopen the file even when you closes it
'A
:40 enter       To jump to line 40
40G             in normal mode to the same thing but quicker. 
J               Capital J merges the next line with this line with a spacee in between
gJ              merge the next two lines with no spaces in between.


Ctrl + W or o: Delete by entire words, backwards or forwards must be in insite mode
Ctrl + Y: Paste (yank) back whatever you just cut using  Ctrl + U or  Ctrl + K.

Ctrl + T: Swap the last two characters near your cursor (great for fixing quick typos).

Tab: Autocomplete the name of a command, file, or directory path.

Ctrl + R: Open a reverse history search. Type a few letters of an old command to pull it up instantly.

/Running a Python Server/
Python3 server.py 8000         "Run a server at port 8000
Python3 % 8000

/Node.js server
npm run dev
npm start
```



| Category | Command | Action Description |
| ----- | ----- | ----- |
| **Document Navigation** | **`gg`** | Move cursor to the **very first line** of the file |
|  | **`G`** | Move cursor to the **very last line** of the file |
|  | **`w`** / **`b`** | Move forward / backward by **one word** |
|  | **`0`** (Zero) / **`$`** | Move cursor to the **start** / **end** of the current line |
| **Deleting & Cutting** | **`dG`** | Delete from **current line to the bottom** of the file |
|  | **`dd`** | Delete (cut) the **entire current line** |
|  | **`dw`** | Delete (cut) from the cursor to the **end of the word** |
|  | **`x`** | Delete the **single character** under the cursor |
| **Copying & Pasting** | **`yy`** | Copy (yank) the **entire current line** |
|  | **`p`** | Paste copied/deleted text **after** the cursor |
|  | **`P`** | Paste copied/deleted text **before** the cursor |
| **Modes & Editing** | **`i`** | Enter **Insert Mode** to type text before the cursor |
|  | **`o`** | Open a **new blank line below** and enter Insert Mode |
|  | **`Esc`** | Exit any mode and return to **Normal Mode** |
| **Saving & Exiting** | **`:w`** | Save (write) changes |
|  | **`:wq`** | Save changes and quit Vim |
|  | **`:q!`** | Quit immediately **without saving** (force quit) |


```bash
-5dd = Delete 5 lines.
-3w = Move forward 3 words.
-10j = Move down 10 lines.
```

### vim written commands

```vim
:%y+ to coppy an entire file
:pwd to get the current director in oil

:vsplit for a vertical split
:split for a horizontal split

:terminal for terminal
    ctrl \ ctrl n   together to exit out of terminal


:InspectTree    to use inspectree
:inspect

To turn render on and off
:RenderMarkdown Toggle

#Yanking from Vim
"+yy — Yanks the entire current line to your system clipboard
"+y — Yanks the current visual selection to your system clipboard 
      "(press v or V first to highlight text, then type "+y).
"+p — Pastes text from your system clipboard into Vim.
gg%+yG          - gg takes you to the top, % all in the range, + add to (clipboard), y yank, G range to the end of the file 
:let @+ = @" "- To move text you have already yanked inside Vim into your system clipboard

set ft? or set filetype?    to check filetype
set ft=python               to set the file to python


#Vim Macros
Press q                       to record macro
Choose a register to store the macro eg "h"
execute your macro your inputs and regex will be saved
Use vim motions to execute your macro e.g:
    Quote a line " word " then hit esc enter:
    q h ciw " esc p " esc enter go down one line then q 
    again to exit recording
q to end recording
type @h to quote the next line (normal mode, no colon :)
5@h to quote the next 5 lines.

:reg to see your recorded in register h or q
put q   to see edit your macros saving in q
qyy     to save your edited macro in regx form and save it to q again.
:reg    should be visiable under the q  register.
:put q  to type out the macro you recorded and random it in text.
"qyy    to yank that edited macro into q register
        @q in normal mode will run your edited macro
        :put q to see if the changes carried over. :


```
### NVIM refactoring

```vim
:vimgrep /oldname/  'find . -type f'             Uses grep to filter for the word "oldname" and find those that are "types"
                                                 this is establishes a "quick fix list"

:copen                                           access every instance of the target word is a quick fix list you can cycle through

:cdo %s/oldname/newname/gc                       cdo allows access to the quick fix list
                                                 % means all in regex
                                                 s for "sed command"
                                                 g for "global"
                                                 c for "confirmation" require confirmation for each possible change "y/n"

```
### Multi line editing

```vim

    regex: substitute pattern
Highlight with v and then click : that will start typing the substitution pattern:'<,'> 

:'<,'>s/oldname/newname

" s for substittute    end with /g for global  
"use \ for special characters  oldname = \,  if you want to edit comma
"Note: When in VISUAL MODE and click : it automatically types '<,'>s
"'<,'>  represents in regex the visual selection range

Refactoring in ED Stem
[user@sahara ~ 1$ ed stock.cpp
700
1,46s/bestP/bestProfit/g
725

The pattern
[start_linel, lend_line]s/[old_name]/[new_namel/g
    - S for substitute
    - g for global,     as in don't stop at one, do all in the range 


if your variable is single letter like g this might be better
1,46s/\<g\>/newVariable/g

        "Add <b> </b> betweens lins of text"
ctrl v              much like visual mode highlight but lets you do so in a square uniform shape
                    ideal for macros
i                   for insert mde
type <b>            
esc                 esc will apply the macro

for the other side
gv                  restores the previous highglight <REMEMBER>
$                   to takes the highlight to the other side
                    note you can also use w, e, b
type </b>
esc



```
### VIM Visual Multi

```bash
Pugin:VIM Visual Multi

Its Ctrl-n mapping is active.

Quick use:
1. Place the cursor on a word.
2. Press Ctrl-n repeatedly to select additional occurrences.
3. Press i, a, c, or another editing command.
    - i to append the start
    - a to append the end of the line
    - c to delete and replace
4. Type once to edit every selected occurrence.
5. Press Escape to exit Visual Multi.

Other useful controls:
- n / N — next/previous occurrence
- q — skip the current occurrence
- Q — remove the current selection
- Ctrl-Down / Ctrl-Up — add cursors vertically
- Tab — switch between cursor and selection modes

For unrelated lines or positions:
Remapped to shift ctrl down/up due to macos conflicts
- Use Ctrl-Down or Ctrl-Up to add cursors vertically.
- Or move to a position and press \ followed by \ to add a cursor there (\\).
- Make a Visual selection and press \c to create a column of cursors.


    \\\—three backslashes—is the manual toggle cursor at this exact position command.

It is useful when the desired cursor positions cannot be generated by:
- Control-n because the words differ.
- Control-Shift-Up/Down because the positions are not vertically aligned.
- \\c because they do not form a clean column.

Pressing \\\ where there is no cursor adds one; pressing it where a cursor already exists removes it.

For your bold example, you don’t need it. Your vertical-cursor method is simpler:
1. Add cursors with Control-Shift-Down.
2. Press i, type **, then Escape.
3. Move all cursors with l or a suitable motion.
4. Press i or a, then type the closing **.
Think of the commands this way:
- Control-n → cursors on matching words.
- Control-Shift-Up/Down → cursors in a straight vertical line.
- \\c → convert a Visual block into a cursor column.
- \\\ → manually toggle one cursor at an exact position.

Use:
- Control-n for identical words.
- Control-v for rectangular columns.
- Control-Shift-Up/Down for multiple independent cursors on adjacent lines.



https://github.com/mg979/vim-visual-multi/wiki/Mappings



```

###  NVIM Session manangement / Tmux

```vim
Some multiplexing is possible locally within NVIM and most modern terminals.

NVIM multiplexing is saved in a small savefile. 

Tmux multiplexing can wasteful on resources when not use remotely, 
Tmux main value is meant to be from from remote server access

from a work computer (SSH). It's optimal to use these alternative multiplexing options. 

Ghosty, Kitty, WezTerm, warp some form of way to say layouts and sessions and split screen
```

```vim
mksession  savefile1.nvim

loadsession  savefile1.nvim

nvim -S [path/to/file.vim].         looad instantly

            SessionManager Plugin
    SessionManager load_session

    SessionManager save_current_session

    SessionManager delete_session 

    SessionManager load_last_session

    load_current_dir_session

mks session.vim         mks = make

so session.vim          so = source

:mksession! | qa        forces a session save over an existing file and closes all windows.

:Se + Tab → :SessionManager

 Run nvim -S            #saved layout

    Same command again for off
:MarkdownPDF
Close current tab:tabclose or :tabe

tabnext or tqbn         gt

tabprevious or tabp      gT


:tabnext 2        2gt goes to tab 2

:tabclose (or :tabc)        ctrl w c (when there are no panes/windows)

:tabonly or tabo            Close all tabs but one

Ctrl + w then T      Move current window to new tab


```



### NVIM Custom Commands


```vim
Space f d   Teslecope lists all the flagged code (great for coding/debugging)
Space f f    Telescope: find files
Space f g    Telescope: live grep
Space f b    Telescope: buffers
Space f h    Telescope: help

Space e      Oil file explorer | A fast nvim file explorer, you can use 
             VIM insert mode to make and delete files (:q to save) 
Space n      NeoTree | NeoTree like the side bar of file in VsCode
Space a      Aerial | Areial is like NeoTree but shows Chapter Contents, Functions
             
             To jump between markdown headings or functiions
             [[ 
             ]]
             [h
             ]h

    TYPST
Space t p       to render and preview in browser
Space t r       to reset


    Plugin:MarkdownRender Commands
:RenderMarkdown preview
:RenderMarkdown enable
:RenderMarkdown disable
:RenderMarkdown toggle
    type again to turn off
:RenderMarkdown preview       
:MarkdownPDF
    Custom commands: Markdown
MarkdownLock
    space m l 


K            LSP hover
gd           go to definition
grr          references
Ctrl-o       jump back
`            Sets Oil's directory to the actual terminal directory
             prompted AI to detect when I backtick(`) into a new directory on oil
             upon closing (q)
             "y/n" it asks me to cd into the new directory

:term        nvim terminal
shift esc    custom escape out of nvim terminal (must be in insert mode)

:lua Snacks.image.buf.attach()                  Deteaches the images being displayed or ghosted/stuck
:lua Snacks.image.buf.attach(0)                 This restablishes the connection to the image in the file.
                                                Must be used in the page of the missing image.
space c esc                                     Macro clears frozen images in nvim buffer and then resets it.
                                                Then it places the image reset command in the clipboard.
                                                ':lua Snacks.image.buf.attach(0)'



Custom Copyrigt Image Kill Switch
Run once in terminal to load it
source ~/.zshrc

turn on
terminal-visuals safe

turn off
terminal-visuals personal

ls
terminal-visuals status


```
 

### NVIM  Favorites Dashboard (custom)

```text
I have  custom/local NVIM plugin that sets favorite files or folders
and sets them in the nvim snacks dashboard. The files or folders are acessible with:
                    
                        option + 1...9

        or you can 'enter' in to them from the dash board

NVIM much better with favorites/bookmarks there are folders i keep going to and Mac aliases
strictly don't work on terminals. Originally i had a .md in my user folder (~) that
I copy pasted cd directories onto.

*NVIM Snacks* is a popular repo that brings a lot of QOL update to the standard NVIM like
an ineractive Home menu/Dashboard that can display recent files/projects/git requests. 
This just adds to that.
```
| Command | Effect |
|---|---|
| `:Fav` | Pin the current file into the lowest free slot |
| `:Fav 3` | Pin into slot 3, overwriting whatever is there |
| `:Fav!` | Pin the **cwd** even when a file is open |
| `:FavDel 3` | Clear slot 3 |
| `:FavList` | Show all nine slots, empty ones as `—` |




### Panes

```Bash
split or sp or ctrl w s          horizon stplit
vsplit or vp or ctrl w v         vertical split
ctrl w w                         cycle between pains cycle baclwards "Ctrl p" to cycle return
ctrl ijkl                        moved around panes
ctrl + - < >                     to increase pane size, decrease, width
ctrl _ or ctrl |                 for max width
ctrl w c or :close               close a pane
ctrl w ijkl                      move pane 
ctrl w x                         exchange with next pane
ctrl w r                         rotate
ctrl w T                         take pane to a new tab

Lock panes
:setlocal winfixheight                  /lock
:setlocal winfixwidth
:setlocal winfixheight winfixwidth
:setlocal winfixheight winfixwidth      unlock
```

## tmux Controls

```vim
ctrl b + "     "make a horizontal pane
ctrl b + %     make a verticle pane
ctrl b+o       to switch between panes
ctrl b + w     SESSIONG MANAGER to look at all your windows within the session (confused me)
    t          to select a window
    T          to unselect
    x          to close selected windows
    v          to toggle
ctrl b + c     New Window/Tab
ctrl b + d     to close a window
ctrl b + n     to swap to the next window ctrl b p for previous
ctrl b + x     to close a pane
ctrl d         to close a WINDOW you are inside off
ctrl b + : "kill-pane" -t 0    to close a specific pane
ctrl b + c                  new window
ctrl b { or }               to swap window panes between each other


tmux ls        to see all the open session
tmux           to make a new session
tmux new -s session_name to         to make a new session name
tmux attach -t session_name         to attach to a specific session
tmux attach -t 0                    or another number to open an unnammed session
tmux kill-window -t
tmux kill-session 
tmux kill-server
ctrl b ,                            to rename the window/tab
ctrl b $                            to rename the current session

 /Resizing windows 5 to 3 units up)/
ctrl b:     #then
    resize-pane -L 5
    resize-pane -R 5
    resize-pane -U 3
    resize-pane -D 3
    swap-pane   ctrl M then ctrl o target a pane to swaop pane input this
    select-pane -d (for "disable") pane from moving
    select-pane -e (for "enable") 
ctrl [      then arrow up key to scrll up 
            /ctrl c/ to escape you can get stuck
            may need "set -g mouse off"

## doesn't reall work...
Ctrl-b Al
t-Left
Ctrl-b Alt-Right
Ctrl-b Alt-Up
Ctrl-b Alt-Down

ctrl ,      #to rename a window
tmux rename-window <new-name>       #written command to rename a window
set-option -g automatic-rename off      #block automative renaming

Renaming Session
ctrl b or w         To View Tmux Session List
shift E             To rename
Enter
tmux rename-session <new-name>      written command to rename current session
tmux rename-session -t <old-name> <new-name>    written command to rename an external session

```

| To close a... | Shortcut | Command prompt (`Ctrl + b` then `:`) | Terminal command |
| :--- | :--- | :--- | :--- |
| **Pane** | `Ctrl + b` then `x` | `kill-pane` | `tmux kill-pane -t <id>` |
| **Window** | `Ctrl + b` then `&` | `kill-window` | `tmux kill-window -t <id>` |
| **Session** | N/A (or detach with `d`) | `kill-session` | `tmux kill-session -t <name>` |


### TMUX Config and Other Locations
```text
Working with tmux configurations and other plugins
```

```Bash
#Nvim config FIle
nvim ~/.config/nvim/init.lua
:reset #to reload

#To open the Tmux Confuguration
nvim ~/.tmux.conf

#to reload
tmux source-file ~/.tmux.conf

#other locations

#Zshell
nvim ~/.zshrc

#fast fetch
nvim ~/.config/fastfetch/config.jsonc

#WezTerm
nvim ~/.config/wezterm/wezterm.lua 


```

```bash
#To open the file for confuguration
nvim ~/.tmux.conf

#to reload
tmux source-file ~/.tmux.conf
```


## Zelli
```text
Zellij is a modern alternative to tmux with loads of QOL updates
```


### Zellij Controls

```vim
ctrl p          pane mode

    n           new pane

    x           close pane

    p           switch between panes

    h / j / k / l
                move between panes

    arrow keys  move between panes


ctrl t          tab mode

    n           new tab

    x           close tab

    left/right  move between tabs


ctrl n          resize mode

    left        resize left

    right       resize right

    up          resize up

    down        resize down


ctrl s          scroll mode

    up/down     scroll

    page up     page up

    page down   page down


ctrl d          close shell / pane you are inside


zellij list-sessions
zllij ls
                see open sessions

zellij --session session_name
zellij -s 
                make/open named session

zellij attach session_name
zellij -a
                attach to session

zellij action rename-session new_name
zellij ac rename-session
                rename current session

zellij action rename-tab new_name
zellij ac rename-tab
                rename current tab



Closing Sessions
Ctrl Q  quit
Ctrl 0  detach
zellij kill-session <session-name>  Kill a specific session
zellij k <target-session>).
zellij kill-all-sessions        Kill all sessions ending all processes but maintain data to revive a session
zellij ka
zellij dele-all-sessions        deletes all sessions(tmux kill just kills processes and deletes) 
zellij da                       delete is closer to tmux kill session which deletes all data


```


## Git

```vim
Git adds a hidden file on your project/folder, this tracks changes necessary allowing for "version control"

My manual way of version control, I simply copy paste the whole folder into a new folder when i want to

to a new direction, hit a check point or trying out random ideas.i

Git is a more organise way of what I would do locally.

Commands you would use a lot

Git Status 
Imagine living your life with your eyes closed. Commands like Git status and "ls" in bash let's you be more aware.

Git add .
Imagine loading a gun. The " fullstop '.' "  means "all" while Git add loads your changes read to be sent to the
"repo" the main folder you're trying update. 

```

### Git in General

```vim

git init            this begins git's tracking of your files helping compare diferences between the main
                    database and your potential changes. The main point is version control. This ability 
                    track changes and potentially rewind time as well review changes before they go live
                    and cause trouble.

                    Note this is the first thing you do with a new project as far as your local code base
                    goes.

git add .           Imagine "loading a gun" git add loads you current changes and starts the process of querying 
                    and asking to make your current changes with the goal of changing the live code base. The full stop 
                    means "all" but you target changes only in specific files.


git commit -m "your message"                        So you've written your message and you locked it in your envolop. Git commit is like 
                                                    sending it off to the post office. -m is for message. You ust have a message it is
                                                    a non negotiable. The -m flag is byproduct of the architecture it's convenient. 

git remote add origin https://github.com            This links your your github repo or any github to to your own personal 
                                                    copy. Unlick the previous two you likely only need to do it once. You 
                                                    can actually skip this and keep your version control local from what I
                                                    gather.

git branch -M main                                  Names your branch of the code (your local setup). It doesn't have to be "main"
git branch -M name newname                          but it's a common convention. When you name your branch it is unique and you can't
                                                    have idential names. -M forces a move or rename. -m is possible but it will be less
                                                    authoritative on a conflict and be immediately locked out. Where -M can attempt to 
                                                    query even if it is not going to be manually approved.


git remote -v                                       Shows the github link(or other) linked to it if there is one.                                

.gitignore                                          Let's you exclude files and folders from your commits and push. Some files and folders
                                                    are not necessary or even determental to the full build. 

touch .gitignore                                    To create .gitignore



ls a 

git clone <YOUR_REMOTE_REPOSITORY_URL>              Clone  a repo.

Make a repo from your terminal
gh auth login                                                       login to github  ("brew install gh" if not instally)


gh repo create <YOUR_REPO_NAME> --public --source=. --remote=origin --push          # Create a remote repo and push your local files automatically


What if there is already files in your repo and you code base don't match
git remote add origin <PASTE_YOUR_REPO_LINK_HERE>
git pull origin main --allow-unrelated-histories
git add .
git commit -m "Fix merge conflict"
git push -u origin main



```

```vim

git push -u origin <new-branch-name>                Push the new branch and request it to be merged to the main relase. Git push only adter.

git push origin --delete <old-branch-name>          Delete the old branch from the remote server 

echo "fileOrfolder/" > .gitignore                   Adds file/folder to .gitignore, it is appended to the end of the list.
                                                    This command may also overwrite existing .gitignore so be careful.

ls -a                                               To check for existing .gitignore. 
cat .gitignore

git rm --cached filename                            To remove tracking if you already uploaded a file that was not meant to be tracked or in the release.  

ls -la                                              Shows .git and .gitignore files. With '-l' it shows the files with info about permissions, size, owners
                                                    date and times.
                                                    

rm -rf .git                                         Deletes .git disconnected the folder from the repo and frees it up for different repo. rm fo remove -r
                                                    delete evertyhing inside -f forces deletion even for protected files.

git remote set-url origin <URL>                     To change github repo after origin has already been set. THe behavior is diffent after original links.

git diff --cached                                   Shows the code that is about to be changes by the proposed commit.

git log --oneline                                   Shows a history of your commits. --oneline shorterns the output making it more reasable.



#unlinking a cloned repo
git remote remove origin                            Unlinks the cloene repo from the original repo.
git remote add origin https://github.com   
git remote add origin <YOUR_NEW_REPO_URL>

#other way
rm -rf .git
rmdir /s /q .git                                   Removes .git /s remove the directrory quickl /q quiet mode does not ask permission. rmdir is removew directory.

git init -b main                                   Intiative .gitinit and sets the branch name to main.

```

### ISSUE: fresh repo has a file already

```vim
#as usual
git init
git add .
git commit -m "Initial commit"
git remote add origin <YOUR_REMOTE_REPOSITORY_URL>

#Pull/Download the remote README and force merge the unrelated histories
git pull origin main --allow-unrelated-histories

#Fix any conflicts if they arise, then push. 
You can change main origin main to anything.
git push -u origin main


```

### ISSUE: You want to keep a live repo just incase but you also have a completely different build you want to push

```text
You noticed your repo is suddenly very different, there are now new files and some of the system has been changed. 

You're worried that they might be important but you also need to get this new and  completely different version live.

How can you save the current repo?
```   


```vim
One way...

You can make a new branch from your side. Who ever is the admin still has to approve it. 

You must access this live repo in your terminal.

Go to your local set up and use the terminal.




Acess the latest changes from your remote directory
git fetch origin


Create a new backup branch to keep the strange files safe
-b for branch setups the repo for a branch
git checkout -b backup-old-files


Push this current version of the repo into the back up branch you just made
-u for upstram sets set up a link between the live repo and the new branch
A tracker is set that will allow you to recreate this version if needed
git push -u origin back-up-message


Switch to your local version
git checkout main

Add and load up your new version
git add .


Commit your changes
git commit -m "mesage"

Push and make it live
git push origin main


git push                might sitll work instead







```
