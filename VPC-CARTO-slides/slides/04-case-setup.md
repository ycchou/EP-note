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

---

## CARTO Study Setup · 開新 study

<div class="cols image-wide">
<div>

### 填四件事

1. **Patient name + ID**
2. **Date of birth + Gender**
3. **Physician**（主治醫師）
4. **Select template** — Ventricular Tachycardia

</div>
<div>

<img src="assets/vgh/study-setup.png" alt="CARTO Study Setup screen" />
<span class="fig-cap">CARTO Study Setup 畫面（VGH-TP）</span>

</div>
</div>

Note:
Template 選 Ventricular Tachycardia 是 VPC ablation 的標準起點 — 自帶適當 chamber/filter 預設值。Physician 欄位要填，研究案 documentation 才能撈得到。

---

## Catheter Setup · DECANAV + THERMOCOOL

<div class="cols image-wide">
<div>

### 標準組合
- **DECANAV** — 多極 mapping catheter
- **THERMOCOOL** — ablation catheter（ST / SF）

### 注意
- 兩根都要在 Catheter Setup 畫面被正確辨識
- 確認 PIU PIN 配置與畫面顯示一致
- Catheter color 在 3D map 上對應

</div>
<div>

<img src="assets/vgh/catheter-setup.png" alt="CARTO Catheter Setup screen with DECANAV and THERMOCOOL" />
<span class="fig-cap">Catheter Setup · DECANAV + THERMOCOOL（VGH-TP）</span>

</div>
</div>

Note:
DECANAV 在 RVOT mapping 是主力 — 一根 catheter 同時看 10 個極可大幅縮短 FAM 時間。THERMOCOOL ST 有 force sensor，contact 不穩會即時提醒。

---

## Map Setup · 預先建好幾個 Map

<div class="cols image-wide">
<div>

### Map List 預先建立

- **1-RVOT SR** — 用於 sinus rhythm map
- **2-RVOT A** — RVOT activation map
- **3-CS A** — CS activation map
- **4-CUSP A** — Aortic cusp activation map
- **5-RVOT B** — 備用

### Map Setup 必選

| 項目 | 設定值 |
| --- | --- |
| Chamber | **Ventricular** |
| 勾選 | **LAT hybrid** ✓ |
| Reference | **BS V1–V6 Automatic** |
| WOI | **–180 to –20** |

</div>
<div>

<img src="assets/vgh/map-setup.png" alt="CARTO Map Setup with WOI and LAT hybrid checked" />
<span class="fig-cap">Map Setup · LAT hybrid 勾選 + WOI –180 to –20</span>

</div>
</div>

Note:
**先建好 5 個 Map** 是 VGH-TP 戰術 — case 一開始就把可能用到的 chamber 都建出來，省得 mapping 中再切換。**WOI –180 to –20** 是 VPC mapping 的標準視窗，涵蓋預期 earliest activation 範圍。

---

## Mapping 頁面 · Layout + Parallel Mapping

<div class="cols">
<div>

### 畫面配置

- **主畫面：左邊**（active map 即時操作）
- **副畫面：右邊**（reference map 對照）

### Parallel Mapping

將預先設定好的 Map（RVOT SR、RVOT A、CS A、CUSP A…）打開 parallel mapping。

</div>
<div>

<div class="callout orange">
<span class="label">為什麼要 parallel</span>
- 同一個 case 多 chamber 比較 timing
- LV summit case：RVOT vs LVOT vs cusp vs CS 並列看
- Sinus rhythm 與 PVC map 一鍵切換對照
</div>

</div>
</div>

Note:
Parallel mapping 是 LV summit / 複雜 origin case 的關鍵 — 一個畫面同時看四個 chamber 的 earliest，origin 在哪一個 chamber 一目了然。VGH-TP 預設 layout 就是「左主右副」，operator 翻 case 時不用重新調畫面。
