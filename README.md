# Stochastic Analysis and Statistics 2026-II

2026年11月4日（水），東京大学大学院数理科学研究科（駒場キャンパス）122号室．

[2026年4月の研究集会サイト](https://kkamatani.github.io/2026-stochastic-analysis-statistics/)を基にした，英語の Jekyll + Bootstrap 5 サイトです．メイン写真には指定された `IMG_4545.jpeg` をそのままコピーして使用しています．写真に合わせ，ボタン・リンク・見出し・背景・フッター・ファビコンを深緑とオリーブグリーンの配色で統一しています．上部ナビゲーションは不透明度60%の半透明です．

仮プログラムは13:00–16:50で，Arnaud Gloter氏（Université Évry Paris-Saclay）の特別講演40分，若手講演6枠各25分（いずれも質疑込み），休憩2回各15分，開閉会各5分としています．開始時刻と若手枠数は仮置きです．若手講演枠には，吉田淳一郎，矢野翔太，塩谷天章，Boyuan Ning，冨田明希，仲北祥悟の順で氏名・所属を仮配置しています．演題・要旨・参加方法は後日掲載します．前回の講演者とプログラムは転記していません．支援表記は前回と同じ JST CREST（JPMJCR2115，研究代表者：吉田朋広）を引き継いでいます．

Arnaud Gloter氏の所属は[LaMMEの本人ページ](https://www.math-evry.cnrs.fr/members/agloter/welcome)で確認し，大学名は[大学公式サイト](https://www.univ-evry.fr/accueil.html)の現行表記に合わせています（2026年10月7日確認）．

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
- `_data/organisers.yml`：世話人の氏名，所属，公式ページへのリンク（表示順）．所属は2026年10月7日に確認し，大学・研究所名で表記しています．
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
