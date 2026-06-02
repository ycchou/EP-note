<!-- .slide: class="section-title" -->

<div class="part-no">PART VI · 17</div>

# 臨床 Decision Tree

<div class="subtitle">VPC 一出現，每個分岔點該怎麼選</div>

Note:
這是 Workflow Part 14。把整個 case 的決策邏輯壓縮成一棵樹。

---

## VPC Decision Tree

```text
VPC 出現
│
├─ 是否為 clinical PVC？
│   ├─ Yes → Pattern Matching confirms → 收進 LAT map
│   └─ No  → Auto Pattern Bank 分到其他 morphology，不納入 target map
│
├─ VPC 是否頻繁？
│   ├─ Frequent   → LAT Hybrid activation mapping 為主
│   └─ Infrequent → PASO + limited activation + anatomy guide
│
├─ LAT earliest 是否夠早？
│   ├─ Yes → 看 unipolar QS + contact + PASO
│   └─ No  → 換 chamber / opposite side / cusp / CS
│
├─ PASO 是否高？
│   ├─ High → 支持 target
│   └─ Low  → 檢查 pacing output / contact，或考慮 deep / intramural origin
│
└─ Ablation
    │
    ├─ Target PVC 消失 → wait + induction
    └─ 未消失         → 重新檢查 morphology / chamber / mapping quality
```

Note:
這棵樹是 case 中遇到分岔時的「導航圖」 — 每個 yes / no 都有清楚的下一步。

---

## 樹的核心邏輯

<div class="workflow-grid">
<div class="workflow-step">
<div class="num">1</div>
<div class="title">先問是不是 clinical</div>
<div class="desc">Pattern Matching = 過濾器</div>
</div>
<div class="workflow-step">
<div class="num">2</div>
<div class="title">再問頻不頻繁</div>
<div class="desc">決定 LAT 主導 還是 PASO 主導</div>
</div>
<div class="workflow-step">
<div class="num">3</div>
<div class="title">看 LAT 夠不夠早</div>
<div class="desc">不夠早 → 換 chamber</div>
</div>
<div class="workflow-step">
<div class="num">4</div>
<div class="title">看 PASO 夠不夠高</div>
<div class="desc">不夠高 → 檢查 contact / output</div>
</div>
<div class="workflow-step">
<div class="num">5</div>
<div class="title">RF 後驗證</div>
<div class="desc">消失 → wait；沒消 → 重新 map</div>
</div>
</div>

Note:
每個 case 都會經過這 5 個分岔點 — 練熟這棵樹，case 就會行雲流水。
