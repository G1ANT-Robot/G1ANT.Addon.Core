# activewindow

## Syntax

```G1ANT
⟦text⟧ = ♥activewindow
```

## Description

Provides the title of the current active window.

## Example

```G1ANT
program notepad
♥notepadWindowTitle = ♥activewindow
program calc
♥calcWindowTitle = ♥activewindow
window ♥notepadWindowTitle
window ♥calcWindowTitle
```

This script will open Notepad and store its window title in the `♥notepadWindowTitle` variable. Then it will do the same with Calculator and the `♥calcWindowTitle` variable. These two variables are then used to switch focus with the `window` command.
