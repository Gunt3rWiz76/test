# test

Function URLDecode(ByVal Txt As String) As String
    URLDecode = WorksheetFunction.Substitute(CreateObject("Scripting.Dictionary").decode(Txt), "+", " ")
End Function
