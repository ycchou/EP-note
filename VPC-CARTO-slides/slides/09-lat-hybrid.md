<!-- .slide: class="section-title" -->

<div class="part-no">PART IV · 09</div>

# LAT Hybrid

<span class="pill pill-lat">CARTO Module 3 / 4</span>

<div class="subtitle">專為 PVC mapping 設計的 Hybrid Point · 位置取自 sinus、激活取自 PVC</div>

Note:
LAT Hybrid 不是「一般 activation map」 — 它是 CARTO PRIME™ 模組中專門解決 PVC mapping 痛點的功能。下一張說明它真正在做什麼。

---

## LAT Hybrid 解決什麼問題？

<div class="callout red">
<span class="label">核心問題</span>
PVC 是 transient 心律 — 病人出現 PVC 時，<strong>呼吸與心搏的瞬間變化會讓 catheter 位置相對於 sinus rhythm 漂移</strong>。如果直接用 PVC 那一拍的 location 收點，整張 activation map 的幾何就會被「動過的位置」污染。
</div>

<div class="callout orange">
<span class="label">LAT Hybrid 的解法</span>
每一個 LAT Hybrid 點是<strong>「兩拍合成的 hybrid point」</strong>：
<ul>
<li><strong>Location data</strong>（catheter 位置）→ 取自 PVC 前的 <strong>sinus beat</strong></li>
<li><strong>LAT / EGM / Force</strong>（電氣訊號）→ 取自 <strong>PVC beat</strong></li>
</ul>
</div>

Note:
這是 CARTO PRIME™ 模組的功能，不是基本 LAT mapping。原理在 CARTO 3 IFU 第 320 頁有詳細說明。

---

## Hybrid Point 怎麼運作

<div class="workflow-grid">
<div class="workflow-step">
<div class="num">1</div>
<div class="title">Pattern Bank 雙 template</div>
<div class="desc">同時建立 PVC pattern + NSR pattern</div>
</div>
<div class="workflow-step">
<div class="num">2</div>
<div class="title">Auto acquisition</div>
<div class="desc">系統在 PVC beat 前找 2 個連續 sinus beats 取位置</div>
</div>
<div class="workflow-step">
<div class="num">3</div>
<div class="title">Manual acquisition</div>
<div class="desc">選定 PVC beat → 往前搜尋 5 個 sinus beats 找 location</div>
</div>
<div class="workflow-step">
<div class="num">4</div>
<div class="title">Non-Hybrid Point</div>
<div class="desc">找不到 sinus → 用 PVC 位置，標註 Non-Hybrid Point</div>
</div>
<div class="workflow-step">
<div class="num">5</div>
<div class="title">Catheter 顯示位置</div>
<div class="desc">畫面顯示 catheter 在 <strong>sinus rhythm 時的位置</strong></div>
</div>
<div class="workflow-step">
<div class="num">6</div>
<div class="title">電氣顯示</div>
<div class="desc">map 顏色 = PVC 的 LAT 值</div>
</div>
</div>

---

## Map Setup · LAT Hybrid 必要條件

| 條件 | 設定 |
| --- | --- |
| **Map type** | Ventricular maps only（atrial map 不可用） |
| **Pattern Bank** | 必須同時有 **PVC** + **NSR** template |
| **Pattern Matching filter** | 分別設定 PVC 與 NSR 兩條 |
| **Position Stability filter** | 預設 **4 mm** · 對 hybrid map 成效關鍵 |
| **Density filter** | 系統設為 maximum，不可修改 |
| **Cycle Length filter** | 不可用 |
| **Smart Index** | ⚠️ 不能與 LAT Hybrid 同時選 |
| **Map Replay** | 可在 standard map ↔ LAT Hybrid 之間轉換 |

Note:
Position Stability 預設 4 mm 是 hybrid map 成功的關鍵；catheter 不夠穩，sinus location 與 PVC activation 就配不準。

---

## Activation 找最早 · 重要數字

<img src="assets/diagrams/lat-timing-ruler.svg" alt="LAT timing threshold ruler showing -20, -30, -40 ms zones" />

| Local bipolar EGM 提前 QRS onset | 意義 |
| --- | --- |
| **20 ms** | 可能接近 |
| **30 ms** | 很有意義 |
| **40 ms 以上** | **非常可疑 origin** |
| 加上 **unipolar QS pattern** | 支持 focal origin |
| 加上 sharp prepotential | fascicular / Purkinje |

VPC map 以 **PVC QRS onset = time zero**，找 local EGM 比 QRS onset 早多少 ms。

---

## LAT Hybrid · 實際畫面

<img src="assets/carto/lat-activation-map.png" alt="CARTO 3 LAT Hybrid activation map" />
<span class="fig-cap">CARTO 3 LAT Hybrid Map · 紅色 = earliest activation（PVC beat 的 LAT）·  catheter 顯示於 sinus rhythm 位置</span>

Note:
這是真實 LAT Hybrid map — 顏色是 PVC 時的 LAT timing，但每個 point 的幾何位置是該 PVC 前 sinus beat 的位置，避免 PVC 時 catheter 漂移污染 map。

---

## Filters Status · 雙重檢查

<div class="cols image-wide">
<div>

LAT Hybrid 的 Filters Status bar 同時顯示：

- **PVC filter** 狀態（activation beat）
- **RS (Real Sinus) filter** 狀態（location beat）

任一 filter 不過 → 該點被丟棄。

點 status box 可在 pattern viewer 看細節。

</div>
<div>

<img src="assets/carto/reference-egm.png" alt="CARTO reference EGM channels" />
<span class="fig-cap">Reference EGM channels · annotation timing 必須在兩拍都穩定</span>

</div>
</div>

---

## ✅ Good LAT Hybrid Target 長怎樣？

<div class="cols image-wide">
<div>

```text
PVC morphology = target VPC template
NSR location stable (Position Stability passed)
Local bipolar EGM = earliest (–35 ms)
Unipolar QS · steep negative deflection
PASO = 92%
Anatomy = RVOT septal site
```

<div class="callout orange">
六項齊全 → confident ablation target
</div>

</div>
<div>

<img src="assets/carto/egm-timing-annotation.png" alt="EGM with timing annotation" />
<span class="fig-cap">EGM timing 視窗 · LAT 65 ms · 多通道對齊</span>

</div>
</div>

---

## ❌ 不可信的點

```text
LAT 看起來很早，但：
- beat morphology 不像 target PVC      (PVC filter fail)
- 該點沒有對應的 sinus location         (Non-Hybrid Point)
- EGM 鈍、像 far-field
- catheter contact 不穩 / Position Stability fail
- 點位孤立，周圍沒有 early zone gradient
```

<div class="callout red">
Non-Hybrid Point 與孤立 early point 都要先驗證再下手，不要被「紅色」誤導。
</div>
