---
# Configurations
# black, white, league, beige, sky, simple, serif, night, moon, solarized
theme: league
# cube, page, concave, zoom, linear, fade, none, default
transition: slide
#  Syntax highlighting style https://highlightjs.org/static/demo/
highlight: solarized-dark
backgroundTransition: zoom
progress: true
controls: true
hideAddressBar: true

# Editor settings
editor:
    fontSize: 14
    theme: solarized_light
    # keybinding: vim
---
# 基盤汎用検索
## 勉強会１
### 【クレカ連携機能概要】

2021/06/17

@chuang.li
---
<!-- .slide: data-auto-animate -->
## 目 次

1. 汎用検索は何
1. 汎用検索仕組み
1. クレカ連携機能説明
---
<!-- .slide: data-auto-animate -->
## 目 次

1. <div data-id="box" style="height: 50px; background: grey;">汎用検索は何</div>
1. 汎用検索仕組み
1. クレカ連携機能説明
---
<!-- .slide: data-auto-animate -->
## 汎用検索は何
> ❝マーケティング担当者・分析者が自動化していない施策のターゲティングリストを簡便に作成するため、また対象となる顧客数の確認に使用する。❞

ーー「汎用検索概要説明_v1.16」

🥴 <!-- .element: class="fragment " data-fragment-index="1" -->

Note:
参照資料の紹介
---
<!-- .slide: data-auto-animate -->
## 汎用検索は何
> ❝マーケティング担当者・分析者が**自動化していない施策**のターゲティングリストを簡便に作成するため、また**対象となる顧客数の確認**に使用する。❞

ーー「汎用検索概要説明_v1.16」

🤔

Note:
参照資料の紹介
---
<!-- .slide: data-auto-animate -->

### 施策の属性
<div class="r-hstack justify-center">
<div data-id="box1" style="background: #999; width: 250px; height: 50px; margin: 10px; border-radius: 5px;" data-auto-animate-target="">レギュラー</div>
<div data-id="box2" style="background: #999; width: 250px; height: 50px; margin: 10px; border-radius: 5px;" data-auto-animate-target="">非レギュラー</div>
</div>

Note:
定期、長期的な施策
要件が明確な施策

突発的な施策
短期的な施策
PoC実験的な施策
---
<!-- .slide: data-auto-animate -->
### ターゲットの属性
<div class="r-hstack justify-center">
<div data-id="box1" data-auto-animate-delay="0" style="background: orange; width: 150px; height: 150px; border-radius: 150px;" data-auto-animate-target="51">定期<br>定量<br>定常</div>
<div data-id="box2" data-auto-animate-delay="0.1" style="background: red; width: 150px; height: 150px; border-radius: 150px;" data-auto-animate-target="52">非明確<br>自由</div>
</div>

Note:
決まってる施策を決まってるデータテーブルを分析し、決まってるルートで決まってる対象者に配信する。（新規ユーザwelcome）
施策自由、データマート上あるデータ、SMC以外他システム、用途が広い。
---
<!-- .slide: data-auto-animate -->
### 対象者リストの連携方式
<div class="r-stack">
<div data-id="box1" style="background: green; width: 300px; height: 300px; border-radius: 200px; font-size:30px;" data-auto-animate-target="55"><h5><br>ターゲット</h5></div>
<div data-id="box2" style="background: red; width: 150px; height: 150px; border-radius: 150px; position: absolute; top: 40%; left: 50%; font-size:30px;" data-auto-animate-target="56"><br>汎用検索<br>手動</div>
<div data-id="box3" style="background: orange; width: 150px; height: 150px; border-radius: 150px; position: absolute; top: 40%; right: 50%; font-size:30px;" data-auto-animate-target="57"><br>SMC/BP<br>自動</div>
</div>

😀 <!-- .element: class="fragment " data-fragment-index="1" -->
---
<!-- .slide: data-auto-animate -->
## 目 次

1. 汎用検索は何
1. <div data-id="box" style="height: 50px; background: grey;">汎用検索仕組み</div>
1. クレカ連携機能説明
---
<!-- .slide: data-auto-animate -->
## アーキテクチャ

![snip_20210617_025828.png](https://qiita-image-store.s3.ap-northeast-1.amazonaws.com/0/89709/6f2441ec-3d49-dde1-3557-210190425343.png)

---
<!-- .slide: data-auto-animate -->
## アプリ配置概要

<img src="https://qiita-image-store.s3.ap-northeast-1.amazonaws.com/0/89709/ab260e15-979f-f255-b74e-da874cb74775.png" width="60%">

---
<!-- .slide: data-auto-animate -->
## アプリ配置概要

<img src="https://qiita-image-store.s3.ap-northeast-1.amazonaws.com/0/89709/6834bfbe-8a81-02fa-d558-5213a1ea3000.png" width="60%">

---
<!-- .slide: data-auto-animate -->
## アプリ配置概要
#### アプリ選択画面
![image.png](https://qiita-image-store.s3.ap-northeast-1.amazonaws.com/0/89709/b1d10b92-357a-89ae-0e3b-be75c57592cd.png)
---
<!-- .slide: data-auto-animate -->
### 連携ファイルフォーマット

|  | 全項目/ID | SEJ/IY/FS |
| ------ |:------:| :-----:|
| 拡張子 | TXT | CSV |
| 圧　縮 | ZIP | ZIP |
| 改　行 | LF | LF |
| 区切り | なし | なし |
| 文　字 | UTF-8 | UTF-8 |

 (7CEを除く)
---
<style>
.smalltable > table, .smalltable > th, .smalltable > td {
    font-size: 75%;
}
</style>
<!-- .slide: data-auto-animate -->
### 連携ファイルフォーマット

<div class="smalltable">

| &nbsp; &nbsp;&nbsp; &nbsp;| 全項目/ID | SEJ/IY/FS |
| ----- |:------:| :-----:|
| ヘッダー&nbsp;&nbsp;&nbsp;| なし | なし|
| 暗号化 | なし | なし |
| カラム数 | 1 | 1 |
| ファイル名&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;| IFID-datetime.zip | IFID_会社コード_コンテンツ種別_施策ID_バージョン.zip |

</div>

Note:
7CEちょっと特殊なので、次回で紹介させていただきます。
---
## テストデータ作成 Tips

- Redshift SQL Script
  大量データ作成方法.txt
- CSVファイル作成
  testdata2csv.py
```py
# 200M Size
$ python testdata2csv.py 815000
write 815000 test items done!
  ```
---
<!-- .slide: data-transition="zoom-in zoom-out" -->
## パフォーマンス

> upload + copy time ≈ insert time

| records | Insert | S3 Copy  |
| -------- |:------:| -----:|
| 1k | 0.3s | 0.65s |
| 10k | 1.90s |  1.99s |
| 100k | 9.10s | 9.20s |

*参照：[stackoverflow](https://stackoverflow.com/questions/25454477/amazon-redshift-bulk-insert-vs-copying-from-s3?rq=1)
---
## デバッグ Tips

- 環境変数を確認する
- デバッグモードオン
```py
# main/settings.py
DEBUG = True
```
- ログを確認する
- アプリ起動コマンド
```sh
$ python manage.py runserver 0:8080
```

Note:
 0は0.0.0.0 のショートカットです。
 8080はポートナンバー
 Pythonコード変更してもリクエスト時コードを自動的にリロードします、サーバーを再起動する必要はありません。
---
### コンフィグレーション

```sh
$ sudo vim /etc/secret/general_search.yml
```
```yml
mysql:
    host: sevenandi-stgdb02.cvhb3esx6t5b.ap-northeast-1.rds.amazonaws.com
    user: general_search
    password: P@ssw0rd
    database: general_search
    port: 3306

log:
    log_path: \7iGeneralSearch\log\django.log

passwordreset:
    file_path: C:\Users\Public\Documents\pwdreset

redshift:
    host: redshift-stg01.cpmundnkeusy.ap-northeast-1.redshift.amazonaws.com
    port: 5439
    db_name: prd_database
    user: screenuser
    password: Redsh1ft_screenuser
    devgroup:
        user: screenuser
        password: Redsh1ft_screenuser
    anlgroup:
        user: screenuser
        password: Redsh1ft_screenuser
    sejgroup:
        user: screensej
        password: Redsh1ft_screesej
    iygroup:
        user: screeniy
        password: Redsh1ft_screeniy
    seven_fsgroup:
        user: screenseven_fs
        password: Redsh1ft_screenseven_fs
    seven_cegroup:
        user: screenseven_ce
        password: Redsh1ft_screenseven_ce

sej_redshift:
    host: redshift-stg02.cpmundnkeusy.ap-northeast-1.redshift.amazonaws.com
    port: 5439
    db_name: prd_database
    user: screenuser
    password: Redsh1ft_screenuser
    devgroup:
        user: screendev
        password: Redsh1ft_screendev
    anlgroup:
        user: screenanl
        password: Redsh1ft_screenanl
    sejgroup:
        user: screensej
        password: Redsh1ft_screensej
    iygroup:
        user: screeniy
        password: Redsh1ft_screeniy
    seven_fsgroup:
        user: screenseven_fs
        password: Redsh1ft_screenseven_fs

aws:
    key: AKIAIZBOLZXFWQXZXVEA
    secret: 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
    kms: cd6e10e5-d353-4db5-b78c-0eff1e1ea087
    bucket: analytics-7andi-common-dev-test
    iy_bucket: analytics-7andi-common-dev-test
    sej_bucket: analytics-7andi-common-dev-test
    aws_account_id: 898505340510
    role_name: role-analytics-dev-redshift-all

```
---
# End
### 2021/06/17
##### @chuang.li
