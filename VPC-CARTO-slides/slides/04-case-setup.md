<!-- .slide: class="section-title" -->

<div class="part-no">PART II · 04</div>

# CARTO 3 Case Setup

<div class="subtitle">系統設定、Catheter 配置、各 origin 注意事項</div>

Note:
這是 Workflow Part 2。Case setup 沒做好，後面 mapping 都會出問題。

---

## 建立 CARTO Case · 系統設定重點

| 設定項目 | 建議 |
| --- | --- |
| Study type | **VT / PVC ablation** |
| Mapping chamber | RV / LV / Aortic root / CS 依 case 決定 |
| Reference | 穩定 intracardiac reference，常用 **RV catheter** 或 **CS catheter** |
| Surface ECG | **12-lead 一定要品質好** |
| Respiration / patient movement | 盡量穩定，避免 map shift |
| Filter setting | 確保 ventricular EGM 和 unipolar 訊號清楚 |

Note:
品質好的 12-lead 是 Pattern Matching 與 PASO 都要用的；先確認貼片位置、皮膚阻抗、訊號乾淨度。

---

## Catheter Setup · 常見配置

| Catheter | 目的 |
| --- | --- |
| **Decapolar CS catheter** | reference、LA/LV timing reference、CS/GCV access clue |
| **Ablation catheter** | mapping + ablation |
| **ICE** | LVOT、papillary muscle、valve、cusp、contact、安全監測 |
| **RV catheter** | pacing、reference、誘發 |

Note:
ICE 在 papillary muscle / LVOT case 幾乎是必備；如果懷疑 LV summit，CS catheter 一定要進。

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
