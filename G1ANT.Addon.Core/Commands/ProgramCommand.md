# program

## Syntax

```G1ANT
program name ⟦text⟧ arguments ⟦text⟧ wait ⟦bool⟧
```

## Description

The `program` command runs the executable file of a program installed on a user’s system.

| Argument | Type | Required | Default Value | Description |
| -------- | ---- | -------- | ------------- | ----------- |
|`name`| [text](https://manual.g1ant.com/link/G1ANT.Language/G1ANT.Language/Structures/TextStructure.md) | yes |  | Program name or path to a program’s executable file; if a non-executable file is provided, it will be open in the default application associated with this file type |
|`arguments`| [text](https://manual.g1ant.com/link/G1ANT.Language/G1ANT.Language/Structures/TextStructure.md) | no |  | Argument to pass to the launched application |
|`wait`| [bool](https://manual.g1ant.com/link/G1ANT.Language/G1ANT.Language/Structures/BooleanStructure.md) | no | [♥programwait](https://manual.g1ant.com/link/G1ANT.Language/G1ANT.Addon.Core/Variables/ProgramWaitVariable.md) | If set to `true`, the robot executing the `program` command waits for a program to be ready for input. |
| `result`       | [variable](https://manual.g1ant.com/link/G1ANT.Language/G1ANT.Language/Structures/VariableStructure.md) | no       | `♥result`                                                   | Name of a variable where the command's result will be stored |
| `if`           | [bool](https://manual.g1ant.com/link/G1ANT.Language/G1ANT.Language/Structures/BooleanStructure.md) | no       | true                                                        | Executes the command only if a specified condition is true   |
| `timeout`      | [timespan](https://manual.g1ant.com/link/G1ANT.Language/G1ANT.Language/Structures/TimeSpanStructure.md) | no       | [♥timeoutcommand](https://manual.g1ant.com/link/G1ANT.Language/G1ANT.Addon.Core/Variables/TimeoutCommandVariable.md) | Specifies time in milliseconds for G1ANT.Robot to wait for the command to be executed |
| `errorcall`    | [procedure](https://manual.g1ant.com/link/G1ANT.Language/G1ANT.Language/Structures/ProcedureStructure.md) | no       |                                                             | Name of a procedure to call when the command throws an exception or when a given `timeout` expires |
| `errorjump`    | [label](https://manual.g1ant.com/link/G1ANT.Language/G1ANT.Language/Structures/LabelStructure.md) | no       |                                                             | Name of the label to jump to when the command throws an exception or when a given `timeout` expires |
| `errormessage` | [text](https://manual.g1ant.com/link/G1ANT.Language/G1ANT.Language/Structures/TextStructure.md) | no       |                                                             | A message that will be shown in case the command throws an exception or when a given `timeout` expires, and no `errorjump` argument is specified |
| `errorresult`  | [variable](https://manual.g1ant.com/link/G1ANT.Language/G1ANT.Language/Structures/VariableStructure.md) | no       |                                                             | Name of a variable that will store the returned exception. The variable will be of [error](https://manual.g1ant.com/link/G1ANT.Language/G1ANT.Language/Structures/ErrorStructure.md) structure  |

For more information about `if`, `timeout`, `errorcall`, `errorjump`, `errormessage` and `errorresult` arguments, see [Common Arguments](https://manual.g1ant.com/link/G1ANT.Manual/appendices/common-arguments.md) page.

## Example 1

If a program is installed in Windows, you can use just the name of its executable file:

```G1ANT
program notepad
```

## Example 2

You can also specify the exact executable file in its full path:

```G1ANT
program ‴C:\Program Files\7-Zip\7zG.exe‴
```

## Example 3

Here, the specified non-executable file will be opened in its associated application — Excel or other spreadsheet program in this case:

```G1ANT
program C:\Documents\report.xls
```

## Example 4

In the following example the `program` command uses an argument that is passed to the application it launches. Every program has its own list of arguments, and in case of Notepad here, the `/p` argument means to print the text file located on the user’s Desktop (the filepath is stored in the `♥file` variable).

```G1ANT
♥file = ♥environment⟦USERPROFILE⟧\Desktop\test2.txt
program notepad arguments ‴/p ♥file‴
```

> **Note:** More information on the `♥environment` special variable [here](https://manual.g1ant.com/link/G1ANT.Language/G1ANT.Addon.Core/Variables/EnvironmentVariable.md) and [here](https://manual.g1ant.com/link/G1ANT.Manual/appendices/environment.md).