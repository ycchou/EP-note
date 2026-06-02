<!-- .slide: class="section-title" -->

<div class="part-no">PART VI · 16</div>

# 模組使用時間總表

<div class="subtitle">每個 case timing → 對應 CARTO module</div>

Note:
這是 Workflow Part 13。把四大模組綁到 case timeline，operator 在哪個時間點該開哪個模組一目了然。

---

## ⭐ Module Usage Timeline

| Case timing | 主要任務 | CARTO module / function |
| --- | --- | --- |
| **Baseline recording** | 收集 VPC 型態 | <span class="pill pill-apb">Auto Pattern Bank</span> |
| **Target selection** | 指定 clinical PVC | <span class="pill pill-pm">Pattern Matching</span> |
| **Anatomy build** | 建立 chamber 幾何 | CARTO anatomy / mapping |
| **Activation map** | 找 earliest activation | <span class="pill pill-lat">LAT Hybrid</span> |
| **Sparse PVC** | 補足定位 | <span class="pill pill-paso">PASO</span> |
| **Pre-ablation confirmation** | 確認 target site | <span class="pill pill-lat">LAT</span> + <span class="pill pill-paso">PASO</span> |
| **During ablation** | 觀察 PVC suppression | <span class="pill pill-pm">Pattern Matching</span> |
| **Post-ablation** | 確認 target morphology 消失 | <span class="pill pill-pm">Pattern Matching</span> |
| **Post-ablation with new PVC** | 判斷是否新 morphology | <span class="pill pill-apb">Auto Pattern Bank</span> |
| **Redo / multiple PVC** | 分類 morphology | <span class="pill pill-apb">Auto Pattern Bank</span> |

Note:
這張表是 operator 的「儀錶板」 — 不管 case 走到哪一步，看這張表就知道該開哪個模組。

---

## 四個模組角色一覽

<img src="assets/diagrams/module-quadrant.svg" alt="Four CARTO modules quadrant" />

---

## 四個模組的時間軸視覺化

<div class="cols">
<div>

### <span class="pill pill-pm">Pattern Matching</span>
**全程開啟** · 從 baseline 到 post-ablation 一路用

### <span class="pill pill-apb">Auto Pattern Bank</span>
**頭尾各一次** · Baseline 分類、術後驗證

</div>
<div>

### <span class="pill pill-lat">LAT Hybrid</span>
**Mid-case 主力** · Target 鎖定後到 RF 前

### <span class="pill pill-paso">PASO</span>
**穿插使用** · Sparse PVC / pre-ablation confirm

</div>
</div>

<div class="callout">
<span class="label">Operator 直覺</span>
四個模組不是「擇一使用」，而是<strong>「各司其職、貫穿全 case」</strong>。
</div>

---

## 🎯 一句話總結

<div class="callout red">
<span class="label">記憶口訣</span>
<strong>Baseline 用 APB 分類，全程用 Pattern Matching 過濾，<br/>
Mid-case 用 LAT 找最早，PASO 確認像不像，<br/>
RF 前最後 LAT + PASO 雙確認，<br/>
RF 後用 Pattern Matching + APB 驗證消失。</strong>
</div>
