# VPC Ablation with CARTO 3 · 訓練簡報

> A reveal.js training deck for CARTO 3 operators / Biosense Webster field engineers.
> 基於 [`ycchou/EP-note`](https://github.com/ycchou/EP-note) 的臨床筆記 (`VPC-case-workflow.md`, `VPC-origin.md`, `Transition Zone.md`) 製作。

---

## 內容

- 20 章 ~82 張投影片，繁中為主、英文術語
- 完整覆蓋 Workflow Part 1–15：Pre-case → Setup → Mapping → PASO → Ablation → Scenarios → Decision Tree
- 4 大 CARTO 模組：**Pattern Matching · Auto Pattern Bank · LAT Hybrid · PASO**
- 6 種臨床 scenario：RVOT / Infrequent / Multi-morphology / LV summit / Papillary muscle / Para-Hisian
- 內建 speaker notes（按 `S` 開講者視圖）
- 內建搜尋（按 `Ctrl-Shift-F`）
- 支援 PDF 匯出

---

## 快速開始

### 本地預覽

reveal.js 需要透過 HTTP server 載入 markdown，**不能直接 file:// 開啟**。

```bash
# 方法 1：Python 3（最簡單）
cd VPC-CARTO-slides
python -m http.server 8000

# 方法 2：Node.js
npx serve .

# 方法 3：VS Code Live Server 擴充套件
```

開啟瀏覽器：

```
http://localhost:8000/
```

### 鍵盤快捷鍵

| Key | 動作 |
| --- | --- |
| `→` `↓` `Space` | 下一張 |
| `←` `↑` | 上一張 |
| `Esc` | 縮覽全部投影片 |
| `S` | 開啟 Speaker view（含 notes、計時、下一張預覽） |
| `F` | 全螢幕 |
| `Ctrl-Shift-F` | 全文搜尋 |
| `B` | 黑屏（暫時遮蓋畫面） |
| `?` | 顯示快捷鍵說明 |

---

## 匯出 PDF

1. 用 Chrome 開啟：

   ```
   http://localhost:8000/?print-pdf
   ```

2. `Ctrl-P` (Windows) / `Cmd-P` (macOS) 開列印對話
3. 目的地選「另存為 PDF」
4. 紙張大小：A4 橫向 · 邊界：無 · 背景圖形：勾選

詳細匯出設定請見 [reveal.js 官方文件](https://revealjs.com/pdf-export/)。

---

## 編輯內容

### 修改投影片

所有投影片內容都在 `slides/*.md`，是純 markdown，直接編輯即可：

```
slides/
├── 00-title.md
├── 01-vpc-origin-basics.md
├── 02-transition-zone.md
├── ...
└── 19-summary-closing.md
```

### Markdown 慣例

- 投影片分隔：**空行 + `---` + 空行**（水平翻頁）
- Vertical slide 分隔：**空行 + `--` + 空行**
- Speaker notes：以 `Note:` 開頭的段落

### 自訂樣式

調色、字體、版面樣式都在：

```
css/carto-theme.css
```

主要 CSS 變數：

| 變數 | 預設值 | 用途 |
| --- | --- | --- |
| `--jnj-red` | `#c8102e` | J&J 紅 |
| `--carto-deep` | `#0b1e3f` | CARTO 深藍 |
| `--carto-cyan` | `#16b8c7` | 重點青 |
| `--highlight` | `#ffd166` | 警示金 |

---

## 部署到 GitHub Pages

`EP-note` repo 已 push 後，可在 GitHub 設定 Pages：

1. Repository → Settings → Pages
2. Source 選 `main` branch、Folder 選 `/ (root)`
3. 等 1–2 分鐘
4. 公開網址：

   ```
   https://ycchou.github.io/EP-note/VPC-CARTO-slides/
   ```

或可建一個 `gh-pages` branch 只放這個資料夾。

---

## 檔案結構

```
VPC-CARTO-slides/
├── index.html              ← reveal.js 入口
├── README.md               ← 本檔
├── lib/
│   └── reveal.js/          ← reveal.js 6.0.1 (dist + LICENSE)
├── css/
│   └── carto-theme.css     ← 自訂 J&J/CARTO 視覺
├── slides/
│   ├── 00-title.md
│   ├── 01-vpc-origin-basics.md
│   ├── 02-transition-zone.md
│   ├── 03-pre-case-prep.md
│   ├── 04-case-setup.md
│   ├── 05-baseline-assessment.md
│   ├── 06-pattern-matching.md
│   ├── 07-auto-pattern-bank.md
│   ├── 08-anatomy-map.md
│   ├── 09-lat-hybrid.md
│   ├── 10-paso.md
│   ├── 11-lat-paso-combo.md
│   ├── 12-ablation-targeting.md
│   ├── 13-during-ablation.md
│   ├── 14-post-ablation.md
│   ├── 15-scenarios.md
│   ├── 16-module-timeline.md
│   ├── 17-decision-tree.md
│   ├── 18-lab-script.md
│   └── 19-summary-closing.md
└── assets/
    ├── jnj-logo.svg        ← J&J 商標
    ├── diagrams/           ← 自訂流程圖（預留）
    └── ecg/                ← ECG 範例截圖（預留）
```

---

## 商標與授權

- **Johnson & Johnson** 與 **CARTO 3** 為 Johnson & Johnson 及其子公司 Biosense Webster 的註冊商標。本簡報僅作為 J&J / Biosense Webster CARTO 3 trainer 的內部訓練教材。
- 投影片內容（文字、表格、決策樹）依據 [`ycchou/EP-note`](https://github.com/ycchou/EP-note) 的個人臨床筆記整理。
- reveal.js 採 MIT License — 見 `lib/reveal.js/LICENSE`。

---

## 致謝

- 原始筆記作者：**ycchou** ([github.com/ycchou/EP-note](https://github.com/ycchou/EP-note))
- 簡報架構：reveal.js 6.0.1
