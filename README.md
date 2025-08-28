# polaris-hands-on
Polaris Hands-onセミナーで使用する演習用ソースコードなど

## フォルダの説明

### app1-flask

Polaris の SAST/SCA/DAST の解析対象のサンプルです。

### app2-forSCA

Polaris の SCA（シグネチャースキャン）を試すサンプルです。

### app3-c

Polaris の SAST で ビルドが必要なスキャンを行うサンプルです。

### ex4

PolarisのASPM機能を使用するときに使用するファイルです。

* webgoat-2025.3.jar-vulnerabilities.csv : Black Duck Binary Analysis(Standalone版) から出力したSCA結果です
* cppcheck_isssus.xml : CppCheck から出力した SAST結果です。

## DAST 解析対象の構築

### 必要なもの

* Python3
* pipenv

### インストール方法

依存関係のインストール

```bash
cd app1-flask
pipenv shell
pipenv install
```

DBの初期設定
```bash
python -c "from app import init_db; init_db()"
```
データの保存先として、app.db が作成されます。

### 起動方法

```bash
python server.py
```

http://localhost:5000 でアクセスして、ログインページが表示されたら起動完了です。
「ユーザー登録」から任意のユーザーを登録してください。ユーザー情報は、app.db に保存されます。
