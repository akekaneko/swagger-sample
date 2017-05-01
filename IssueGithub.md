課題のまとめ

# **課題一覧**
1. ブランチ名で使用できる文字
1. 権限について
1. GitHubメンバー参加拒否した場合
1. リポジトリのエンドポイントの命名規則
1. クローンでフォルダのないパスを指定した場合
1. ブランチ名かぶり
1. 間違ってマージをした場合
1. [GitHubフロー(Issueの使用)](https://github.com/akekaneko/swagger-sample/blob/master/GitHubFlow.md) GitHubフロー(Issueの使用)

## **1. ブランチ名で使用できる文字**
英数字、小文字、大文字  「-(ハイフン)  _ (アンダーバー) .(ピリオド)」のみ使用可能。

## **2.リポジトリのユーザー権限について**
作成したリポジトリのユーザーSettings内容は下記の通り。

|項目|機能|設定状況  |
|---|---|---|
|Features|Wikis|on|
|Features|Restrict editing to collaborators only|on|
|Features|Issues |on|
|Features|Projects|on|
|Merge button|Allow merge commits  |on|
|Merge button|Allow squash merging |on|
|Merge button|Allow rebase merging  |on|

リポジトリ機能のユーザー権限について

|機能|作成者|参加者 |
|---|---|---|
|clone/pull |〇|〇|
|push|〇|〇|
|リポジトリの作成|〇|×|
|リポジトリ名の変更|〇|×|
|リポジトリの削除|〇|×|

リポジトリページのタブ単位の機能のユーザー権限について

|タブ|機能|  |作成者|参加者|
|---|---|---|---|---|
|Code|Add topics|  |〇|×|
|Code|Edit topics|  |〇|×|
|Code|Description Edit|  |〇|×|
|Code|Create new branch|  |〇|〇|
|Code|Create new file|  |〇|〇|
|Code|Upload files|  |〇|〇|
|Code|Find file|  |〇|〇|
|Code|ファイルの編集|  |〇|〇|
|Code|ファイルの削除|  |〇|〇|
|Issues|New Issue|  |〇|〇|
|Issues|New Issue|イシューの修正|〇|〇|
|Issues|New Issue|イシューのクローズ|〇|〇|
|Issues|New Issue|コメント投稿|〇|〇|
|Issues|New Issue|コメント削除|〇|〇|
|Pull Requests|New Pull Request|  |〇|〇|
|Pull Requests|マージ|  |〇|〇|
|Pull Requests|ブランチの削除|  |〇|〇|
|Projects|New Project|  |〇|〇|
|Projects|New Project|Save Project|〇|〇|
|Projects|New Project|Delete Project|〇|〇|
|Projects|New Project|Add card|〇|〇|
|Projects|New Project|Add column|〇|〇|
|Projects|New Project|Edit column name|〇|〇|
|Projects|New Project|Delete Column|〇|〇|
|Projects|New Project|Add note|〇|〇|
|Projects|New Project|Delete note|〇|〇|
|Projects|New Project|プロジェクト編集ボタン(設定ボタンのようなマーク)|〇|〇|
|Projects|New Project|　　Edit project|〇|〇|
|Projects|New Project|　　Delete project|〇|〇|
|Projects|New Project|Project close|〇|〇|
|Wiki|New Page|  |〇|〇|
|Wiki|New Page|Edit|〇|〇|
|Wiki|New Page|　　Page History|〇|〇|
|Wiki|New Page|　　Delete Page|〇|〇|
|Wiki|New Page|Clone this wiki locally|〇|〇|
|Pulse|ページ表示|  |〇|〇|
|Graphs|Contributorsページ表示|  |〇|〇|
|Graphs|Trafficページ表示|  |〇|〇|
|Graphs|Commitsページ表示|  |〇|〇|
|Graphs|Code frequencyページ表示|  |〇|〇|
|Graphs|Punch cardページ表示|  |〇|〇|
|Graphs|Networkページ表示|  |〇|〇|
|Graphs|Membersページ表示|  |〇|〇|
|Graphs|Dependentsページ表示|  |〇|〇|
|Settings|ページ表示|  |〇|×|

## **3.GitHubメンバー参加拒否した場合**
　リポジトリから招待された場合は、拒否するボタンをクリックすると招待された側ではブラウザ上に表示するが、招待した側は何も表示しないためわからない。

## **7.間違ってマージをした場合**
間違ってマージをした場合の対処方法を記載する。
1. リモートリポジトリのコードタブで一覧から対象のタイトルリンクボタンをクリックする
2. 1.で表示された画面から、master(#番号)リンクボタンをクリックする。
3. 2.で表示された画面から、Revertボタンをクリックする。
4. 3.で表示された画面から、Create pull requestボタンをクリックする。
5. 4.で表示された画面から、Merge pull requestボタンをクリックする。
6. 5.で表示された画面から、Comfirm mergeボタンをクリックする。
7. 6.で表示された画面から、Delete branchボタンをクリックする。

