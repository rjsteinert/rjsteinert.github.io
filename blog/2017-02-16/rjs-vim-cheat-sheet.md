# R.J.'s Vim Cheat Sheet
This is a WIP document of the tricks I use in Vim the most.

## Opening files in Vim
- `vim .`: Open current directory in a file tree explorer.
  - `Enter`: To open a folder or file, navigate to it and press `Enter`.
  - `t`: Open a file in a new tab.
  - `p`: Preview a file in a vertical window.
  - `R`: Rename file/directory.
  - `:b#`: Command to go back to tree.
- `vim <file>`: Open a single file.
- `vim -O <file> <file...>`: Open files in vertical windows.
- `vim -o <file> <file...>`: Open files in horizontal windows.
- `:tabedit <file>`: Open a file in a new tab.
- `:split <filename>`, `:vsplit <filename>`: Open a file in a horizontal or vertically split window.


## Tabs
- `gt`, `gT`, `<tab numbe>gt`: Next tab, previous tab, go to tab number.
- If you have `set mouse=a` in your `~/.vimrc` file, you can select a tab by clicking on it.


## Windows
- `ctrl+w` and then arrow direction of window to switch to.
- `resize <number of lines>`: Resize window to number of lines.
- `vertical resize <number of columns`: Resize window to number of columns.
- If you have `set mouse=a` in your `~/.vimrc` file, you can select a window by clicking on it.


## Vim modes
- `Esc`: Standard mode.
  - `$`, `0`: Go to beginning of line, end of line.
  - `ctrl+f`, `ctrl+b`: Forward and back pages.
  - `e`, `b`: next word and back word.
  - `dd`: Cut line.
  - `yy`: Copy line, AKA yank line.
  - `p`: Paste.
  - `h`, `j`, `k`, `l`: Left, Up, Down, Right. Great for keeping your hands on the home row. Also can be used when changing windows, and navigating file tree.
  - `<<`, `>>`: Indent.
  - `.`: Do that operation again. Useful for repeating indents.
  - `r<key>`: Replace character under cursor with <key>.
  - `o`: Create new line below cursor and start Insert mode.
  - `A`: Go to end of line cursor is on and start Insert mode.
- `v`: Visual mode, AKA select mode.
  - Use navigation keys on home row, word skips, arrow keys, etc. to expand selection. If you have `set mouse=a` in your `~/.vimrc` file, you can select text by click and dragging.

  - `y`: Copy.
  - `d`: Delete.
- `/` Search mode.
  - `/foo` + `Enter`: Search mode for `foo`
  - `n`: Next occurrence of `foo`.
  - `b`: Previous occurrence of `foo`.
- `:`: Command mode.
  - `w`: Write changes to disk.
  - `q`: Quit vim.
  - `wq`: Write and quit.
  - `33`: Go to line number 33.
  - `98765`: Go to end.
  - `!`: See the command line.
    - `!sudo make-me-a-sandwich`: Run `sudo make-me-a-sandwich` on the command line. This is not really a command. I'm just pointing out that you can run any command on the command line from vim. Handy for when you need to do something like compile or restart a service after you make a change.
  - `%s/<find this>/<replace with this>/g`: Find and replace. Make sure to escape forward slashes if your strings have them. Don't forget the `g` on the end or it will only replace one occurrences of that thing on every line as opposed to all occurences on all lines.


## Vim settings in `~/.vimrc`
Your `~/.vimrc` file is a set of commands to run every time Vim opens. Mine enables better handling of indentation when pasting from your system's clipboard, support for using a mouse, better indentation formatting, showing line numbers, and enabling formatting of text. See it [here](https://gist.github.com/rjsteinert/87c3dfdd96692d97ea3a88fd3f1bc867). Make it your own by running `curl https://gist.githubusercontent.com/rjsteinert/87c3dfdd96692d97ea3a88fd3f1bc867/raw/.vimrc > ~/.vimrc`.

[gimmick:gist](87c3dfdd96692d97ea3a88fd3f1bc867)

<script src="https://gist.github.com/rjsteinert/87c3dfdd96692d97ea3a88fd3f1bc867.js"></script>

## Tips
- Map `caps lock` to `Esc` to keep your fingers on the home row. https://pqrs.org/osx/karabiner/seil.html.en
- Install `nerdtree` to make the file explorer formatted as an expandable tree. https://github.com/scrooloose/nerdtree
- Interactive Vim training is worth the time. http://www.openvim.com/
- Remember, if there is anything you are doing that feels awkward there is a vim command to solve that problem. For example, going to the end of a line and starting insert mode is awkward without `A`.
- [Another good vim cheatsheet](http://www.worldtimzone.com/res/vi.html)
