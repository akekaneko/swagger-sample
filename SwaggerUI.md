# Swagger UIの使用について

## Swagger UIの使用一覧
1. Swagger UIの起動
2. APIファイルを読み込む
3. 用語について
4. APIの実行

## **1. Swagger UIの起動**
Swagger UIはサーバサイドで動くスクリプトのため、WebServerを起動する。
WebServerを起動した後、ブラウザからSwagger UIを起動する。

## **2. APIファイルを読み込む**
初期状態では、Swagger PetstoreのSwagger SpecをベースにしたAPIが表示されています。
別のAPIを指定する場合は赤枠部分に別のファイルを指定し、Exploreボタンをクリックすることで切り替え可能です。
![image](https://github.com/akekaneko/swagger-sample/blob/master/SwaggerImages/swagger_ui_1.png)

用意されているメソッドは、データベースの世界で言うところのCRUD(Create/Read/Update/Delete)に相当し、 
例えばGETはRead、PUTはUpdateといった形です。また/pet/{petId}といった形でRESTのパス(URL)を示しており、 
{perId}は変数に相当します。 今回は、[/pet/findByStatus]をクリックし、APIの仕様を表示します。 

メソッド一覧

|CRUD|メソッド名  |
|---|---|
|Cretate|POST|
|Read|GET|
|Update|PUT|
|Delete|DELETE|

![image](https://github.com/akekaneko/swagger-sample/blob/master/SwaggerImages/swagger_ui_2.png)




## **3. 用語について**
以下の通り、APIの説明(Implementation Notes)や、モデルのサンプル値(ModelのExample Value)など、APIの仕様を確認できます。
[Parameters]-[Parameter]-[status]-[available]を選択した上で、[Try it out!]をクリックし、APIを実行します。






## **4. APIの実行**
以下の通り、APIの説明(Implementation Notes)や、モデルのサンプル値(ModelのExample Value)など、APIの仕様を確認できます。
[Parameters]-[Parameter]-[status]-[available]を選択した上で、[Try it out!]をクリックし、APIを実行します。


![image](https://github.com/akekaneko/swagger-sample/blob/master/SwaggerImages/swagger_ui_3.png)


「Try it out」ボタンをクリックする
![image](https://github.com/akekaneko/swagger-sample/blob/master/SwaggerImages/swagger_ui_4.png)

「Try it out」ボタンをクリックするとこのような画面が表示される。

URLパラメータを入力する
赤色で「*required」となっているので必須入力項目です。入力せずにExecuteボタンをクリックするとエラーになります。また、数値入力なので文字列を入力するとエラーになります。

「Execute」ボタンをクリックする

![image](https://github.com/akekaneko/swagger-sample/blob/master/SwaggerImages/swagger_ui_5.png)

Curl表示されます。

![image](https://github.com/akekaneko/swagger-sample/blob/master/SwaggerImages/swagger_ui_6.png)
