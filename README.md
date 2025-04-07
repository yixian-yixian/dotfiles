# dotfiles
Useful commands collected from all over the world thanks to [dwmkerr](https://github.com/dwmkerr/dotfiles/blob/main/README.md?plain=1), [gpakosz](https://github.com/gpakosz/.tmux)
### Shell Commands

The following shell commands are setup:

| Command                                   | Usage                                                               |
|-------------------------------------------|---------------------------------------------------------------------|
| **Quick Aliases**                         | [`shell.d/aliases.sh`](./shell.d/aliases.sh)                        |
| [`serve`](./shell.d/aliases.sh)           | Serve the current folder over HTTP on port 3000.                    |
| [`vinilla`](./shell.d/aliases.sh)         | Open `vi` without loading the `vimrc` (i.e. vanilla configuration). |
| **Basic Functions**                       |                                                                     |
| [`eachdir`](./shell.d/functions.sh)       | Run a command in each child directory.                              |
| [`D`](./shell.d/functions.sh)             | Get the date in ISO86091 format (e.g. `2021-04-24`).                |
| [`mkd`](./shell.d/functions.sh)           | Make a directory, using `-p` and `cd` into it.                      |
| [`restart_shell`](./shell.d/functions.sh) | Restart the current shell process, useful when profile changes.     |
| [`revcut`](./shell.d/functions.sh)        | Cut, but in reverse (i.e. from the last to the first delimiter).    |
| [`toggle_bak`](./shell.d/functions.sh)    | Toggle *.bak off or on a file (useful to disable config etc).    |
| **Git Functions**                         |                                                                     |
| [`ghclone`](./shell.d/git.sh)             | Clone from GitHub, e.g: `ghclone dwmkerr/effective-shell`.          |

### Shell Scripts

| Script                      | Usage                                                                            |
|-----------------------------|----------------------------------------------------------------------------------|
| `./scripts/test-shell.d.sh` | Source each `./shell.d` file in turn, time result. Good for checking for errors. |

## Cheat Sheet - TMux

| Command                                   | Usage                                                            |
|-------------------------------------------|------------------------------------------------------------------|
| **Sessions**                              |                                                                  |
| `tmux detach -E 'bash --noprofile --norc` | Detach the current session and open a vanilla shell.             |
|-------------------------------------------|------------------------------------------------------------------|
| `<leader> R`                              | Reload Tmux configuration (i.e. source the `~/.tmux.conf` file). |
| `man tmux`                                | Get help on commands.                                            |
| `<leader> ?`                              | Get help on commands.                                            |
| `Ctrl + h/j/k/l`                          | Navigate splits (vim aware)                                      |
| `Meta + h/l`                              | Move through tabs.                                               |
| `Ctrl + Meta + h/j/k/l`                   | Move through tabs.                                               |
| `move-window -r`                          | Re-order the tab numbers (useful if there are gaps).             |
| `<leader> / S`                            | Show Sessions with window preview, hit `x` to delete.            |
| `<leader> / $`                            | Rename session.                                                  |
| `new -s <name>`                           | New session with name.                                           |
| `<leader> / Ctrl+S`                       | Save Tmux Session                                                |
| `<leader> / Ctrl+R`                       | Restore Tmux Session                                             |
| `<leader> /`                              | Last split                                                       |
| `<leader> {`                              | Swap pane left                                                   |
| `<leader> }`                              | Swap pane right                                                  |
| `<leader>. <session-name>:<pane number>`  | Move a pane to a session.                                        |


## Cheat Sheet - Vim

Here's a quick reference. My `<Leader>` is `\`, so I've written shortcuts as `\x` rather than `<Leader>x` for brevity. I still need to port the above to the structure below.

| Command                              | Usage                                                                                                                             |
|--------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------|
| **Custom Commands**                  |                                                                                                                                   |
| `<leader>t`                          | Open current file in NERDTree.                                                                                                    |
| `<leader>w`                          | Write buffer.                                                                                                                     |
| `<leader>\\`                         | Open buffer in new tab.                                                                                                           |
| `<leader>d`                          | Open word under cursor in Dash.                                                                                                   |
| `<leader>t`                          | Show current buffer in NERDTree.                                                                                                  |
| `<leader>F`                          | Toggle focus mode.                                                                                                                |
| **Other Commands**                   |                                                                                                                                   |
| `\[<Space>`                          | blank line above                                                                                                                  |
| `]<Space>`                           | blank line below                                                                                                                  |
| `sj`                                 | Splitjoin down (i.e. split a line downwards).                                                                                     |
| `sk`                                 | Splitjoin up (i.e. join a line upwards).                                                                                          |
| `:Tabularize /=`                     | Line up selection, using '='                                                                                                      |
| **Navigation**                       |                                                                                                                                   |
| `gd`                                 | Where possible, will go to a local definition. Supercharged by vim-coc.                                                           |
| `gd`                                 | https://vi.stackexchange.com/questions/42414/for-vim-and-specifically-coc-vim-is-it-idomatic-to-use-gd-to-open-a-link/42415#42415 |
| `gf`                                 | Open file under cursor.                                                                                                           |
| `gx`                                 | Open link or address under cursor.                                                                                                |
| **Spelling**                         |                                                                                                                                   |
| `]s` and `[s`                        | Next/Previous spelling error.                                                                                                     |
| `z=` and `zg`                        | Check dictionary / add to dictionary.                                                                                             |
| **Markdown**                         | Provided by `vim-markdown`                                                                                                        |
| `]]` and `[[`                        | Next and previous headers.                                                                                                        |
| `gx`                                 | Open link in standard editor.                                                                                                     |
| **Focus**                            | From `vim-goyo` and `vim-limelight`                                                                                               |
| `:Goyo`                              | Enter focus mode.                                                                                                                 |
| `:Limelight 0.8` and `:Limelight!`   | Go into limelight, 80% ultra focus, and toggle limelight.                                                                         |
| `let g:limelight_paragraph_span = 1` | Span more paragraphs in limelight.                                                                                                |
| **Markdown Tables**                  |                                                                                                                                   |
| `\tm`                                | Enter/Exit 'table mode', which will dynamically format markdown tables.                                                           |
| `ci｜`                               | Example of the `｜` motion for cells - i.e. 'change-in-cell'.                                                                     |

Note: including the vertical pipe `|` in the table above would cause rendering issues. So instead, the unicode character `｜` is used to illustrate the commands. Do not use the unicode character, use the normal ASCII 0x7C character.

Other useful stuff:

- By default vim doesn't treat `-` as part of a word (for motions, search, autocomplete, etc). Use `set iskeyword+=-` to change this. This is the changed in my `vimrc` but a useful one to remember.

## Effective Tmux

Most essential commands:

- Option - h/l - move left/right between tabs


## Effective Vim

Here's some of the stuff I find most useful.

### The Golden Rule

If you repeat yourself or do dumb formatting crap, find the idiomatically correct way to do something or use a plugin. Always look up native ways first.

### Process & Copy Buffer

Grep all lines with `secret` and put on clipboard:

```vim
:!cat % | grep secret | pbcopy
```

This example could be used to grab all references to GitHub secrets from a buffer.

### NerdTree

- `C-n` to toggle/focus the tree
- `R` in the tree to refresh
- `<leader>t` to 'tree' the current file, i.e. show the current buffer in NerdTree.

### fzf-lua

- `<leader>space` buffers
- `<leader>f` files
- `<leader>g` ripgrep (works amazingly)
