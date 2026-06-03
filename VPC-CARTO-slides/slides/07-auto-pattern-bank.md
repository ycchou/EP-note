<!-- .slide: class="section-title" -->

<div class="part-no">PART III · 07</div>

# Auto Pattern Bank

<span class="pill pill-apb">CARTO Module 2 / 4</span>

<div class="subtitle">自動把 VPC 分成 A 型、B 型、C 型</div>

Note:
Auto Pattern Bank 與 Pattern Matching 是雙生模組。一個鎖定 target，一個自動分類所有 morphology。

---

## 什麼時候用？

<div class="callout">
<span class="label">使用時間點</span>
<strong>在 baseline rhythm assessment 或 mapping 初期就開。</strong>
</div>

尤其適合：

| 情境 | 使用 Auto Pattern Bank |
| --- | --- |
| 病人有 multiple PVC morphology | **必用** |
| 不確定 clinical PVC 是哪一個 | 很有用 |
| VPC burden 高但型態混雜 | 很有用 |
| ablation 後出現新 morphology | 用來分辨是不是新 VPC |
| **redo case** | 幫助整理不同 morphology |

Note:
Redo case 最常見的情境就是「上次燒掉一顆，又長出新的一顆」 — APB 直接告訴你它是新還是舊。

---

## Auto Pattern Bank 的角色

<div class="callout orange">
<strong>Auto Pattern Bank 會自動把不同 morphology 的 VPC 分類成不同 pattern。</strong>
</div>

你可以把它想成：

```text
自動幫你把 VPC 分成 A 型、B 型、C 型。
```

---

## Auto Pattern Bank · 實際畫面

<div class="cols image-wide">
<div>

<img src="assets/carto/auto-pattern-bank-panel.png" alt="Auto Pattern Bank panel with 6 categorized VPC morphologies" style="max-height:340px;" />

</div>
<div>

- **Pattern 1 (547 beats)** — 主要 morphology
- **Pattern 2 / 3** (160 / 79) — 次要
- **Pattern 4–6** — 偶發
- 下方 Cycle Length / burden 並排

<div class="callout orange">
看一眼知道：病人有幾型、哪型最多、該鎖定哪型當 target。
</div>

</div>
</div>

Note:
Pattern 1 設為 clinical target；其餘 morphology 暫時不收進 LAT map。範例對照：Pattern 1 (LBBB/inferior) ≈ RVOT VPC；Pattern 2 (RBBB/superior) ≈ LV inferior；Pattern 3 (LBBB/normal axis) ≈ para-Hisian / RV septal。

---

## Auto Pattern Bank vs Pattern Matching

| 功能 | 主要用途 |
| --- | --- |
| **Pattern Matching** | 判斷某一拍是否符合你指定的 target morphology |
| **Auto Pattern Bank** | 自動分類多種 VPC morphology |

<div class="cols">
<div>

### Pattern Matching
- 你指定一個 target
- 系統二分法：像 / 不像
- 用於 mapping 過濾

</div>
<div>

### Auto Pattern Bank
- 系統自動分組
- 多分類
- 用於探索 morphology

</div>
</div>

Note:
兩者互補。多 morphology case 通常先開 APB 看有幾型，再決定 Pattern Matching 鎖哪一個 target。

---

## 實戰用法 · 三步驟

1. **Baseline 觀察幾分鐘** → 讓 APB 自動收集 PVC morphology
2. **選 clinical VPC** → 依術前 12-lead、Holter dominant、病人症狀時的 VPC、lab 最常出現型態決定要打哪一型
3. **設成 target** → 用 Pattern Matching 鎖定該 morphology

<div class="callout gold">
<span class="label">關鍵</span>
不能只看 lab 裡多的那一型，要回到 Holter 看「真正讓病人症狀的那一型」 — 那才是 clinical target。
</div>
