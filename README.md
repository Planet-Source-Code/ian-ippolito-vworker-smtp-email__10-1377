<div align="center">

## SMTP email


</div>

### Description

One of the bad things about old/classic ASP is its lack of easy built-in support for something as easy as sending an email. Most developers (including myself) ended up having to purchase a seperate email component such as ASPQMail, or SA-Mail. Well, now with ASP.NET that is no longer necessary...it's included in the box and is REALLY simple. Here's how to use it.
 
### More Info
 
There's a little wrinkle in that the smtpserver object CANNOT be created "as New". Don't worry...it still works.


<span>             |<span>
---                |---
**Submitted On**   |
**By**             |[Ian Ippolito \(vWorker\)](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/ian-ippolito-vworker.md)
**Level**          |Beginner
**User Rating**    |4.0 (16 globes from 4 users)
**Compatibility**  |ASP\.NET
**Category**       |[Internet/ Browsers/ HTML](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/internet-browsers-html__10-9.md)
**World**          |[\.Net \(C\#, VB\.net\)](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/net-c-vb-net.md)
**Archive File**   |[](https://github.com/Planet-Source-Code/ian-ippolito-vworker-smtp-email__10-1377/archive/master.zip)





### Source Code

```
Dim objMailMessage As New System.Web.Mail.MailMessage()
Dim objSmtpServer As System.Web.Mail.SmtpMail
  objMailMessage.From = "me@from.com"
  objMailMessage.To = "you@to.com"
  objMailMessage.Subject = "My Subject"
  objMailMessage.Body = "my body" 'set body
  objMailMessage.BodyFormat = System.Web.Mail.MailFormat.Html 'set format
  objMailMessage.Priority = System.Web.Mail.MailPriority.High 'priority of message
  'note:next line only required if the local machine doesn't have a working SMTP server
  'replace value with the name of your own smtp server
  objSmtpServer.SmtpServer = "smtp.mydomain.com" 'set SMTP server
  Try
    objSmtpServer.Send(objMailMessage)
  Catch ex As Exception
    'you can add error handling here
    'throw it back out
    Throw ex
  End Try
```

