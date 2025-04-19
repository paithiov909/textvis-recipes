## 開発コンテナについて

このディレクトリのファイルは、手もとでKH Coderの図表を確認するために、開発コンテナ内でKH Coderを動かせるようにしていたものです。

具体的には、[Light-weight Desktop (desktop-lite)](https://github.com/devcontainers/features/tree/main/src/desktop-lite) というDev Container Featuresを使っていて、コンテナ内のデスクトップ環境（[Fluxbox](http://fluxbox.org/)）に[noVNC](https://novnc.com/)経由で接続できるようにしていました。

参考にできるように残しておきますが、いろいろ調整しないと動かせないと思います。また、これはIMEがない環境なので、日本語入力ができません。

---

### 使い方

1. サブモジュールをチェックアウトした後、ターミナルなどが表示されるパネルの「ポート」タブから「転送されたアドレス」（ローカルアドレス）を確認し、ブラウザで開きます
2. noVNCの画面が出るのでパスワードに`khcoder`と入力して接続します
3. 右クリックするとメニューが開くので、「Terminal」を起動します
4. `workspace/khcoder`に移動します（`cd workspace/khcoder`）
5. `perl kh_coder.pl`を実行します
6. VS Codeで`khcoder/config/coder.ini`の一部の行を次のように編集し、再度`perl kh_coder.pl`を実行します（コンテナをはじめて起動したときのみ）

```
mecab_unicode	1
last_method mecab
c_or_j  mecab
sql_username  root
sql_password  khcoder
sql_host  host=db
sql_port  3306
```

### 参考にしたリポジトリ

- [sinchiba-backyard/NL2E: Natural Language to Embedding with Docker featuring KH Coder](https://github.com/sinchiba-backyard/NL2E)
- [naoigcat/docker-khcoder: Docker Image for KH Coder on Ubuntu](https://github.com/naoigcat/docker-khcoder)
