# GitHub ブランチ名かぶり

Aさんが新規ブランチを作りGitHubへPUSH後、Bさんが同名の新規ブランチを作りGitHubへPUSHすると、エラーがでてしまいPUSHできない。でもPUSHしなければならない場合の対処方法（AさんのファイルとBさんのファイルをマージしてから、BさんはPUSHする）

1. Bさん、ローカルのブランチを確認

    新規ブランチがチェックアウト中であることを確認します。

    ```
    $ git branch

    * issue-20
      master
    ```

1. git fetch を実行

    リモートリポジトリの内容をローカルリポジトリに取り込むために git fetch を実行します。
    ```
    $ git fetch
    ```
    ※pullしてしまうと、fetch & mergeになるので、fetchだけ行う。  
    ※SourceTreeでは、Fetchボタン

1. mergeを実行

   git fetchだけでは情報を取り込んだだけで、ファイルはマージされません。ファイルをマージするには merge コマンドを実行します。

    ```
    $ git merge origin/issue-20
    ```

    Aさんが修正しているので競合が発生し自動マージはできませんでした。

    ※SourceTreeでは、Aさんの修正のコミット箇所で  
    右クリック＞マージ＞競合発生

1. エディタで競合個所を修正

    競合が発生しているファイル(a.txt)をエディタで開き、競合個所を修正します。

    Aさんの修正を反映し、かつBさんの修正も反映して、修正を完了します。

1. 修正をコミットし、issue-20ブランチをPUSH

    エラーを発生することなく無事、新規ブランチをPUSHできました。


**参考**

http://tomoyamkung.net/2014/03/14/git-checkout-branch-from-remote/#2
