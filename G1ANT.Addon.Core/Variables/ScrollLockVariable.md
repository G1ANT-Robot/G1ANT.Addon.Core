# scrolllock

## Syntax

```G1ANT
♥scrolllock = ⟦bool⟧
```

## Description

Switches ScrollLock on/off.

## Example

```G1ANT
program scalc
waitfor.window title ✱Calc
keyboard 1⋘TAB⋙2⋘TAB⋙3⋘TAB⋙4⋘TAB⋙5⋘TAB⋙⋘HOME⋙
keyboard 1⋘ENTER⋙2⋘ENTER⋙3⋘ENTER⋙4⋘ENTER⋙5⋘ENTER⋙
keyboard ⋘CTRL+HOME⋙
keyboard ⋘DOWN 4⋙
delay 1
keyboard ⋘RIGHT 4⋙
delay 1
keyboard ⋘CTRL+HOME⋙
♥scrolllock = true
keyboard ⋘DOWN 4⋙
delay 1
keyboard ⋘RIGHT 4⋙
delay 1
♥scrolllock = false
keyboard ⋘CTRL+HOME⋙
```

This script shows the difference of using cursor keys with ScrollLock off and on while in LibreOffice Calc: when you press the arrow keys, the selection moves between individual cells. However, if you press the arrow keys when ScrollLock is on, you scroll one row or column at a time.

**Note:** If you have Excel, just replace `scalc` with `excel` in the first line and `Calc` with `Excel` in the second line.
