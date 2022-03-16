# sweetlemon

## 準備

### 概要
Macに標準でインストールされているターミナルというアプリを起動してコマンドを打っていく

### Homebrew

```
brew --help
```
Example usage:とかでてくればインストール済みなのでアップデートしておく
```
brew upgrade
```
アップデートが終わったら次に進む

command not foundとでてきたら下のコマンドをターミナルに貼り付けて実行
```
softwareupdate --install-rosetta && xcode-select --install && /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

### docker
```
brew install docker
```

### git
```
git clone https://github.com/rysh/sweetlemon.git
```

## 始め方

### dockerからwordpressとmysqlを起動する
```
cd sweetlemon
docker-compose up -d
```

### wordpressにアクセスして始める
ブラウザのURLに```http://localhost:8000/```を打ち込む

設定途中で入力を求められる情報はdocker-compose.ymlの下記に対応してるので適当なものを入れる。
```
MYSQL_ROOT_PASSWORD: somewordpress
MYSQL_DATABASE: wordpress
MYSQL_USER: wordpress
MYSQL_PASSWORD: wordpress
WORDPRESS_DB_HOST: db:3306
WORDPRESS_DB_USER: wordpress
WORDPRESS_DB_PASSWORD: wordpress
```

参考資料
https://docs.docker.jp/compose/wordpress.html