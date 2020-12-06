---
Keywords: webサーバ, apache, 初期設定
Copyright: (C) 2020 Masayuki Onishi
---

# Web サーバ初期設定 ( Ubuntu × Apache )


## インストール

```bash
$ sudo apt install apache2
```

## セキュリティ対策

### エラーにサーバ情報を隠蔽

エラー画面において、デフォルトでは、フッターに Apache の情報が表示される。

そのため、最低限の対策として、当該情報を隠蔽する。


```bash
$ sudo vim /etc/apache2/apache2.conf
```

Apache の設定ファイルの下部に以下の設定を追加する。

```diff
...
+ ServerSignature Off
+ ServerTokens ProductOnly
```

```bash
$ sudo service  apache2 restart
```

- 参考 URL
    - [たった2行でできるWebサーバ防御の「心理戦」 \(2/3\)：セキュリティ対策の「ある視点」（1） \- ＠IT](https://www.atmarkit.co.jp/ait/articles/0707/19/news141_2.html)
