# マトメル LP（matomeru-lp）

## 1. プロジェクト概要

### サービス名
マトメル（Matomeru）

### ワンライナー
「バラバラの売上を、一画面に。」

### サービス概要
整体・美容院・ネイルサロン・エステなど、小規模サービス業の店舗オーナー向けの売上統合ダッシュボードのランディングページ。
ホットペッパービューティ、EPARK、電話予約、LINE予約など、複数の予約チャネルからの売上データを1つのダッシュボードに集約し、月末の売上集計作業を大幅に削減するサービスの集客・訴求を行う。

### ターゲットユーザー
- 1店舗運営の個人事業主（整体・マッサージ・美容院・ネイル・エステ）
- ホットペッパービューティを使って集客している
- ITリテラシーは低め〜中程度
- 月額1万円程度なら払える

### 料金プラン（LP上の表示）
- 月額 ¥10,000（税別）
- 年額 ¥100,000（税別）＝2ヶ月分割引
- 初期費用なし

## 2. ディレクトリ構成

```
matomeru-lp/
├── CLAUDE.md              # この仕様書
├── index.html             # LPメインファイル（単一HTMLファイル）
├── images/                # Nano Banana生成画像（後から追加）
│   ├── hero-visual.png
│   ├── step1-csv.png
│   ├── step2-upload.png
│   ├── step3-dashboard.png
│   ├── icon-scattered.png
│   ├── icon-time.png
│   ├── icon-invisible.png
│   ├── icon-channels.png
│   ├── before.png
│   ├── after.png
│   ├── industry-seitai.png
│   ├── industry-biyou.png
│   ├── industry-nail.png
│   ├── industry-esthe.png
│   └── logo.png
└── README.md
```

## 3. LP構成（セクション順）

1. **ヘッダー（固定）** — ロゴ、ナビ（機能/料金/お問い合わせ）、CTAボタン「無料で相談する」
2. **ヒーロー** — キャッチコピー「月末の売上集計、まだ手作業ですか？」、サブコピー、CTAボタン、メインビジュアル（ダッシュボードモック）
3. **ペインポイント（4カード）** — 課題を4つ提示
   - 売上データがバラバラ
   - 月末の集計に時間がかかる
   - リアルタイムで売上が見えない
   - チャネルごとの把握ができない
4. **ソリューション** — ダッシュボードのアニメーション付きモックアップ（CSS）
5. **3ステップ説明** — STEP 1: CSVダウンロード → STEP 2: アップロード → STEP 3: ダッシュボード表示
6. **Before/After比較** — テーブル形式（毎月3〜4時間 → たった5分）
7. **対象業種** — 整体/美容院/ネイル/エステ（4カード）
8. **料金プラン** — 月額/年額の2プラン表示
9. **CTA** — 「まずはLINEで無料相談」ボタン + LINE QRコード
10. **マタキテ連携** — クロスセルセクション（「お客様の声も一元管理しませんか？」）
11. **フッター** — コピーライト、リンク

## 4. デザイン方針

### カラーパレット
```css
:root {
  --primary: #1a6fb5;        /* メイン青 */
  --primary-dark: #124d7e;
  --primary-light: #e8f2fb;
  --accent: #ff6b35;         /* アクセントオレンジ */
  --accent-light: #fff3ed;
  --text: #2a2a2a;
  --text-light: #6b7280;
  --bg: #fafcfe;
  --bg-warm: #f5f0eb;
  --white: #ffffff;
  --border: #e5e7eb;
}
```

### フォント
- 見出し: Zen Maru Gothic（丸ゴシック、親しみやすさ）
- 本文: Noto Sans JP（可読性重視）
- Google Fonts CDNから読み込み

### デザインテイスト
- クリーンで余白多め
- 角丸カード（border-radius: 16px〜20px）
- 柔らかい影（box-shadow: 0 4px 24px rgba(0,0,0,0.06)）
- モバイルファースト・レスポンシブ対応
- ガガガ決算（gagagakessan.com）のLP構成を参考にしている

## 5. 現在の実装状態

### 完了
- HTML/CSS/JS 単一ファイルで全セクション実装済み
- レスポンシブ対応済み
- ダッシュボードモックアップ（CSSアニメーション付き）
- Before/After比較テーブル
- 料金プランセクション

### 要改修

#### 5.1 画像差し替え（高優先度）
現在LPのアイコンに絵文字を使用している。
Nano Bananaで生成したフラットデザインイラストに差し替える。

差し替え対象と画像ファイル名の対応：

| セクション | 現状 | 差し替え画像 |
|---|---|---|
| ペインポイント1 | 📊 | images/icon-scattered.png |
| ペインポイント2 | ⏰ | images/icon-time.png |
| ペインポイント3 | 😰 | images/icon-invisible.png |
| ペインポイント4 | 📱 | images/icon-channels.png |
| STEP 1 | テキストのみ | images/step1-csv.png |
| STEP 2 | テキストのみ | images/step2-upload.png |
| STEP 3 | テキストのみ | images/step3-dashboard.png |
| Before | テキスト | images/before.png |
| After | テキスト | images/after.png |
| ヒーロー | CSSモック | images/hero-visual.png（任意） |
| 業種:整体 | 💆 | images/industry-seitai.png |
| 業種:美容院 | ✂️ | images/industry-biyou.png |
| 業種:ネイル | 💅 | images/industry-nail.png |
| 業種:エステ | 🧖 | images/industry-esthe.png |
| ロゴ | テキスト | images/logo.png |

#### 5.2 動画埋め込み（中優先度）
ヒーローセクション直下に30〜45秒のイメージ動画を埋め込む。
動画はYouTubeまたはVimeoにアップロードし、iframe埋め込み。
動画未完成の間はセクション自体を非表示にしておく。

#### 5.3 デモリンク追加（低優先度、アプリ完成後）
CTAボタンの横に「デモを試す →」リンクを追加。
リンク先はアプリのデモモード（サンプルデータ入り）。

#### 5.4 アプリへの導線
ヘッダーに「ログイン」ボタン追加。リンク先: https://app.matomeru.app/login（仮）
CTAセクションに「無料で始める →」ボタン追加。リンク先: https://app.matomeru.app/signup（仮）

## 6. ホスティング
- 方式: 静的ホスティング（Vercel / Netlify / Cloudflare Pages のいずれか）
- ドメイン: matomeru.app（仮）の / に配置
- アプリとは別デプロイ
- SSL: 自動（ホスティングサービス側）

## 7. 関連プロダクト

### マタキテ（Matakite）
- AI顧客フィードバック管理プラットフォーム（別サービス）
- LP内のクロスセルセクションからリンク
- バンドル提案: マトメル ¥10,000 + マタキテ ¥5,000 = ¥15,000/月

### マトメル アプリ（matomeru-app）
- 売上統合ダッシュボード本体
- 別リポジトリで管理
- LP完成後にログイン/サインアップへの導線を追加
