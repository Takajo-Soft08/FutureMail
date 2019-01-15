<html lang="ja">
  <head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <title>メール送信テスト画面</title>
    <link rel="stylesheet" href="">
    <script src="javascript/index.js" type="text/javascript" charset="utf-8" ></script>
  </head>
  <body>
    <input type='hidden' id='hidden_data' value='送信したい情報をここに記載'>
    <button id='mail'>メール送信</button>
    <script>
# index.js
/**
 * メーラーを起動してメールを送信する
 */

window.onload = function() {

    /**
   * メールに記載する情報を格納する変数
   */
    var address, subject, body, hiddenData;
    var sendmail = document.getElementById('mail');

    sendmail.onclick = function() {

        // メールに記載したい情報をhiddenタグから取得
        hiddenData = document.getElementById('hidden_data').value;
        address = '~@co.jp';
        subject = '件名';
        body = '本文' + hiddenData;

        location.href = 'mailto:' + address + '?subject=' + subject + '&body=' + body;
    };

};      
    </script>
    
    <div align="center">
      <h1>Search Chords Mode</h1>
      <hr size="2" width="90%" align="center" color="blue">
      <h2>単音からコードを検索する</h2>
      <a href="https://takajo-soft08.github.io/SearchChord/Parts/FromSolo.html">
         <input type="button" value="Search Chord">
      </a>
      <hr size="2" width="30%" align="center" color="grey">
      <h2>コードから単音を検索する</h2>
      <a href="https://takajo-soft08.github.io/SearchChord/Parts/FromChord.html">
         <input type="button" value="Search Notes">
      </a>
      <hr size="2" width="30%" align="center" color="grey">
      <h2>使用方法</h2>
      <a href="https://takajo-soft08.github.io/SearchChord/Parts/HowToUse.html">
         <input type="button" value="How To Use?">
      </a>
      <hr size="2" width="30%" align="center" color="grey">
      <h2>コード解釈</h2>
      <a href="https://takajo-soft08.github.io/SearchChord/Parts/Explanation.html">
         <input type="button" value="Explanation">
      </a>      
      <hr size="2" width="80%" align="center" color="orange">
      <h6 align="right">※この検索システムは、個人的にまとめたため、信頼度は低いです。あらかじめご了承ください。</h6>
    </div>
    <div align="right">
      <a href="https://takajo-soft08.github.io/SearchChord/" align="right">
        Back To Home
      </a>
    </div>
  </body>
</html>
