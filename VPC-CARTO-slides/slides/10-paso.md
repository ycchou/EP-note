<!-- .slide: class="section-title" -->

<div class="part-no">PART IV · 10</div>

# PASO

<span class="pill pill-paso">CARTO Module 4 / 4</span>

<div class="subtitle">Pace Mapping · 確認 paced QRS 與 clinical PVC 的相似度</div>

Note:
這是 Workflow Part 7。PASO 是 CARTO 的 pace mapping 工具，與 LAT Hybrid 配合使用。

---

## 什麼時候用？

PASO 通常在以下時機使用：

| 時間點 | PASO 角色 |
| --- | --- |
| **VPC 很少時** | **主力工具之一** |
| activation map 找到 early site 後 | confirm target |
| ablation 前 | 確認 pace map similarity |
| 多個 early sites 差不多時 | 幫助選點 |
| suspected exit site vs origin 不一致時 | 幫助理解 breakout |
| ablation 後還有 PVC | 找殘餘或新 morphology |

Note:
VPC 少的時候 LAT 收不到點，PASO 就成為主力 — 後面 scenario 會深入講。

---

## PASO 是什麼？

<div class="callout">
<strong>PASO 是 CARTO 的 pace mapping 工具，用 pacing QRS 與 clinical PVC QRS 做相似度比較。</strong>
</div>

簡單說：

```text
在某個點 pacing，
如果 paced QRS 長得很像 clinical PVC，
代表這個點接近 PVC 出口或 origin。
```

Note:
PASO 比較的是「人造的這拍」和「自然的這拍」 morphology — 越像，代表 pacing 點越接近真正 origin / exit。

---

## ⭐ PASO 高分代表什麼？

<img src="assets/diagrams/paso-similarity.svg" alt="PASO similarity bar with 4 zones and lead refinement guide" class="svg-fit" />

Note:
PASO 分數區間：&gt; 95% 非常好；90–95% 很有價值；85–90% 可接受但需搭配 activation；&lt; 85% 可能不是最佳點，或 pacing capture / output / fusion 有問題。但要記得「PASO 高 ≠ 真正 origin」，可能是 exit site。

---

## ⚠️ PASO 高分 ≠ 真正 origin

```text
PASO 高分不一定等於真正 origin。
它可能是 exit site，而不是 deep origin。
```

尤其在：

<div class="cols">
<div>

- LV summit
- intramural PVC

</div>
<div>

- papillary muscle
- fascicular PVC
- **epicardial origin**

</div>
</div>

<div class="callout red">
<span class="label">關鍵警告</span>
這些「深層」或「特殊位置」的 VPC，PASO 高分也可能燒不掉 — 因為你找到的是 exit，不是 origin。
</div>

Note:
這就是為什麼 LV summit case 即使 PASO 95% 也可能燒失敗 — 真正 origin 在 intramural 或 epicardial。

---

## PASO Viewer · 實際畫面

<div class="cols image-wide">
<div>

<img src="assets/vgh/paso-viewer-vgh.png" alt="VGH PASO Viewer with correlation score" />
<span class="fig-cap">PASO Viewer · Correlation 0.998 + 12-lead 對齊比較</span>

</div>
<div>

### 戰術重點 (VGH-TP)

- **臨床 12-lead VT 波形為 template**
- **Pace mapping score &gt; 90% 視為接近 exit site**
- 每條 lead 都看 morphology 對不對齊
- 不像的 lead → 告訴你 catheter 要往哪邊移

</div>
</div>

Note:
這張是 VGH 真實 PASO Viewer — Correlation 0.998 表示這個 pacing 點與 clinical VT 波形 99.8% 相似。VGH-TP 的門檻：>90% 就認為接近 exit site，搭配 LAT earliest 一起決定 RF target。

---

## PASO 操作步驟

### Step 1 · 建立 clinical PVC template
使用目標 VPC 的 12-lead morphology。

### Step 2 · 在疑似區域 pacing

```text
低 output 優先，例如接近 threshold 的 2x capture threshold
```

<div class="callout">
如果 output 太高，會 capture 太大範圍，造成<strong>假性高分</strong>。
</div>

Note:
這是初學者最常犯的錯 — 用太高 output pacing，會把鄰近組織也激活，得到「看起來很像」的假分數。

---

## PASO 操作 · Step 3 比較 paced QRS 與 clinical PVC

看：

1. **PASO percentage**
2. 每個 lead 的 morphology
3. QRS onset
4. intrinsicoid deflection
5. R/S transition
6. limb lead axis

### Step 4 · 標記高分區域

在 CARTO map 上標示：

```text
PASO 95%
PASO 92%
PASO 88%
```

再與 **LAT early zone 疊合**。

Note:
PASO map 與 LAT map 疊合是 ablation 前的最終確認 — 兩張圖的 hot zone 重合，就是 sweet spot。

---

## PASO 判讀技巧 · 最重要不是總分

```text
PASO 93%
但是 V1–V3 transition 不對
```

<div class="callout red">
<span class="label">關鍵</span>
這代表可能左右或 anterior / posterior 位置還差一點。
</div>

Note:
要看每條 lead 哪裡不像 — 不像的 lead 告訴你「該往哪邊修正」。

---

## 常見修正方向

| Pace map 差異 | 修正方向 |
| --- | --- |
| **V1–V2 R 波太小** | 更左側 / 更 posterior |
| Transition 比 clinical PVC 晚 | pacing 太右，往左 |
| **Lead I 太正** | site 太右，往左 |
| Inferior leads 不夠高 | site 太低，往更 superior |
| III 比 II 差很多 | 左右 / 前後方向需修正 |
| aVL / aVR 不像 | OT 左右上方位置需修正 |

Note:
這張表是 PASO 修正的「導航地圖」 — 看哪條 lead 不像，就知道下一拍要往哪邊移 catheter。
