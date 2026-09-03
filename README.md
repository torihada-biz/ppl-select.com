# ppl-select.com

GitHub Pages で配信している広告用ブランド紹介LPサイト（カスタムドメイン `ppl-select.com`、`CNAME` 設定済み）。
ディレクトリ単位で同フォーマットのLPを追加する運用。

## ページ一覧

| URL | ブランド | 遷移先（Qoo10 商品ID） | 用途 | 公開日 |
|---|---|---|---|---|
| https://ppl-select.com/ | KOPHER × Anua × medicube（Beauty Trio Select） | 各カードの Qoo10 リンク | 3ブランド版 | 2026-08-31 |
| https://ppl-select.com/cm-a/ | malun malun × Isntree | malun malun: 1072234942 ／ Isntree: 1046521530 | TikTok Spark Ads の CTA 遷移先 | 2026-09-02 |

## 計測

- 現在、どのページにも計測タグ（TikTok Pixel 等）は入っていない。
- 2026-09-03 に `/cm-a/` へ TikTok Pixel（ID: `DAC4ESJC77UCRCTV9K80`）を一度設置したが、同日中に撤去した。再設置する場合はコミット `4d9b81a` の実装（Pageview ＋ Qoo10 CTA の ClickButton）を参照。

## ページ追加の型

1. ルートの `index.html` を `<dir>/index.html` に複製し、画像は `<dir>/images/*.webp` に置いて相対パスで参照する。
2. ロゴは余白トリミング後に幅 560px、商品画像は白背景 640×640 の正方形、WebP 化する。
3. ブランド数に応じて `.brand-grid` の列数と `max-width` を変える。
4. `og:url` / `og:image` は `https://ppl-select.com/<dir>/...` の絶対 URL にする。
5. Qoo10 URL は実ページを開いてブランドとの対応を確認してから差し込む。
6. 公開前に CSS と DOM のクラス突合、スマホ幅でのスクリーンショット確認を行う。

## 変更履歴

| 日付 | 対象 | 内容 |
|---|---|---|
| 2026-09-03 | /cm-a/ | TikTok Pixel を撤去（計測なしの状態に戻す。Qoo10 リンクの変更は維持） |
| 2026-09-03 | /cm-a/ | malun malun の Qoo10 リンクを 1069270140 → 1072234942（2＋1箱 メガ割限定ページ）に差し替え |
| 2026-09-03 | /cm-a/ | TikTok Pixel を設置（Pageview ＋ Qoo10 CTA の ClickButton） |
| 2026-09-02 | /cm-a/ | malun malun × Isntree の2ブランド版を新規公開、Qoo10 リンク設定、画像を `cm-a/images/` に移動 |
| 2026-09-01 | / | カスタムドメイン `ppl-select.com` を設定、OGP を独自ドメインに更新、PR 表記をバッジ化 |
| 2026-09-01 | / | エンジニアレビュー対応（OGP/lang/favicon 追加、画像 WebP 化と外部ファイル化、不要 CSS 削除、モバイル調整） |
| 2026-08-31 | / | Beauty Trio Select（KOPHER × Anua × medicube）を新規公開 |
