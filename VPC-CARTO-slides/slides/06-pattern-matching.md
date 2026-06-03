<!-- .slide: class="section-title" -->

<div class="part-no">PART III · 06</div>

# Pattern Matching

<span class="pill pill-pm">CONFIDENSE™ Acquisition Filter</span>

<div class="subtitle">以 12-lead morphology 即時辨識 target VPC · 確保 mapping points 來自同一型態</div>

Note:
Pattern Matching 不是獨立的模組 — 它是 CONFIDENSE™ 模組的其中一個 acquisition filter。下一張說明這個關係。

---

## Pattern Matching 在 CARTO 3 架構中的位置

<div class="callout orange">
<span class="label">官方定義</span>
Pattern Matching 是 <strong>CONFIDENSE™ 模組</strong>下的一個 <strong>optional acquisition filter</strong>，用在 <strong>continuous mapping</strong>（連續收點）流程中。它依照 user 預先定義的 surface ECG（或 IC unipolar）pattern，判斷每一拍是否符合，只讓符合的點被收進 map。
</div>

<div class="cols">
<div>

### CONFIDENSE™ Continuous Mapping Filters
- Density（點密度）
- **Pattern Matching**（形態比對）
- Position Stability（位置穩定）
- LAT Stability（LAT 穩定）
- Cycle Length（週期長度）
- Respiration Gated（呼吸校正）

</div>
<div>

### 為什麼是 Filter？
- 每收一拍，所有開啟的 filter 都要 **同時通過**
- 任一 filter fail → 該點被丟棄
- Pattern Matching 是 **morphology gate** — 不像 template 的拍子不收

</div>
</div>

Note:
這就是為什麼 Pattern Matching 從 baseline 就要開 — 它是 continuous mapping 的把關者。Filters Status bar 隨時顯示每個 filter 過或不過。

---

## 什麼時候用？

<div class="callout red">
<span class="label">使用時間點</span>
<strong>一開始 baseline recording 就要開。</strong>
</div>

尤其在以下情況非常重要：

| 情境 | 是否需要 Pattern Matching |
| --- | --- |
| 多種 VPC morphology | **非常需要** |
| VPC 不頻繁 | 需要 |
| VPC 會被 sinus beat / fusion beat 干擾 | 需要 |
| ablation 後確認是否同一顆 VPC 消失 | 需要 |
| activation map 收點時避免收錯 morphology | **非常需要** |

Note:
case 一開始就開，整個 case 都不關。

---

## Pattern Matching 的目的

<div class="callout orange">
<strong>Pattern Matching 是用 surface ECG morphology 來辨認「現在這一拍是不是我們要打的 clinical VPC」。</strong>
</div>

它不是定位工具，而是：

```text
確保你 map 的每一個點，
都是同一種 VPC。
```

Note:
這點很重要：Pattern Matching 不告訴你 origin 在哪，它只負責「篩拍子」。

---

## Pattern Matching Viewer · 實際畫面

<img src="assets/carto/pattern-matching-viewer.png" alt="Pattern Matching Viewer screen showing 12-lead comparison with similarity score" />
<span class="fig-cap">CARTO 3 Pattern Matching Viewer · 左：template (-0.14 similarity)、右：clinical PVC 12-lead 對照</span>

Note:
左邊是建立好的 BS PVC 1 template，右邊是即時比對的 beat。系統會給每一拍一個 similarity score（這張是 -0.14，代表還沒對上）。實戰中我們設定 ≥ 90% 才納入 LAT map。

---

## 建立 Template · Pattern Bank 介面

<div class="cols image-wide">
<div>

### 步驟
1. 挑一拍乾淨的 clinical PVC
2. Type 選 **PVC**
3. 12-lead 自動載入
4. 設定 sample window (–18 → 150 ms)
5. 按 **OK** 存入 Pattern Bank
6. 之後 mapping 都用這個 template

</div>
<div>

<img src="assets/carto/pattern-bank-single.png" alt="Pattern Bank single template setup" />
<span class="fig-cap">Pattern Bank · 建立 BS PVC 1 template (CARTO 3 IFU)</span>

</div>
</div>

---

<!-- .slide: class="v-center" -->

## 操作概念

<div class="workflow-grid">
<div class="workflow-step">
<div class="num">1</div>
<div class="title">找到清楚的 clinical VPC</div>
<div class="desc">挑一拍乾淨、無 fusion、12-lead 完整的 VPC</div>
</div>
<div class="workflow-step">
<div class="num">2</div>
<div class="title">用 12-lead ECG 建立 template</div>
<div class="desc">系統會記下這拍的 morphology 作為比對基準</div>
</div>
<div class="workflow-step">
<div class="num">3</div>
<div class="title">後續 VPC 自動比對</div>
<div class="desc">系統判斷每一拍與 template 的相似度</div>
</div>
<div class="workflow-step">
<div class="num">4</div>
<div class="title">高相似度才納入 LAT map</div>
<div class="desc">設定相似度門檻（如 ≥ 90%）</div>
</div>
<div class="workflow-step">
<div class="num">5</div>
<div class="title">不同 morphology 排除或另分類</div>
<div class="desc">交給 Auto Pattern Bank 處理</div>
</div>
</div>

---

## 沒有 Pattern Matching 會發生什麼？

<div class="callout red">
<span class="label">災難情境</span>
你以為你在 map 同一顆 VPC，其實中間混進不同 origin 的 VPC，最後 LAT map 變亂、earliest point 不可信、找錯 origin、燒了沒效果。
</div>

**解法**：baseline 就開 Pattern Matching，收點時看 similarity（建議門檻 ≥ 90%），不確定就先停手驗證。

Note:
下一個模組 Auto Pattern Bank 是 Pattern Matching 的好搭檔 — PM 過濾單一 target，APB 自動分類所有 morphology。
