# GitHubフロー図(Issueの使用)

API仕様書の元ファイルとなるYAMLファイルをswaggerEditorで編集し、swagger UIで仕様書を出力する。
YAMLファイルはGitHubを介し、AさんとBさんと両方で編集することにし、以下作業フローをまとめた。

## フロー図

[GitHubフロー図(Issueの使用) PDF](https://github.com/akekaneko/swagger-sample/blob/master/GitHubFlow.pdf)

ローカルファイル (エクセル)   
\\server02\trainee\a_kaneko\GitHubフローissue版.xlsx


## 手順

管理者 (レビュアー) ：Aさん  
開発者：Bさん

### 1. マスターファイルの作成 (Aさん)

①GitHub：リモートリポジトリを作成

swagger-sample というリポジトリを作成。URLは以下となる。

https://GitHub.com/akekaneko/swagger-sample.git

②GitHub：メンバーの追加 (Bさん) 

対象リポジトリの画面で

Settings＞Collaborators

ここで追加したいメンバーの"ユーザID"を入力し、Add Collaborator ボタンを押す

追加メンバー側にメールが届き、許可のアクションをすることでメンバー追加完了。

これにて追加メンバーもリポジトリ更新が可能となる。

③SourceTree：クローン (ローカルリポジトリ作成) 

GitHubの以下のリポジトリをクローンする。

https://github.com/akekaneko/swagger-sample.git

メモ：

- ローカルにswagger-sampleという空フォルダを作成し、そこにクローンするフォルダ名は別名でもクローン可能。
- 途中でリポジトリ名変えられるか？＞変えられる。  
リモート側 (Settings>Repository Name)  
ローカル側 (SourceTreeの場合 Settings>リモートリポジトリのパス編集)

④masterブランチでswagger.yamlを新規作成

C:\xampp\htdocs\swagger\swagger-sample\swagger.yaml

フォルダ内のファイルは

http://localhost/swagger/swagger-sample

として閲覧できるようにする。

⑤SourceTree：masterブランチをPUSH

### 2. Swagger EditorでYAML修正 (Bさん)

①GitHub：issue追加

②SourceTree：クローン (ローカルリポジトリ作成) 

③SourceTree：新規ブランチ作成 (issue-[issue番号])

④SourceTree：新規ブランチでswagger.yamlを修正

1.  Swagger Editor でswagger.yamlを読み込み修正する
versionは1.0.1にする  
その他修正をする

1. Swagger EditorでYAMLをエキスポート

1. Swagger UIでYAMLを検証

1. 動作OKであれば新規ブランチのswagger.yamlを上書き更新

⑤SourceTree：コミット

⑥SourceTree：新規ブランチをPUSH

⑦GitHub：Pull Requestをする

⑧GitHub：メンバーで討論  (→④→⑤→⑥→⑧を繰り返す) 

⑨GitHub：新規ブランチをmasterブランチへマージ(Aさん)

⑩GitHub：issueクローズ

⑪GitHub：新規ブランチ削除

⑫SourceTree：masterブランチをPULL

⑬SourceTree：新規ブランチ削除

### 3. Swagger EditorでYAML修正 (Aさん)

①GitHub：issue追加

②SourceTree：masterブランチをPULLする

③SourceTree：新規ブランチ作成 (issue-[issue番号])

④SourceTree：新規ブランチでswagger.yamlを修正

versionは1.0.2にする  
その他修正をする

⑤SourceTree：コミット

⑥SourceTree：新規ブランチをPUSH

⑦GitHub：Pull Requestをする

⑧GitHub：メンバーで討論  (→④→⑤→⑥→⑧を繰り返す) 

⑨GitHub：新規ブランチをmasterブランチへマージ(自分)

⑩GitHub：issueクローズ

⑪GitHub：新規ブランチ削除

⑫SourceTree：masterブランチをPULL

⑬SourceTree：新規ブランチ削除
