<div align="center">

## A VB\.NET sample showing how to send emails to recipients


</div>

### Description

This Console application, written in Visual Basic .NET, shows how to send (multiple) email messages to (multiple) recipients. Code sample is simple. However, advanced features like embedded attachments, rich text formatting etc. are possible
 
### More Info
 


<span>             |<span>
---                |---
**Submitted On**   |
**By**             |[Roby Kott](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/roby-kott.md)
**Level**          |Beginner
**User Rating**    |2.6 (34 globes from 13 users)
**Compatibility**  |VB\.NET, ASP\.NET
**Category**       |[Miscellaneous](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/miscellaneous__10-1.md)
**World**          |[\.Net \(C\#, VB\.net\)](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/net-c-vb-net.md)
**Archive File**   |[](https://github.com/Planet-Source-Code/roby-kott-a-vb-net-sample-showing-how-to-send-emails-to-recipients__10-767/archive/master.zip)





### Source Code

```
' Description:Send email(s) to an SMTP server,
' to multiple recipients, with attachments etc.
' Easy to use, no IIS or MS SMTP service required.
'
' You need the FREEWARE AEmail.dll to run the sample.
' Download it from http://www.vahland.com/pub/aemail.dll
' and register it on your machine.
' Then, choose 'Add Reference' from your Solutions Window,
' and 'Add' the 'ActivEmail 2.1 Type Library'.
'
' Read http://www.vahland.com/pub/aemail.htm for more info.
Imports AEMAILLib
Module Module1
  Sub Main()
    Dim objSmtpMail As AEMAILLib.SmtpMailClass
    Console.WriteLine("Be sure To have the FREEWARE AEmail.dll registered on your system,")
    Console.WriteLine("and add the ActivEmail 2.1 Type Library to your references.")
    Console.WriteLine("Check out the code header about how to obtain the free component.")
    Console.WriteLine("")
    objSmtpMail = New AEMAILLib.SmtpMailClass()
    objSmtpMail.HostName = "yourmailserver.yourdomain.dom"
    objSmtpMail.FromName = "Senders Name"
    objSmtpMail.FromAddress = "sender@sendersdomain.dom"
    objSmtpMail.AddTo("john.doe@domain.dom", "John Doe")
    objSmtpMail.Subject = "My Subject"
    ' If you want, you can include attachment, multiple recipients, rich text formatting etc.
    ' It's not included in this sample to keep sample straight.
    objSmtpMail.Body = "Here is the body text" & vbCrLf & "Best regards..."
    objSmtpMail.Send()
    Console.WriteLine("Send, result: " & objSmtpMail.LastError.ToString())
    objSmtpMail.Clear() ' To use the same object again with all properties cleared
  End Sub
End Module
```

