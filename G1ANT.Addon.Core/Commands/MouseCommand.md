# mouse

## Syntax

```G1ANT
mouse position ⟦point⟧ button ⟦text⟧ relative ⟦bool⟧
```

## Description

This command moves mouse cursor to the required position and performs a left or a right click.

The click action can be combined with a key press action in the `button` argument by adding `+` and the name of a key to the mouse button name. Available keys:

- `+shift`
- `+control` or `+ctrl`
- `+windows` or `+win`

| Argument | Type | Required | Default Value | Description |
| -------- | ---- | -------- | ------------- | ----------- |
|`position`| [point](https://manual.g1ant.com/link/G1ANT.Language/G1ANT.Language/Structures/PointStructure.md) | yes |  | Screen coordinates at which a mouse click will be performed |
|`button`| [text](https://manual.g1ant.com/link/G1ANT.Language/G1ANT.Language/Structures/TextStructure.md) | no | left | Mouse button to be clicked: `left` or `right`. Can be combined with a key press action: `+shift`, `+ctrl`, `+win` |
|`relative`| [bool](https://manual.g1ant.com/link/G1ANT.Language/G1ANT.Language/Structures/BooleanStructure.md) | no | true | If set to true, the mouse position is relative to the active window |
| `if`           | [bool](https://manual.g1ant.com/link/G1ANT.Language/G1ANT.Language/Structures/BooleanStructure.md) | no       | true                                                        | Executes the command only if a specified condition is true   |
| `timeout`      | [timespan](https://manual.g1ant.com/link/G1ANT.Language/G1ANT.Language/Structures/TimeSpanStructure.md) | no       | [♥timeoutcommand](https://manual.g1ant.com/link/G1ANT.Language/G1ANT.Addon.Core/Variables/TimeoutCommandVariable.md) | Specifies time in milliseconds for G1ANT.Robot to wait for the command to be executed |
| `errorcall`    | [procedure](https://manual.g1ant.com/link/G1ANT.Language/G1ANT.Language/Structures/ProcedureStructure.md) | no       |                                                             | Name of a procedure to call when the command throws an exception or when a given `timeout` expires |
| `errorjump`    | [label](https://manual.g1ant.com/link/G1ANT.Language/G1ANT.Language/Structures/LabelStructure.md) | no       |                                                             | Name of the label to jump to when the command throws an exception or when a given `timeout` expires |
| `errormessage` | [text](https://manual.g1ant.com/link/G1ANT.Language/G1ANT.Language/Structures/TextStructure.md) | no       |                                                             | A message that will be shown in case the command throws an exception or when a given `timeout` expires, and no `errorjump` argument is specified |
| `errorresult`  | [variable](https://manual.g1ant.com/link/G1ANT.Language/G1ANT.Language/Structures/VariableStructure.md) | no       |                                                             | Name of a variable that will store the returned exception. The variable will be of [error](https://manual.g1ant.com/link/G1ANT.Language/G1ANT.Language/Structures/ErrorStructure.md) structure  |

For more information about `if`, `timeout`, `errorcall`, `errorjump`, `errormessage` and `errorresult` arguments, see [Common Arguments](https://manual.g1ant.com/link/G1ANT.Manual/appendices/common-arguments.md) page.

## Example

This example shows how to use the `mouse` command to perform a left click with **Shift** key pressed on the first icon on the Windows Desktop (usually it’s the Recycle Bin):

```G1ANT
keyboard ⋘WIN+D⋙
mouse 36⫽30 button left+shift relative false
```

