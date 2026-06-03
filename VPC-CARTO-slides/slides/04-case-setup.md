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

<!-- .slide: class="v-center" -->

## 預判 origin 之後 · Setup 要準備什麼？

| 預判 origin | Chamber / Anatomy | 額外 catheter | 安全注意 |
| --- | --- | --- | --- |
| **RVOT** | RV + RVOT + pulmonary valve | — | RVOT free wall 薄 |
| **LVOT / Aortic cusp** | LV + LVOT + aortic root | ICE 建議 | 確認 coronary ostia 距離 |
| **LV summit** | LVOT + cusp + CS + GCV + AIV | **CS catheter 必進**、ICE | LAD / LCX 距離、必要時 coronary angio |
| **Para-Hisian** | RA septum + RV septum + His + NCC | — | His annotation、低功率、AV block 警戒 |
| **Papillary muscle** | LV chamber | **ICE 必備** | Papillary 跳動、contact force 支援 |
| **Fascicular** | LV septum + Purkinje area | — | Purkinje potential 標記 |

<div class="callout orange">
<span class="label">怎麼讀這張表</span>
從左到右一列就是一個 case 的 setup checklist：先決定要建哪些 chamber，再決定要不要加 ICE / CS catheter，最後標出 ablation 安全考量。預判越準 → 越省時間。
</div>

Note:
Setup 階段的每個決定都來自 pre-case 預判的 origin。LV summit 是最複雜的 — 4 個 chamber + CS + ICE + coronary 距離全部要顧。
