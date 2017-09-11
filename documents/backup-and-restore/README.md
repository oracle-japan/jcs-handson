# Java Cloud Service のバックアップの作成とリストア

## 1. Java Cloud Service インスタンス概要画面の表示

![jcs-overview](images/jcs-overview.png)

Java Cloud Service サービス・コンソール画面からインスタンス概要画面を開きます。

標準では「概要」タブが選択されているので、その下の「管理」タブを選択します。

<div style="page-break-before:always"></div> 

## 2. 手動バックアップの実施

![click-backup-now](images/click-backup-now.png)

画面中央に表示されている **「今すぐバックアップ」** をクリックし、バックアップ情報入力のダイアログボックスを開きます。

![click-backup](images/click-backup.png)

以下の選択肢を選択します。

|項目名|選択肢|
|-----|------|
|データベースを含める|いいえ|
|永久に保持|いいえ|

「永久に保持」を「いいえ」にすると、保存期間（デフォルト：30日）が過ぎると、バックアップを削除します。

![backup](images/backup.png)

バックアップを取得しています。暫く（１０分程度）待ちます。

<div style="page-break-before:always"></div> 

## 3. リストア実施確認のための構成変更

バックアップ・データからリカバリを実施する際の確認のために構成情報に変更をいれます。

アプリケーションのデプロイメント手順確認の中でデプロイを行った **HR** アプリケーションを削除します。

![stop-app](images/stop-app.png)

「デプロイメント」を選択し、表示されるアプリケーション一覧の中から「HR」アプリケーションを選び、横にあるチェックボックスを選択済みとします。

そして、「停止」ボタンをクリックし、「ただちに強制停止」を選択します。

![stop-app-confirmation](images/stop-app-confirmation.png)

「はい」を選択します。

![delete-app](images/delete-app.png)

「ロックして編集」をクリックします。次に、「HR」を再度選択済みとして、「削除」ボタンをクリックします。

![delete-app-confirmation](images/delete-app-confirmation.png)

「はい」を選択します。

![delete-activation](images/delete-activation.png)

「変更のアクティブ化」をクリックします。

![](images/404.png)

下記のURLでアプリケーションの動作確認を改めて実施します。

`https://<パブリック IP>/HR-ViewController-context-root/faces/hr.xhtml`

すると、404エラーが表示されてアプリケーションがなくなっている事が確認できます。

<div style="page-break-before:always"></div> 

## 4. リストアの実施

![restore](images/restore.png)

手動で作成したバックアップ・データの右側にある
メニューをクリックし、「リストア」を選択します。

![restore-confirmation](images/restore-confirmation.png)

表示されるダイアログ・ボックスで「リストア」をクリックします。

![restore-execution](images/restore-execution.png)

リストア実施の確認で「はい」を選択します。

## 5. リストアの確認

![hr-app](images/hr-app.png)

下記のURLでアプリケーションの動作確認を改めて実施します。

`https://<パブリック IP>/HR-ViewController-context-root/faces/hr.xhtml`

すると、HRアプリケーションが復旧し稼働している事が確認できます。