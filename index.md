<html lang="ja">
  <head>
    <meta charset="UTF-8">
  </head>
  <body>
    <script type="text/javascript">
    window.moveTo(screen.width/2-150, screen.height/2-150);
    window.resizeTo(400, 300);
  <!---->
    var cdoMsg = new ActiveXObject("CDO.Message");
    var schemas = "http://schemas.microsoft.com/cdo/configuration/";
  <!---->
    cdoMsg.Configuration.Fields.Item(schemas+"sendusing") = 2;
    cdoMsg.Configuration.Fields.Item(schemas+"smtpserver") = "★smtp-server★";
    cdoMsg.Configuration.Fields.Item(schemas+"smtpserverport") = 25;
    cdoMsg.Configuration.Fields.Item(schemas + "smtpauthenticate") = true;
    cdoMsg.Configuration.Fields.Item(schemas + "sendusername") = "★username★";
    cdoMsg.Configuration.Fields.Item(schemas + "sendpassword") = "★password★";
    cdoMsg.Configuration.Fields.Item(schemas + "smtpusessl") = true;
    cdoMsg.Configuration.Fields.Update();
    cdoMsg.From     = "★from-address★";
  <!---->
    function send(){
        cdoMsg.To       = document.getElementById("mail_to").value;
        cdoMsg.Subject  = document.getElementById("mail_subject").value;
        cdoMsg.TextBody = document.getElementById("mail_textbody").value;
        // ファイルを添付
        cdoMsg.AddAttachment(document.getElementById("file1").value); 
        try {
            cdoMsg.Send();
        } catch(e) {
            alert(e.message);
        }
    }
    </script>
    <div style="background-color : #CCC;">
    <table>
        <tr>
            <td>宛先</td>
            <td><input id="mail_to" type="text" placeholder="xxx@yyy.com"></td>
        </tr>
        <tr>
            <td>件名</td>
            <td><input id="mail_subject" type="text" placeholder="タイトル"></td>
        </tr>
        <tr>
            <td>本文</td>
            <td><textarea id="mail_textbody" cols="35" rows="10" placeholder="本文"></textarea></td>
        </tr>
        <tr>
            <td colspan="2">
            <input id="file1" type="file" /><div id="output"></div></td>
        </tr>
    </table>
    <input id="send_button"  type="button" value="送信" onClick="send()">
    </div>
  </body>
</html>
