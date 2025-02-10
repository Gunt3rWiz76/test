# test

Function URLDecode(ByVal Txt As String) As String
    URLDecode = WorksheetFunction.Substitute(CreateObject("Scripting.Dictionary").decode(Txt), "+", " ")
End Function


    ="<p>Click <a href='" & [YourLinkColumn] & "'>here</a>. <scrip
t>window.location.href='" & [YourLinkColumn] & "';</script></p>"

Function RemoveHTMLTags(ByVal txt As String) As String
    Dim RegExp As Object
    Set RegExp = CreateObject("VBScript.RegExp")
    
    RegExp.Pattern = "<[^>]+>"
    RegExp.Global = True
    RemoveHTMLTags = RegExp.Replace(txt, "")
    
    Set RegExp = Nothing
End Function