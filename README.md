<div align="center">

## SnadBoy Imitator \(Password Unmasker\)


</div>

### Description

You've all seen the *'s that are used to hide passwords. This program reveals the text behind these stars. Extremely easy to follow, only 19 lines of code, including API declarations. Easy enough for an intermediate beginner.
 
### More Info
 
Create one textbox named Text1 and one timer named Timer1.


<span>             |<span>
---                |---
**Submitted On**   |
**By**             |[Matt Fredrikson](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/matt-fredrikson.md)
**Level**          |Beginner
**User Rating**    |5.0 (20 globes from 4 users)
**Compatibility**  |VB 4\.0 \(32\-bit\), VB 5\.0, VB 6\.0
**Category**       |[Windows API Call/ Explanation](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/windows-api-call-explanation__1-39.md)
**World**          |[Visual Basic](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/visual-basic.md)
**Archive File**   |[](https://github.com/Planet-Source-Code/matt-fredrikson-snadboy-imitator-password-unmasker__1-8121/archive/master.zip)





### Source Code

```
'(C) Copyright 1999 Matt Fredrikson
Private Declare Function WindowFromPoint Lib "user32.dll" (ByVal xPoint As Long, ByVal yPoint As Long) As Long
Private Declare Function SendMessage Lib "user32.dll" Alias "SendMessageA" (ByVal hWnd As Long, ByVal Msg As Long, wParam As Any, lParam As Any) As Long
Private Declare Function GetCursorPos Lib "user32.dll" (lpPoint As POINT_TYPE) As Long
Private Type POINT_TYPE
 x As Long
 y As Long
End Type
Private Const WM_GETTEXT = &HD
Private Const TXT_LEN = 100
Private Sub Timer1_Timer()
 Dim ppoint As POINT_TYPE
 Dim ttxt As String
 ttxt = Space(100) 'Give space for window text
 errval = GetCursorPos(ppoint) 'Get Cursor Point
 thwnd = WindowFromPoint(ppoint.x, ppoint.y) 'Get window handle of window under cursor
 errval = SendMessage(thwnd, WM_GETTEXT, ByVal TXT_LEN, ByVal ttxt) 'Get text of that window
 ttxt = RTrim(ttxt) 'Remove Spaces
 Text1.Text = ttxt 'Display results
End Sub
```

