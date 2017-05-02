# クローンでフォルダのないパスを指定した場合

SourceTreeでリポジトリをクローンする際、あらかじめフォルダを用意していなかった場合、新規作成されるか否かを検証する

1. リポジトリの作成

    新規リポジトリをGitHubに作成

    https://github.com/akekaneko/testsample.git

1. SourceTreeでクローンする画面を表示

    SourceTreeで、

    ファイル＞新規／クローンを作成する

    元のパス・URLに

    https://github.com/akekaneko/testsample.git

    を入力し、タブキーを押すと以下の状態となる。

    ![画像1](https://github.com/akekaneko/swagger-sample/blob/master/images/SourceTreeClone_01.png "画像")

1. クローンボタンを押すと、以下のフォルダが新規作成される。

    C:\Users\a_kaneko\Documents\testsample


**別フォルダ指定の場合は?**

SourceTreeでクローンする際、デフォルトフォルダではなく、別のフォルダを指定する場合は、最終的に作りたいフォルダ名を入力する必要があるが、フォルダは新規作成される。

![画像2](https://github.com/akekaneko/swagger-sample/blob/master/images/SourceTreeClone_02.png "画像")

クローンボタンを押すと、以下のフォルダが新規作成される。

C:\xampp\htdocs\swagger\testsample

## 検証結果

新規作成される
