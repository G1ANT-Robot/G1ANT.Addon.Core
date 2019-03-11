# if

## Syntax

```G1ANT
if condition ⟦text⟧
end
```

## Description

This command allows to execute a block of commands if a given condition is true. The block ends with the `end` command.

| Argument | Type | Required | Default Value | Description |
| -------- | ---- | -------- | ------------- | ----------- |
|`condition`| [bool](G1ANT.Language/G1ANT.Language/Structures/BooleanStructure.md) | yes |  | If the condition expressed with a C# snippet returns true, the robot will execute everything that is between `if` and `end`, or `if` and `else if`, or `if` and `else` commands |
| `if`           | [bool](G1ANT.Language/G1ANT.Language/Structures/BooleanStructure.md) | no       | true                                                        | Executes the command only if a specified condition is true   |
| `timeout`      | [timespan](G1ANT.Language/G1ANT.Language/Structures/TimeSpanStructure.md) | no       | [♥timeoutcommand](G1ANT.Manual/appendices/common-arguments.md) | Specifies time in milliseconds for G1ANT.Robot to wait for the command to be executed |
| `errorcall`    | [procedure](G1ANT.Language/G1ANT.Language/Structures/ProcedureStructure.md) | no       |                                                             | Name of a procedure to call when the command throws an exception or when a given `timeout` expires |
| `errorjump`    | [label](G1ANT.Language/G1ANT.Language/Structures/LabelStructure.md) | no       |                                                             | Name of the label to jump to when the command throws an exception or when a given `timeout` expires |
| `errormessage` | [text](G1ANT.Language/G1ANT.Language/Structures/TextStructure.md) | no       |                                                             | A message that will be shown in case the command throws an exception or when a given `timeout` expires, and no `errorjump` argument is specified |
| `errorresult`  | [variable](G1ANT.Language/G1ANT.Language/Structures/VariableStructure.md) | no       |                                                             | Name of a variable that will store the returned exception. The variable will be of [error](G1ANT.Language/G1ANT.Language/Structures/ErrorStructure.md) structure  |

For more information about `if`, `timeout`, `errorcall`, `errorjump`, `errormessage` and `errorresult` arguments, see [Common Arguments](G1ANT.Manual/appendices/common-arguments.md) page.

The `if` command may also contain other commands: `else if` and `else`.

If the first condition after the `if` command is not met, the robot will check whether the next condition after the `else if` command is met. It will repeat these actions as many times as there are `else if` commands in the block between the `if` and `end` commands, or if one condition is finally met (then the robot will execute the block between the `else` commands).

If no condition is met, the robot will execute the command block between the `else` and `end` commands.
See the example below for a clearer picture of how it works.

## Example

In the following example a user is asked to enter a digit, which is then stored in the `♥number` variable. This variable is checked for its value and depending on the result, an appropriate message is displayed in a dialog box:

```G1ANT
dialog.ask ‴Enter a digit (0-9):‴ result ♥number
if ♥number=="1"
   dialog one
  else if ♥number=="2"
    dialog two
  else if ♥number=="3"
    dialog three
  else
    dialog ‴Your digit is greater than 3 or less than 1‴
end
```
