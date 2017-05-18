# Issue作成、コミット、プルリク、リリース、ChangeLog作成までの流れを試す

## Issueを作成する

https://github.com/akekaneko/swagger-sample/issues/67

以下を項目としてあげた

- 概要(why/what)
- 解決方法(How)
- 開発担当
- 承認担当
- 終了条件

- Label : help wanted
- Assignees : 開発者を追加


### 気づいたこと
- 解決方法にタスク一覧でチェックボックスを設けたが、何度か作成、修正などを繰り返すとチェック状況の信頼性を失うので不要かも

### GitHubのDefault Labelについて

|labels|意味|
|-|-|
|enhancement|機能追加。実装したらクローズ。|
|bug|バグ。修正したらクローズ。|
|duplicate|他のイシューと重複している。重複先のイシューにリンクしてクローズ。|
|help wanted|	助けが必要。解決したらクローズ。|
|invalid|	間違い、勘違い、実現不可能。対応しない理由を書いてクローズ。|
|question|質問、議論。収束したらクローズ。|
|wontfix|分かっちゃいるけど対応しないバグ。対応しない理由を書いてクローズ。|

## コミット & PUSH

### 気づいたこと
- コミット文のIssue番号は先頭にするべきか、末尾にするべきか
- コミット文に日本語はOKにするか、しないか

## プルリクエスト


### 書き方（GitHubのガイドライン）
- Pull Requestの目的を含める。
- なぜこの作業が必要なのか(適切なリンクとともに)概要を提供する。経緯に精通していると想定しないように。
- 会社内の誰もがPull Requestを読めることを忘れない。
- どんなフィードバックが欲しいかを明確にする。
- いつフィードバックが欲しいかを明確にする。タイトルの接頭辞「[WIP]」は、その状態を示す簡単な共通パターンです。
- @mention個人は、議論に参加してほしい人とその理由を明示する。
- @mentionチームは、議論に参加してほしいチームとその理由を明示する。

### 気づいたこと
- 承認者を必ずAssigneesに追加する
  - あとから追加してもメール通知が届く
  - これがないと通知が来ないので、プルリク・マージされても気づけない
- ラベルは取り急ぎIssueと同じものを設定
- マージ後にプルリクタイトルを変更できてしまうが、マージ直前に確定するべき（WIPを削除する、等）
  - タイトルを変更してしまうと、issue側だけみると、マージしたはずのプルリクがみつからなくてあせる
- タスク一覧のチェック項目は、作成、編集、削除という流れがあるためいチェック状況の正確性が曖昧となり無意味に思えてきた。チェックボックスは終了条件の箇所だけでよいかも。
- プルリクを[WIP]をつけたままcloseするのは避けたい
- マージ前にプルリクがcloseされマスターが更新されるトラブル発生。
  - 原因はなんだったか？
    - SourceTreeでmasterをPUSHした？
    - クローズされたプルリク側にリバートボタンはなかったのでリバートで戻せない
- ブランチはリモートで作りクローンして作業するほうが事故がないかも
  (途中でリモートブランチが削除されあらたにローカルで作成してから事故が発生)
- File Changedの箇所にReview Changesというものがあり、Files changedのレビューコメントを追加できる。目のマークのついたコメントになる。

## マージ

### 気づいたこと
- Issueの中で、先行ファイルアップのみのマージが必要な場合があり、プルリクを分けなければいけない場合がある。その場合はマージ後、ブランチの削除を行わないこと
- 基本はイシューに対して１つのプルリクだが例外も発生する
- 間違ってマージしたら、すぐリバートし元に戻す
- masterブランチだけは管理者の設定でプロテクトをかけておくとマージ事故が防げる
- 開発側で緊急マージが必要な場合は承認者へ連絡後に行うこと（Assigenees追加＆コメントなど）

## リリース
今回作成分のChangeLogをとるために、
更新以前の状態に v0.0.1 (PreRelease)とタグ付けしておき、
今回の更新分は v0.0.2 (PreRelease)とした。

- リリースのタグ付けの編集画面の本文欄を空にすると、マージ時のコメントが表示されるので、慎重にコメントを残さないと恥ずかしい。（これは後から修正できない）

```
Merge pull request #74 from akekaneko/issue-67

Update Index #67

マージ完了！
```

## ChangeLog作成

- v0.0.2のタグをつけv0.0.1とのバージョン単位の差分の[ChangeLog](https://github.com/akekaneko/swagger-sample/releases/tag/v0.0.2)を作成してみた。
- 各ファイルのChangeLogに関しては[Full Change Log](https://github.com/akekaneko/swagger-sample/compare/v0.0.1...v0.0.2)の中で確認することができる。
- 誰が、いつ、何を変更したか、変更理由が明確になるように
- GitHub内ではシャープ＋番号にすると意図しない場所も自動リンクしてしまう。
- コミット文やプルリクのタイトルにつけているイシュー番号は、先頭もしくは以下のようにフォーマットを定めるとログがきれいになる。

```
Fixed issue #442 - broken issue-line-labels in log. #443
```

- ファイルの変更については以下の分類がある
  - Added: 新機能。
  - Changed: 既存機能の変更。
  - Deprecated: 今後のリリースで削除されるもの。
  - Removed: 今回のリリースで削除されたDeprecatedな機能。
  - Fixed: バグの修正。
  - Security: 脆弱性に関するもの。

今回作成したChangeLog

---

## [v0.0.2](https://github.com/akekaneko/swagger-sample/tree/v0.0.2) (2017-05-12)
[Full Changelog](https://github.com/akekaneko/swagger-sample/compare/v0.0.1...v0.0.2)

**Added:**
- GitHubIssueHowToMake.md
- GitHubRemoteBranchClone.md

**Changed:**
- index.md - Add new links to the index.

**Closed issues:**
-  5/8 新規課題についてindex更新とマークダウン新規作成 [\#67](https://github.com/akekaneko/swagger-sample/issues/67)

**Merged pull requests:**
- Update Index \#67 [\#74](https://github.com/akekaneko/swagger-sample/pull/74) ([akekaneko](https://github.com/akekaneko))
- Issue-67「リンク先のマークダウンファイルを新規作成」項目のファイルアップロード \#67 [\#72](https://github.com/akekaneko/swagger-sample/pull/72) ([akekaneko](https://github.com/akekaneko))

---


<!--
### メモ

- Version間のファイルの差分は以下のようにすれば確認できる
  - https://github.com/akekaneko/swagger-sample/compare/v0.0.2...HEAD
  - https://github.com/akekaneko/swagger-sample/compare/v0.0.1...v0.0.2


### サンプル

```
2005-10-11  Juanma Barranquero  <lekktu@gmail.com>

	* emacs-lisp/autoload.el (update-directory-autoloads): Doc fix.
	(autoload-print-form-outbuf): Add docstring.

2005-10-11  Juri Linkov  <juri@jurta.org>

	* info.el (Info-mode-menu): Delete menu item "Edit".
	(Info-mode): Delete description of Info-edit from docstring,
	and rearrange descriptions of Info commands in the order
	they are documented in the Info manual.

2005-10-11  Stefan Monnier  <monnier@iro.umontreal.ca>

	* calendar/appt.el (appt-check): Use diary-selective-display var.
2005-10-10  Richard M. Stallman  <rms@gnu.org>

	* net/newsticker.el (newsticker-start, newsticker-show-news):
	Add autoload cookies.
```

GitHub ChangeLog Sample

```
## [v1.0.2](https://github.com/akekaneko/swagger-test/tree/v1.0.2) (2017-05-09)
[Full Changelog](https://github.com/akekaneko/swagger-test/compare/v1.0.1...v1.0.2)

**Fixed bugs:**
- Fix version 1.0.2 [\#40](https://github.com/akekaneko/swagger-test/pull/40)
- Fix background & text color [\#38](https://github.com/akekaneko/swagger-test/pull/38)

**Closed issues:**
-  Fix version 1.0.2 [\#39](https://github.com/akekaneko/swagger-test/issues/39)
-  Fix background & text color [\#37](https://github.com/akekaneko/swagger-test/issues/37)
```

その他サンプル
```
## [0.0.2] - 2014-07-10
### Added
- Explanation of the recommended reverse chronological release ordering.

## 0.0.1 - 2014-05-31
### Added
- This CHANGELOG file to hopefully serve as an evolving example of a standardized open source project CHANGELOG.
- CNAME file to enable GitHub Pages custom domain
- README now contains answers to common questions about CHANGELOGs
- Good examples and basic guidelines, including proper date formatting.
- Counter-examples: "What makes unicorns cry?"

[Unreleased]: https://github.com/akekaneko/swagger-test/compare/v0.0.2...HEAD
[0.0.2]: https://github.com/akekaneko/swagger-test/compare/v0.0.1...v0.0.2
```
-->


### 参考
- http://keepachangelog.com/en/0.3.0/
- http://www.softantenna.com/wp/software/keep-a-changeloag/
- http://blog.yux3.net/entry/2017/05/04/035811
- [github-changelog-generator ChangeLog](https://github.com/skywinder/Github-Changelog-Generator/edit/master/CHANGELOG.md)
- [ATOM releases](https://atom.io/releases)
- https://www.gnu.org/prep/standards/html_node/Change-Logs.html#index-change-logs

- [GitHubフロー（和訳）](https://gist.github.com/Gab-km/3705015)
