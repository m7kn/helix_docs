# Helix Editor Documentation

## Introduction

Helix is a modern, modal text editor. Modal editing means that we can work with text in different modes. The two main modes are:

- Normal mode: Keys execute commands instead of typing characters
- Insert mode: Used for typing characters

## Basic Movement

Cursor movement in Normal mode:

- `h` - left
- `j` - down
- `k` - up
- `l` - right

## Exiting

- `:q` or `:quit` - quit (only if no unsaved changes)
- `:q!` or `:quit!` - quit discarding unsaved changes
- `:wq` or `:write-quit` - save and quit

## Deletion and Insertion

- `d` - delete character under cursor
- `i` - enter Insert mode before cursor
- `a` - enter Insert mode after cursor (append)
- `I` - enter Insert mode at start of line
- `A` - enter Insert mode at end of line
- `o` - insert new line below and enter Insert mode
- `O` - insert new line above and enter Insert mode

## Saving

- `:w` or `:write` - save current file
- Optional filename/path can be specified

## Movement and Selection

- `w` - forward to start of next word
- `e` - forward to end of current word
- `b` - backward to start of current word
- `W`, `E`, `B` - same as lowercase variants but only stop at whitespace

## Change Commands

- `c` - delete selected text and enter Insert mode
- `d` - delete selected text
- Number + command: execute command multiple times (e.g., `2w`)

## Selection Mode

- `v` - toggle selection mode
- `x` - select entire line
- `;` - collapse selection to cursor

## Copy and Paste

- `y` - copy (yank) selected text
- `p` - paste after cursor
- `P` - paste before cursor
- `Space + y/p` - operations with system clipboard

## Searching

- `/` - search forward
- `?` - search backward
- `n` - next match
- `N` - previous match
- Supports regular expressions

## Multiple Cursors

- `C` - duplicate cursor to next matching line
- `Alt-C` - duplicate cursor to previous matching line
- `s` - select matches in selected text
- `&` - align selections

## Other Functions

- `u` - undo
- `U` - redo
- `.` - repeat last insertion
- `~` - toggle case
- `` ` `` - convert to lowercase
- `Alt-`` ` ``- convert to uppercase
- `Ctrl-c` - comment/uncomment line

## Window Management

- `Ctrl-w nv` - new vertical split
- `Ctrl-w ns` - new horizontal split
- `Ctrl-w h/j/k/l` - move between windows
- `Ctrl-w q` - close current window
- `Ctrl-w o` - close all other windows
- `:vs` / `:hs` - open split with filename

## Match Mode

Match mode, activated with `m` key, is used for handling brackets and other paired characters:

- `mm` - jump to matching character
- `mi(` - select content between parentheses
- `ma(` - select parentheses and their content
- `ms(` - surround selected text with parentheses
- `md(` - delete surrounding parentheses
- `mr([` - replace parentheses with different type

Other paired characters can be used instead of parentheses, e.g., `{}`, `[]`, `""`, `''`.

## Register Usage

Registers are character-identified containers that can serve different purposes:
- Copying/cutting text
- Storing search expressions
- Storing macros

- `"<ch>` - select register (e.g., `"a`)
- Save to selected register with `y` command
- Paste from selected register with `p` or `P`

## Macros

Macros are command sequences that can be replayed later:

- `Q` - start macro recording (default to `@` register)
- `Q` - end macro recording
- `q` - play macro from `@` register
- `"<ch>Q` - record macro to specific register
- `"<ch>q` - play macro from specific register

## Search and Selection

- `*` - search for word under cursor
- `n`/`N` in `v` mode - add new selection to next/previous match
- `Ctrl-s` - save position to jumplist
- `Ctrl-i`/`Ctrl-o` - move forward/backward in jumplist
- `gw` - show two-character labels for quick navigation

## Selection Management

- `)` / `(` - move primary selection forward/backward
- `Alt-,` - remove primary selection
- `Alt-)` / `Alt-(` - swap selection contents
- `S` - split selections based on regex pattern

## Line Manipulation

- `J` - join selected lines
- `>` / `<` - increase/decrease indentation
- `Ctrl-a` / `Ctrl-x` - increment/decrement number

## Advanced Window Management

- `Ctrl-w t` - transpose window layout
- `Ctrl-w H/J/K/L` - move window in given direction
- `Space f` - open file picker
  - `Ctrl-v` - open selected file in vertical split
  - `Ctrl-s` - open selected file in horizontal split

## Tips and Tricks

1. Most commands can be combined:
   - Number + command: multiple execution
   - Register + command: operation with specific register
   - Movement + operation: operation on text selected by movement

2. Efficient editing strategies:
   - Use `.` command for repetitive changes
   - Multiple cursors for parallel editing
   - Match mode for structured text handling
   - Macros for complex operation sequences

3. Search and replace operation:
   - Selection in affected area
   - `s` command to select pattern matches
   - `c` command to execute change

4. Window management patterns:
   - Vertical split for parallel code and documentation editing
   - Horizontal split for comparing different file parts
   - Multiple windows for viewing reference materials

## Configuration

Helix can be configured through:
- `~/.config/helix/config.toml` - general settings
- `~/.config/helix/languages.toml` - language-specific settings

For detailed configuration options, refer to the official documentation.

## Summary

Helix is a powerful, modern text editor that:
- Uses modal editing for efficiency
- Provides rich command and function handling
- Supports multiple cursors and selections
- Enables flexible window management
- Is configurable and extensible

For effective use:
1. Learn basic movement and editing commands
2. Gradually master advanced features
3. Develop configuration tailored to your workflows
4. Regularly practice using new commands
