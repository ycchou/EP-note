<!-- .slide: class="section-title" -->

<div class="part-no">PART II · 04</div>

# CARTO 3 Case Setup

<div class="subtitle">系統設定、Catheter 配置、各 origin 注意事項</div>

Note:
這是 Workflow Part 2。Case setup 沒做好，後面 mapping 都會出問題。

---

## 建立 CARTO Case · 系統設定重點

<div class="cols image-wide">
<div>

| 設定項目 | 建議 |
| --- | --- |
| Study type | **VT / PVC ablation** |
| Mapping chamber | RV / LV / Aortic root / CS |
| Reference | 穩定 intracardiac · 常用 RV / CS |
| Surface ECG | **12-lead 一定要品質好** |
| Respiration | 穩定避免 map shift |
| Filter | 確保 ventricular EGM 清楚 |

</div>
<div>

<img src="assets/carto/location-setup-patches.png" alt="CARTO Location Setup · patch placement" />
<span class="fig-cap">CARTO Location Setup · Chest / Back patch placement (CARTO 3 IFU)</span>

</div>
</div>

Note:
品質好的 12-lead 是 Pattern Matching 與 PASO 都要用的；先確認貼片位置、皮膚阻抗、訊號乾淨度。patch 位置不對會導致 Location accuracy zone 變差。

---

## Catheter Setup · 常見配置

<div class="cols image-wide">
<div>

| Catheter | 目的 |
| --- | --- |
| **Decapolar CS** | reference、LA/LV timing、CS/GCV access |
| **Ablation** | mapping + ablation |
| **ICE** | LVOT、papillary、valve、cusp、contact |
| **RV catheter** | pacing、reference、誘發 |

</div>
<div>

<img src="assets/carto/catheter-ports.png" alt="CARTO 3 PIU catheter connector ports" />
<span class="fig-cap">CARTO 3 PIU connector ports · MAP / REF / QUAD / 20-pole / ULTRASOUND / ECG</span>

</div>
</div>

Note:
ICE 在 papillary muscle / LVOT case 幾乎是必備；如果懷疑 LV summit，CS catheter 一定要進。PIU 的接孔不要插錯，會影響 reference channel。

---

## 各 Suspected origin · 注意事項

| Suspected origin | 需要注意 |
| --- | --- |
| **RVOT** | RVOT anatomy map |
| **LVOT / cusp** | aortic root / LVOT map |
| **LV summit** | CS、GCV、AIV map，必要時 coronary angiography |
| **Para-Hisian** | His annotation、低功率、小心 AV block |
| **Papillary muscle** | ICE 幾乎很重要 |
| **Fascicular** | Purkinje potential mapping 很重要 |

---

## 🎯 Setup 的核心邏輯

<div class="callout red">
<span class="label">Operator 思維</span>
Setup 階段的每個決定都來自 <strong>pre-case 預判的 origin</strong>。
預判越準 → setup 越精準 → mapping 越省時間。
</div>

Note:
這就是為什麼前一張的 12-lead 預判很關鍵 — 它決定了 setup 階段所有 catheter 選擇。
