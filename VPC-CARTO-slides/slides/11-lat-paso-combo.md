<!-- .slide: class="section-title" -->

<div class="part-no">PART IV · 11</div>

# LAT Hybrid + PASO 結合

<div class="subtitle">把兩個模組疊在一起 · VPC ablation 成敗重點</div>

Note:
這是 Workflow Part 8。LAT 找最早，PASO 確認相似 — 兩者疊合才是真正 target。

---

## 最理想 target

<div class="cols image-wide">
<div>

```text
Earliest activation
+ unipolar QS
+ PASO high score
```

<div class="callout gold">
<span class="label">Sweet Spot</span>
LAT 找位置、PASO 確認相似、unipolar QS 證明 focal — 三項齊全才下手。
</div>

</div>
<div>

<img src="assets/carto/lat-propagation-3d.png" alt="LAT propagation 3D chamber view" />
<span class="fig-cap">LAT propagation 3D · 紅色 hot zone = earliest activation cluster</span>

</div>
</div>

Note:
這是教科書級的完美組合 — 任何一項缺，都要先思考為什麼。

---

## ⭐ 不同情況處理表

| 情況 | 解讀 | 策略 |
| --- | --- | --- |
| **LAT earliest + PASO 高** | 最佳 target | **優先 ablation** |
| **LAT earliest + PASO 低** | 可能 deep origin / poor pacing capture / far-field | 檢查 contact、output、鄰近結構 |
| **LAT 不夠早 + PASO 高** | 可能 exit site | 可燒，但需找更早點 |
| **多處 PASO 高** | 可能 broad breakout / intramural | 需多 chamber mapping |
| **PASO 高但 ablation 無效** | 可能不是 origin，只是 exit | 去 opposite side / cusp / CS / LV summit 找 |

Note:
這張表是 case 中遇到「mismatch」時的決策樹 — 不要把 mismatch 當隨機，每種組合都告訴你下一步。

---

## 各情境深入解讀

<div class="cols">
<div>

### LAT 早但 PASO 低
- Catheter 沒貼好？
- Pacing output 不對？
- Far-field 被誤抓？
- Intramural origin？

### LAT 不夠早但 PASO 高
- 你在 **exit site**
- 真 origin 在更深處
- 沿著 activation 梯度往早處找

</div>
<div>

### 多處 PASO 高
- Broad breakout
- Intramural origin (LV summit)
- 需要 multi-chamber

### PASO 高卻燒不掉
- 別只燒同一處
- 換 chamber：cusp / CS / 對側
- 考慮 epicardial

</div>
</div>

---

## 🎯 LAT + PASO · 一句話

<div class="callout red">
<span class="label">核心邏輯</span>
LAT 告訴你<strong>「電氣從哪冒出來」</strong>，PASO 告訴你<strong>「pacing 像不像」</strong>。<br/>
兩者一致 → 燒。<br/>
兩者不一致 → 先想為什麼，再決定要不要燒。
</div>

Note:
這是整個 workflow 的「最後確認」 — 進入 Part V Ablation 之前的最後 checkpoint。
