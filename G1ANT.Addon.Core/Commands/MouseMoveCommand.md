# mouse.move

## Syntax

```G1ANT
mouse.move position ⟦point⟧ relative ⟦bool⟧ wait ⟦integer⟧
```

## Description

This command moves a mouse cursor to the specified position.

| Argument | Type | Required | Default Value | Description |
| -------- | ---- | -------- | ------------- | ----------- |
|`position`| [point](https://manual.g1ant.com/link/G1ANT.Language/G1ANT.Language/Structures/PointStructure.md) | yes |  | XY coordinates of a pixel to move a mouse cursor to |
|`relative`| [bool](https://manual.g1ant.com/link/G1ANT.Language/G1ANT.Language/Structures/BooleanStructure.md) | no | true | If set to `true`, the position is relative to the active window |
|`wait`| [integer](https://manual.g1ant.com/link/G1ANT.Language/G1ANT.Language/Structures/IntegerStructure.md) | no |  | Determines time in milliseconds between mouse 'jumps' to the specified position |
| `if`           | [bool](https://manual.g1ant.com/link/G1ANT.Language/G1ANT.Language/Structures/BooleanStructure.md) | no       | true                                                        | Executes the command only if a specified condition is true   |
| `timeout`      | [timespan](https://manual.g1ant.com/link/G1ANT.Language/G1ANT.Language/Structures/TimeSpanStructure.md) | no       | [♥timeoutcommand](https://manual.g1ant.com/link/G1ANT.Language/G1ANT.Addon.Core/Variables/TimeoutCommandVariable.md) | Specifies time in milliseconds for G1ANT.Robot to wait for the command to be executed |
| `errorcall`    | [procedure](https://manual.g1ant.com/link/G1ANT.Language/G1ANT.Language/Structures/ProcedureStructure.md) | no       |                                                             | Name of a procedure to call when the command throws an exception or when a given `timeout` expires |
| `errorjump`    | [label](https://manual.g1ant.com/link/G1ANT.Language/G1ANT.Language/Structures/LabelStructure.md) | no       |                                                             | Name of the label to jump to when the command throws an exception or when a given `timeout` expires |
| `errormessage` | [text](https://manual.g1ant.com/link/G1ANT.Language/G1ANT.Language/Structures/TextStructure.md) | no       |                                                             | A message that will be shown in case the command throws an exception or when a given `timeout` expires, and no `errorjump` argument is specified |
| `errorresult`  | [variable](https://manual.g1ant.com/link/G1ANT.Language/G1ANT.Language/Structures/VariableStructure.md) | no       |                                                             | Name of a variable that will store the returned exception. The variable will be of [error](https://manual.g1ant.com/link/G1ANT.Language/G1ANT.Language/Structures/ErrorStructure.md) structure  |

For more information about `if`, `timeout`, `errorcall`, `errorjump`, `errormessage` and `errorresult` arguments, see [Common Arguments](https://manual.g1ant.com/link/G1ANT.Manual/appendices/common-arguments.md) page.

## Example

This is a modified example from the [`mouse.click`](https://manual.g1ant.com/link/G1ANT.Addon.Core-1/G1ANT.Addon.Core/Commands/MouseClickCommand.md) command to make a rectangular selection on the Windows Desktop. With a mouse cursor set at the starting position, the left mouse button is clicked and hold. Then the cursor is moved to an intermediate position, and the `wait` argument slows down the movement so that you can see the effects. When this intermediate position is reached, the second `mouse.click` command moves the cursor farther to the destination point and the left mouse button is released.

```G1ANT
keyboard ⋘WIN+D⋙
mouse.click 664⫽346 relative false type down
mouse.move 1100⫽500 wait 1000 relative false
mouse.click 1362⫽671 relative false type up
```
