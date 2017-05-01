# VSCode (Visual Studio Code)
VSCode の機能拡張 Debugger for Chromeで、webページをデバッグ、ステップ実行する

version 1.0.1

## **インストール・設定**

1. VSCodeのインストール

    以下のサイトよりダウンロードしてインストール

    https://code.visualstudio.com/

    ※今回はversion1.11.1

1. VSCodeを起動する

1. F1キーを押し、コマンドラインに ext install と入力し、表示される選択肢の中の”拡張機能のインストール"を選択

1. 左上の入力欄にChromeと入力しフィルタし、”Debugger for Chrome” を選択しインストールし再起動

1. プロジェクトディレクトリの作成

    ローカルPCで、プロジェクトディレクトリをどこかに作成する

    例； C:\Users\a_kaneko\Documents\vscode

1. VSCodeを起動し、ファイルメニュー＞フォルダを開く　よりプロジェクトディレクトリを開く

1. 左メニューのデバッグアイコンをクリック

1. 上部の設定アイコンが赤くなっているのでクリックすると選択肢がでるのでChromeを選択

    すると、.vscode/launch.json という設定ファイルが自動生成される

    ```
    {
        "version": "0.2.0",
        "configurations": [
            {
                "type": "chrome",
                "request": "launch",
                "name": "Launch Chrome against localhost",
                "url": "http://localhost:8080",
                "webRoot": "${workspaceRoot}"
            },
            {
                "type": "chrome",
                "request": "attach",
                "name": "Attach to Chrome",
                "port": 9222,
                "webRoot": "${workspaceRoot}"
            }
        ]
    }
    ```
    launch.json (chrome)

1. 設定の名称で

    - Launch Chrome against localhost
    - Attach to Chrome

    の２つが自動生成される。Attach to ChromeでWebサイトや、ローカルサイト、ローカルファイルのデバッグが可能。

**デバッグ許可モードオプションでChrome起動のバッチ作成**

通常のChromeの起動では、VSCodeでデバッグが許可されないので、デバッグ許可モードオプションをつけてChromeを起動する必要がある。
起動しやすいように以下1行を記述したバッチファイル(chrome_remote_debug.bat)を作成しておく

  "C:\Program Files (x86)\Google\Chrome\Application\chrome.exe" --remote-debugging-port=9222

※パス部分は各自変更ください

## **VSCcodeで、Chromeの画面（Javascript)をデバッグ、ステップ実行する**

1. デバッグ許可モードでChromeを起動

    あらかじめ用意しておいたバッチ

    C:\Users\a_kaneko\Documents\vscode\chrome_remote_debug.bat

    をダブルクリックし、デバッグ許可モードでChromeを起動（これで起動しないとデバッグできない）

    ※Chrome側で、デバッグモードで立ち上げたか確認する方法

    URLの箇所に、chrome://version と打つと、現在のウインドウの状態がでてくるのでコマンドラインの箇所で”--remote-debugging-port=9222"があるか確認

1. Chromeにおいて、デバッグしたい画面を表示

1. VSCodeを起動

    デバッグ虫アイコンを押して
    デバッグの中のプルダウンメニューで、あらかじめ設定している

    （C:\Users\a_kaneko\Documents\vscode\.vscode\launch.json)

    Attach to Chromeを選択し、再生ボタンを押す

1. ブレークポイントは、ALL Exceptionsを選んでみる

    ※ローカルファイルの検証であればJSを開き、ブレークポイントを追加する

     (C:\Users\a_kaneko\Documents\vscode\index.html  であれば、./js/test.js にブレークポイントを設定

1. くるっとした矢印の形の再起動ボタンを押す

1. デバッグが開始される

1. ステップインボタンまたはステップオーバーボタンでステップ実行を行う

**別のページをデバッグするときの切り替え方法**

デバッグ中であれば、赤い切断ボタンで切断

右ウインドウにおいてデバッグ対象のファイルが表示されていたらウインドウをすべて閉じる

別のデバッグ対象ページをChromeで開き

VSCodeでデバッグ再生ボタン

リロードボタン


**参考サイト**

https://ics.media/entry/11356
https://kledgeb.blogspot.jp/2016/03/visual-studio-code-3-google.html
http://qiita.com/Sanshiro/items/084fb0971942e03db9a4#%E6%8B%A1%E5%BC%B5%E6%A9%9F%E8%83%BDdebugger-for-chrome%E3%81%AE%E5%B0%8E%E5%85%A5
