# Filemanager Plugin **improved**

A simple plugin that allows for easy navigation of a file tree.

<img src="https://github.com/user-attachments/assets/33bea6eb-7cba-4632-8bd9-138713bd0b0a" />

### Installation:
```shell
cd ~/.config/micro/plug/
git clone https://github.com/smir-ant/filemanager-plugin.git filemanager
```

### Run

`ctrl+e` in micro > tree to activate, and again to deactivate

Want hotkey for this? Add `"Ctrl-j": "command:tree"` in bindings.json for ctrl+j


### What and why

The original repository received its last commit about 6 years ago. And this is not a problem in itself. The problem is that there are big problems and difficulties in using.

Improvements:
+ MOUSE! now u can click on files or folders to collapse/expand (move to folder is click+tab)
+ Opens the directory of the open file, not from the binary
+ The standard width is set via `"filemanager.width": 20` in the settings json file
+ Relative path, not absolute <sub>(u can move above by select .. and tab, then ./ path will change on ../, again? ../.. - like relative path)</sub>. p.s. reset by reactivate `ctrl+e` > tree

Bonus:
+ U can safely click at the bottom, in an empty space (hello https://github.com/buxxket/filemanager-plugin )


### Options

| Option                       | Purpose                                                      | Default |
| :--------------------------- | :----------------------------------------------------------- | :------ |
| `filemanager.width`          | Width(symbols) of the filemanager panel                      | `30`    |
| `filemanager.showdotfiles`   | Show dotfiles (hidden if false)                              | `true`  |
| `filemanager.showignored`    | Show gitignore'd files (hidden if false)                     | `true`  |
| `filemanager.compressparent` | Collapse the parent dir when left is pressed on a child file | `true`  |
| `filemanager.foldersfirst`   | Sorts folders above any files                                | `true`  |
| `filemanager.openonstart`    | Automatically open the file tree when starting Micro         | `false` |


### Commands and Keybindings

The keybindings below are the equivalent to Micro's defaults, and not actually set by the plugin. If you've changed any of those keybindings, then that key is used instead.

If you want to [keybind](https://github.com/zyedidia/micro/blob/master/runtime/help/keybindings.md#rebinding-keys) any of the operations/commands, bind to the labeled API in the table below.

| Command  | Keybinding(s)              | What it does                                                                                | API for `bindings.json`               |
| :------- | :------------------------- | :------------------------------------------------------------------------------------------ | :------------------------------------ |
| `tree`   | -                          | Open/close the tree                                                                         | `filemanager.toggle_tree`             |
| -        | <kbd>Tab</kbd> & MouseLeft | Open a file, or go into the directory. Goes back a dir if on `..`                           | `filemanager.try_open_at_cursor`      |
| -        | <kbd>→</kbd>               | Expand directory in tree listing                                                            | `filemanager.uncompress_at_cursor`    |
| -        | <kbd>←</kbd>               | Collapse directory listing                                                                  | `filemanager.compress_at_cursor`      |
| -        | <kbd>Shift ⬆</kbd>         | Go to the target's parent directory                                                         | `filemanager.goto_parent_dir`         |
| -        | <kbd>Alt Shift {</kbd>     | Jump to the previous directory in the view                                                  | `filemanager.goto_next_dir`           |
| -        | <kbd>Alt Shift }</kbd>     | Jump to the next directory in the view                                                      | `filemanager.goto_prev_dir`           |
| `rm`     | -                          | Prompt to delete the target file/directory your cursor is on                                | `filemanager.prompt_delete_at_cursor` |
| `rename` | -                          | Rename the file/directory your cursor is on, using the passed name                          | `filemanager.rename_at_cursor`        |
| `touch`  | -                          | Make a new file under/into the file/directory your cursor is on, using the passed name      | `filemanager.new_file`                |
| `mkdir`  | -                          | Make a new directory under/into the file/directory your cursor is on, using the passed name | `filemanager.new_dir`                 |

#### Notes

- `rename`, `touch`, and `mkdir` require a name to be passed when calling.\
  Example: `rename newnamehere`, `touch filenamehere`, `mkdir dirnamehere`.\
  If the passed name already exists in the current dir, it will cancel instead of overwriting (for safety).

- The <kbd>Ctrl w</kbd> keybinding is to switch which buffer your cursor is on.\
  This isn't specific to the plugin, it's just part of Micro, but many people seem to not know this.
