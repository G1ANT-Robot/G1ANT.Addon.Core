# clipboard

## Syntax

```G1ANT
♥clipboard = ⟦text⟧
```

## Description

Reads clipboard content or inserts new content into clipboard.

## Example 1

```G1ANT
program acrord32
keyboard ⋘ALT⋙⋘DOWN⋙⋘1⋙
keyboard ⋘CTRL+A⋙⋘CTRL+C⋙
♥doc1 = ♥clipboard
keyboard ⋘ALT⋙⋘DOWN⋙⋘2⋙
keyboard ⋘CTRL+A⋙⋘CTRL+C⋙
♥doc2 = ♥clipboard
program notepad
keyboard ‴First PDF:⋘ENTER⋙♥doc1⋘ENTER⋙‴
keyboard ‴Second PDF:⋘ENTER⋙♥doc2⋘ENTER⋙‴
```

If you use Acrobat Reader application, the script above will launch this program, open the first of its recent files, copy the content to clipboard and store it in the `♥doc1` variable, then do the same with the second file and the `♥doc2` variable. Finally, the Robot will launch Notepad and type in the content of both PDFs.

## Example 2

In the following example you insert some text into clipboard and then you paste it with the standard **Ctrl+V** keyboard shortcut:

```G1ANT
♥clipboard = ‴This is the clipboard content‴
program notepad
keyboard ⋘CTRL+V⋙
```
