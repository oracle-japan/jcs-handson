# Oracle Java Cloud Service ハンズオン
Java Cloud Service の環境構築と利用方法に関するハンズオン

## 概要

Java Cloud Service 環境の構築方法と、デプロイメントやバックアップといった運用方法に関して基本的な操作を紹介しているハンズオンです。

なお、Java Cloud Service インスタンスの作成には、Database Cloud Service インスタンスが必要となります。そこで、最初の手順に Database Cloud Service インスタンスの作成方法を紹介しています。

## 前提

### 使用している製品バージョン

|製品|バージョン|
|----|---------|
|WebLogic Server|12c Release 1(12.1.3)|
|Oracle Database|12c Release 1|

## ハンズオン内容

### WebLogic Server 12cR1 (12.1.3) 環境作成

#### Database Cloud Service インスタンス作成

- [Oracle Database 12cR1 環境の作成](documents/create-dbcs-12cr1/README.md)

#### Java Cloud Service インスタンス作成

- [WebLogic Server 12cR1 環境の作成](documents/create-jcs-12cr1/README.md)

#### アプリケーションが使用するデータベース・スキーマ及びデータの作成

- [データベース・スキーマの作成](documents/create-db-schema/README.md)

#### Java Cloud Service へのアプリケーションデプロイ

- [データ・ソースの定義とアプリケーションのデプロイ](documents/deploy-application/README.md)

#### Java Cloud Service のバックアップとリストア

- [バックアップとリストア](documents/backup-and-restore/README.md)
