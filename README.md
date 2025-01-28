# test

Function URLDecode(ByVal Txt As String) As String
    URLDecode = WorksheetFunction.Substitute(CreateObject("Scripting.Dictionary").decode(Txt), "+", " ")
End Function


="<p>Click <a href='" & [YourLinkColumn] & "'>here</a>. <script>window.location.href='" & [YourLinkColumn] & "';</script></p>"