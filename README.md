# Even better explorer for micro

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
+ LClick for open file instead of previous (not split tab), select+tab for split
+ Opens the filemanager tree from opened file, not from the binary
+ The standard width is set via `"filemanager.width": 20` in the settings json file
+ Relative path, not absolute <sub>(u can move above by select .. and tab, then ./ path will change on ../, again? ../.. - like relative path)</sub>. p.s. reset by reactivate `ctrl+e` > tree

Bonus:

+ U can safely click at the bottom, in an empty space (hello https://github.com/buxxket/filemanager-plugin )

### settings.json config

| Option                         | Purpose                                                      | Default  |
| :----------------------------- | :----------------------------------------------------------- | :------- |
| `filemanager.width`            | Width(symbols) of the filemanager panel                      | `30`     |
| `filemanager.showdotfiles`     | Show dotfiles (hidden if false)                              | `true`   |
| `filemanager.showignored`      | Show gitignore'd files (hidden if false)                     | `true`   |
| `filemanager.compressparent`   | Collapse the parent dir when left is pressed on a child file | `true`   |
| `filemanager.foldersfirst`     | Sorts folders above any files                                | `true`   |
| `filemanager.openonstart`      | Automatically open the file tree when starting Micro         | `false`  |