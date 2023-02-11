# My config with LSP ### (based on thePrimagean config as a starting point, but
with my additions)

# Step 1: Installation

* Install neovim (ubuntu)

`` curl -LO
https://github.com/neovim/neovim/releases/latest/download/nvim.appimage chmod
u+x nvim.appimage ./nvim.appimage``

then

``./nvim.appimage --appimage-extract ./squashfs-root/AppRun --version

# Optional: exposing nvim globally. sudo mv squashfs-root / sudo ln -s
/squashfs-root/AppRun /usr/bin/nvim nvim```

* Make sure you have gcc installed:

`` sudo apt update``

and then 

`` sudo apt install build-essential ``

 * install fzf
 
 `` git clone --depth 1 https://github.com/junegunn/fzf.git ~/.fzf
 ~/.fzf/install``

* install packer 

`` git clone --depth 1 https://github.com/wbthomason/packer.nvim\
~/.local/share/nvim/site/pack/packer/start/packer.nvim ``

 Source the packer.lua file from lua/chip/packer.lua write ``:PackerSync``
 right after to install everything ### Mappings:

* Ctrl + p - Git file search (if you have git initialized, ignores whatever git
  is supposed to ignore)
* _pf - full file search in the root where nvim was initialised
* _pv - enteres explore mode
* _a - Harpoon - add current file to harpoon
* _u - UndoTree - a history side view of the file
* Ctrl + e - Harpoon - toggle quick menu
* Ctrl + t - Harpoon - switch to file 1
* Ctrl + h - Harpoon - switch to file 2
* Ctrl + n - Harpoon - switch to file 3
* Ctrl + s - Harpoon - switch to file 4
* 10GV12G - select from line 10 to line 12
* gwip - reflow paragraph
* } - jump to next paragraph (or function/block, when editing code)
* { - jump to previous paragraph (or function/block, when editing code)


### Core vim movement keys
* h - go left 1 character
* j - go down 1 character
* k - go up one character
* /abc - find inside current file the characters abc
* n - next occurance of the previously searched word
* N - previous occurance of the previously searched word
* e - jump to last character in word
* w - jump to first character in word
* b - jump to first character in word
* c - change word (ex cw - will remove the text until the first character in the word

* ciw'Ctrl+r"' - wrap a word in single quotes
* <selection>c""(Esc)P - wraps the whole selection in " "

 * vi{ - select everything between {} that I am in or on now

### Git conflict solve approach

- When you pull you sometimes get conflicts to love them: 
1. do a _gs (space then g then s, to enter a new split window with git status)A
2. the conflicted files will appear in merged with a U on their left. go to the conflicted file 1 (choose any conflicted file) and press "o" on it
3. write :Gdiffsplit! on the new file that opens
4. with CTRL+ h for left and CTRL+L for right go to the version you want to accept and press "dp" on the modification from the left or right panel in the command, that will put the selected version in the middle
5. in the middle write :w to save and :Gwrite to stage the resolved conflict in git
6. then you can go back to the presumably already opened _gs window and write cc to commit. The commit message is already in there, you can save (:w) and exit
7. Lastly, you ":Git push" to push the commands to the repoB

## Comands:

* :lua ColorMyPencils() - sets the color theme and transparent background
* :TSPlaygroundToggle - Treesitter insights for plugins
* :%s/searchedText/replaceWithText - search and replace in current file in vim

## Notes

*!!!!!!!!! IMPORTANT !!!!!!!!!  You Require rimgrep installed to have grep fuzzy finder active
* (to be able to search for text within the files of your project)
