# ChangeLogから、変更履歴と変更理由を明確化するためには？

## ChangeLogとは

- ソフトウェアのソースコードの変更履歴を書くためのテキストの形式
- 自動作成ツールもあるが基本は手動で記述する
- GitHubでは、ルートに CHANGELOG.md というファイルでおく
- (↑Githubのリリースの箇所も同様の記述にする？！)
- 変更に関わるIssueやPullRequestへリンクする
- GitHub ChangeLogサンプル  
https://github.com/skywinder/Github-Changelog-Generator/edit/master/CHANGELOG.md
- ChangeLogにはファイル単位のChangeLogも存在する

## Issue作成方法

- タイトル：専門知識がなくても、わかりやすく、簡潔に
- 本文：課題種類ごとに内容を明確にすること
    - 課題提起：概要(why/what)、解決方法(How)、終了条件
    - バグ報告：概要(why/what)、実行環境、再現手順、期待される結果、解決方法(How)、終了条件
    - その他： タスク一覧、対象ファイル、親課題、関連課題、修正依頼担当、プルリク担当、備考、等

**問題の背景や理由(why)がIssue内に明確にあればChangeLogからたどった時に理解しやすい**

- タグをつける
    - 必要であればオリジナルタグを作成する。Bootstrapはよい例かもしれない  
[※Issueの参考例（Bootstrap)](https://github.com/twbs/bootstrap/issues)

**タグをつけることで、ChangeLogを書くときに問題の分類がしやすくなる？**

- 担当者への通知方法
  - Assigneesに追加する(10人まで) ※Issue作成者は登録不要
  - 本文にメンション(@ユーザ名)を追加するとユーザ宛にメールが送信される

- GitHubでは、ルートに ISSUE_TEMPLATE.md というファイルを置くとテンプレートとして読み込むことができる

## コミット

- 修正担当は、issue-[issue番号]という新ブランチを作成し開発をする。
- コミットの際は Fix bug #[issue番号] など、コミット文内にissue番号をつけておくとissueに紐づきコミット内容が表示される。

## Pull requests

- 進行中は頭に[WIP]をつける
- マージ後issueを自動クローズさせる場合は Close #[issue番号]をつける
- 修正完了となったら[WIP]をとる

## マージ＆リリース

- レビュワーはマージを行う
- リリースのバージョンタグをつける
- リリースしたバージョンに関する変更履歴(changelog形式)をまとめる（※）　　
https://github.com/akekaneko/swagger-test/releases  

- バージョンの変更履歴を全体のChangeLogにも追加？


- 不明点
  - 変更履歴作成について、手動の場合効率よく作成する方法がわからない
  - バージョンにまつわるissueは検索できない
  - バージョンをマージしたissueとプルリクを検索し、まとめるしかない？
  - fix bugとclose issueがだぶってしまう内容もあるがいいのか？

参考

-　http://dev.classmethod.jp/tool/git/github-issue-driven-dev/
-　http://qiita.com/awakia/items/c571e93e96a1ec28044f#%E6%A8%99%E6%BA%96%E7%9A%84%E3%81%AA%E3%83%95%E3%83%AD%E3%83%BC
