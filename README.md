# Stochastic Analysis and Statistics 2026-II

2026年11月4日（水），東京大学大学院数理科学研究科（駒場キャンパス）122号室．

[2026年4月の研究集会サイト](https://kkamatani.github.io/2026-stochastic-analysis-statistics/)を基にした，英語の Jekyll + Bootstrap 5 サイトです．メイン写真には指定された `IMG_4545.jpeg` をそのままコピーして使用しています．写真に合わせ，ボタン・リンク・見出し・背景・フッター・ファビコンを深緑とオリーブグリーンの配色で統一しています．上部ナビゲーションは不透明度60%の半透明です．

講演者・所属・演題・要旨・時間割・参加方法は未提供のため，後日掲載の案内を表示しています．前回の講演者とプログラムは転記していません．支援表記は前回と同じ JST CREST（JPMJCR2115，研究代表者：吉田朋広）を引き継いでいます．

## ローカルプレビュー

Ruby 3.2.9 を使用します．

```sh
bundle install
bundle exec jekyll serve --port 4001
```

http://127.0.0.1:4001/2026-stochastic-analysis-statistics-ii/ を開いてください．

```sh
bundle exec jekyll build
```

## 更新するファイル

- `_data/event.yml`：日付，会場，連絡先，支援表記．
- `_data/speakers.yml`：講演者名，所属，演題，講演要旨．
- `_data/programme.yml`：時刻，講演者ID，休憩などの項目．
- `index.md`：各セクションの案内文．
- `assets/css/site.css`：デザイン．
- `assets/img/hero.jpg`：メイン写真．

`speakers.yml` は `{}` を削除し，次の形式で講演順に追加してください（以下は入力形式の例です）．

```yaml
speaker_id:
  name: "Speaker name"
  affiliation: "University or institute"
  title: "Talk title"
  abstract: |
    Abstract text. Markdown is supported.
```

`programme.yml` は `[]` を削除し，次の形式で追加してください．`speaker` は `speakers.yml` のIDと一致させます．

```yaml
- time: "13:00–13:40"
  speaker: speaker_id
- time: "13:40–14:00"
  label: "Break"
```

## GitHubへの配置

フォルダー名・想定するリポジトリ名は `2026-stochastic-analysis-statistics-ii` です．GitHub上で `KKamatani` を所有者とする空のPublicリポジトリを作成してから，このフォルダーで以下を実行できます．README・.gitignore・LicenseはGitHub側では追加しません．

```sh
git init -b main
git add .
git status
git commit -m "Create Stochastic Analysis and Statistics 2026-II website"
git remote add origin git@github.com:KKamatani/2026-stochastic-analysis-statistics-ii.git
git push -u origin main
```

Settings → Pages で **Deploy from a branch → main → / (root) → Save** を指定してください．

想定する公開URL： https://kkamatani.github.io/2026-stochastic-analysis-statistics-ii/

`_config.yml` の `url` と `baseurl` は設定済みです．このフォルダーの準備のみでは，GitHubリポジトリの作成・push・Web公開は行われません．

会場情報の確認元：[東京大学大学院数理科学研究科のアクセス案内](https://www.ms.u-tokyo.ac.jp/access_e/index_e.html)．
