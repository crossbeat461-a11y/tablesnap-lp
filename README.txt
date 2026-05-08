# TableSnap Pro - High-Precision Table Data Extractor

<div align="right">
  <a href="#jp-日本語">JP</a> | <a href="#en-english">EN</a>
</div>

---

## <a name="jp-日本語"></a> 🇯🇵 日本語仕様

<details open>
<summary><b>1. プロダクト概要</b></summary>
Webページ上の複雑なHTMLテーブルを、構造を維持したまま瞬時に抽出するChrome拡張機能です。特にAI（ChatGPT/Claude）へのデータ投入や、Excel/Googleスプレッドシートへの貼り付けを最適化するように設計されています。
</details>

<details>
<summary><b>2. 技術的特徴・工夫</b></summary>

- **高精度TSVフォーマッタ**: `innerText.trim()` をベースに、セル内の改行や空白を保持しつつ、列をタブ（`\t`）、行を改行（`\n`）で構造化します。これにより、AIがデータの区切りを完璧に誤認せず読み取ることが可能です。
- **堅牢なUI分離 (Shadow DOM)**: 拡張機能のUIをShadow DOM内に構築することで、閲覧中のサイトのCSS干渉を100%遮断し、常に一貫した操作感を提供します。
- **動的ハイライトエンジン**: `mouseover` イベントにより、抽出範囲（テーブル全体、行、セル）をリアルタイムに視覚化。複雑なネスト（入れ子）構造のテーブルでも、狙った範囲を逃しません。
- **プライバシー・ファースト**: すべての解析・抽出処理はブラウザのContent Script内（ローカル）で完結。外部サーバーへのデータ送信は一切行いません。
</details>

<details>
<summary><b>3. 実装詳細</b></summary>

- **コアロジック**: `content.js` がDOMをトラバースし、ターゲットとなる `<table>` や `<tr>` 要素を特定。
- **多言語対応 (i18n)**: 日本語、英語を含む14カ国語以上のメッセージリソースを完結。
- **Manifest V3準拠**: Google Chromeの最新基準に基づいたセキュアな設計。
</details>

---

## <a name="en-english"></a> 🇺🇸 English Specifications

<details>
<summary><b>1. Product Overview</b></summary>
A Chrome extension designed to instantly extract complex HTML tables from web pages while preserving their structure. Optimized specifically for data input into AI models (ChatGPT/Claude) and seamless pasting into Excel/Google Sheets.
</details>

<details>
<summary><b>2. Technical Highlights</b></summary>

- **High-Precision TSV Formatter**: Utilizes a logic that structures data with tab delimiters (`\t`) for columns and newlines (`\n`) for rows while maintaining cell-internal formatting. This ensures AI models can interpret data boundaries with 100% accuracy.
- **Robust UI Isolation (Shadow DOM)**: By building the UI within a Shadow DOM, the extension prevents CSS interference from the host website, ensuring a consistent user experience regardless of the site's design.
- **Dynamic Highlight Engine**: Tracks `mouseover` events to visually indicate the extraction scope (Table, Row, or Cell) in real-time. Even with deeply nested table structures, users can accurately select the target data.
- **Privacy First Architecture**: All parsing and extraction processes are handled entirely within the browser's Content Script (local). No data is ever transmitted to external servers.
</details>

<details>
<summary><b>3. Implementation Details</b></summary>

- **Core Logic**: `content.js` traverses the DOM to identify target `<table>` and `<tr>` elements efficiently.
- **Internationalization (i18n)**: Fully localized for 14+ languages including English and Japanese.
- **Manifest V3 Compliant**: Built with the latest secure standards required by the Google Chrome Web Store.
</details>
