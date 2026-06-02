<!-- .slide: class="section-title" -->

<div class="part-no">PART IV · 09</div>

# LAT Hybrid

<span class="pill pill-lat">CARTO Module 3 / 4</span>

<div class="subtitle">Activation Mapping · 找最早 ventricular activation site</div>

Note:
這是 Workflow Part 6–7 的核心。Target VPC morphology 確認後，就靠 LAT Hybrid 找 earliest site。

---

## 什麼時候用？

<div class="callout red">
<strong>當你已經鎖定 target VPC morphology 後，開始做 activation map 時使用。</strong>
</div>

也就是：

```text
Pattern Matching / Auto Pattern Bank 確認目標 VPC
                    ↓
              開始收 activation points
                    ↓
                使用 LAT Hybrid
```

Note:
順序很重要：沒先鎖定 morphology 就開 LAT，等於什麼都沒做。

---

## LAT Hybrid 的目的

<div class="callout">
<strong>LAT Hybrid 是用來建立 VPC 的 local activation time map，找出最早的 ventricular activation site。</strong>
</div>

簡單說：

```text
誰最早 depolarize，
誰最可能靠近 VPC origin。
```

Note:
這是 activation mapping 的基本原理 — 最早被激活的點，就是電氣傳導的起點。

---

## Reference Annotation · 核心設定

你需要選定一個穩定 reference，常見方式：

| Reference | 說明 |
| --- | --- |
| **Surface ECG QRS onset** | 常用於 PVC activation timing |
| Intracardiac reference | 若穩定，可輔助 |
| CS / RV catheter | 需確認每拍穩定 |

VPC map 常見是以：

```text
PVC QRS onset = time zero
```

然後找 local EGM 比 QRS onset 早多少 ms。

Note:
QRS onset 在 12-lead 上要看最早出現偏離 baseline 的那條 lead，通常用 V1 或 lead II 為基準。

---

## ⭐ 最重要的數字

| Finding | 意義 |
| --- | --- |
| local bipolar EGM 提前 QRS onset **20 ms** | 可能接近 |
| 提前 **30 ms** | 很有意義 |
| 提前 **40 ms 以上** | **非常可疑 origin** |
| **unipolar QS pattern** | 支持 focal origin 附近 |
| local EGM sharp prepotential | fascicular / Purkinje 或特殊 substrate |

<div class="callout red">
<span class="label">數字記憶</span>
<strong>–20 / –30 / –40 ms</strong> · 越早越接近 origin；加上 unipolar QS 才是真正的 sweet spot。
</div>

Note:
這幾個數字一定要背下來 — 是 LAT Hybrid 判讀的核心 threshold。

---

## 操作邏輯 · Step 1 只收 target VPC

用 **Pattern Matching** 過濾，避免混入不同 VPC morphology。

```text
只接受與 target template 高度相似的 PVC beats。
```

Note:
這就是為什麼 Pattern Matching 一開始就要開。

---

## 操作邏輯 · Step 2 檢查每個點 annotation

CARTO 自動 annotation 很方便，但 **VPC mapping 不能完全盲信**。

每個重要 early point 要看：

```text
1. bipolar EGM onset
2. unipolar morphology
3. 是否為 far-field
4. catheter contact
5. 是否同一種 VPC
6. beat 是否 fusion
```

<div class="callout red">
<span class="label">注意</span>
Auto annotation 有時會把 far-field signal 抓成 local onset；早 30 ms 的點如果是 far-field，會誤導整張 map。
</div>

---

## 操作邏輯 · Step 3 找 earliest activation

在 LAT map 上尋找最早區域：

```text
紅色 / earliest color zone
```

**但不要只看顏色，要看訊號。**

真正好的 target 通常有：

| 條件 | 理想表現 |
| --- | --- |
| Bipolar timing | earliest，常 **–20 到 –40 ms** |
| Unipolar | **QS pattern**，快速下降 |
| Contact | 穩定 |
| Pattern matching | 高相似度 |
| Pace map | **PASO 高分** |
| Anatomy | 合理且安全 |

---

## ✅ Good Activation Target 長怎樣？

```text
PVC morphology = target VPC
Local bipolar EGM = earliest
Local timing = -35 ms before QRS onset
Unipolar = QS with steep initial negative deflection
PASO = 92%
Anatomy = RVOT septal site
```

<div class="callout">
<span class="label">這就是很漂亮的 ablation target</span>
六個條件全部對上 → confident 燒下去。
</div>

Note:
–35 ms、PASO 92%、unipolar QS — 這組數字是教科書級的完美 target。

---

## ❌ Bad Activation Point 長怎樣？

```text
LAT 很早，但：
- beat morphology 不像 target PVC
- EGM 很鈍，像 far-field
- catheter contact 不穩
- unipolar 不是 QS
- 點位孤立，周圍沒有 early zone
```

<div class="callout red">
<span class="label">不要急著燒</span>
這種點先確認 — 通常是 fusion beat、far-field、或不同 morphology 的 VPC 被誤收。
</div>

Note:
「點位孤立、周圍沒有 early zone」是很重要的提示 — 真 origin 周圍應該有梯度，孤點通常是 artifact。

---

## 🎯 LAT Hybrid · 一句話

<div class="callout gold">
<span class="label">記憶點</span>
LAT Hybrid = <strong>找最早</strong>。<br/>
但「最早 ≠ 一定是 origin」 — 要配 unipolar QS、好 contact、Pattern Matching 確認，才能下手。
</div>
