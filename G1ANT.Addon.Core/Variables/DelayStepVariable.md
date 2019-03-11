# delaystep

## Syntax

```G1ANT
♥delaystep = ⟦integer⟧
```

## Description

Determines the delay value (in ms) for a command to proceed; the default value is 500.

## Example

```G1ANT
♥delaystep = 3000
program notepad
keyboard Wait...
keyboard ‴ for...‴
keyboard ‴ IT!‴
```

The script above will execute each command with a 3-second delay.
