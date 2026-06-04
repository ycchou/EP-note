<!-- .slide: class="section-title" -->

<div class="part-no">PART II · 03b</div>

# 備機與物資準備

<div class="subtitle">VGH-TP 戰術級 SOP · 從 lab 外就開始決定 case 順不順</div>

Note:
這一章是 VGH-TP Jason 簡報 Step 1 的核心 — pre-case 不是只有看 12-lead，還包含主治醫師習慣、研究案、備機物資、cable 配置等實戰細節。

---

## 備機前確認 · 不只看 EKG

<div class="workflow-grid">
<div class="workflow-step">
<div class="num">1</div>
<div class="title">導管室</div>
<div class="desc">確認 lab 安排、設備可用、有沒有撞時段</div>
</div>
<div class="workflow-step">
<div class="num">2</div>
<div class="title">主診斷</div>
<div class="desc">AF / VPC / PSVT / VT — 決定 mapping 策略</div>
</div>
<div class="workflow-step">
<div class="num">3</div>
<div class="title">主治醫師</div>
<div class="desc">手術習慣、常用導管類型、偏好的 setup</div>
</div>
<div class="workflow-step">
<div class="num">4</div>
<div class="title">術式</div>
<div class="desc">導管與 ablation 機器（RF / Cryo / PFA）</div>
</div>
<div class="workflow-step">
<div class="num">5</div>
<div class="title">是否研究案</div>
<div class="desc">IIS · CL · DE — 影響 documentation 與耗材</div>
</div>
</div>

<div class="callout orange">
<span class="label">Trainer Tip</span>
這 5 項在主治醫師到 lab 前就要確認完，到場才不會手忙腳亂。
</div>

Note:
不同主治醫師對 catheter 廠牌、map 順序、target 確認門檻都不一樣 — operator 要記下每位醫師的偏好。研究案分類影響耗材使用記錄與 documentation 流程。

---

## 備機物資清單 · CARTO 套設備

<div class="cols">
<div>

### 備機 (機器端)
- **PIU** — Patient Interface Unit
- **Workstation** — CARTO 主機
- **SMA + remote** — Signal Module Assembly + 遙控
- **ECG** — 12-lead recording
- **Patch** — Location reference patches
- **Location pad** — 床下定位墊

</div>
<div>

### 導管端
- **Mapping catheter** — DECANAV / 其他多極
- **Ablation catheter** — THERMOCOOL ST / SF
- **CS catheter** — Decapolar reference
- **RV catheter**（如需）

### 訊號出口
- **ECG out to recording** — 接到院方 recording system

</div>
</div>

Note:
這份清單在備機前要逐項勾選。任何一項漏 → case 卡住。SMA 遙控壞了會影響 catheter 進出記錄。

---

## Cable 配置與管理

<div class="cols image-text">
<div>

### 戰術 SOP

1. 當日所需的導管放置於 **control room 外窗邊**
2. 連接 cable 至 **PIU**
3. **沒有忌諱要先接導管的 cable** 連接至 PIU
4. cable 統一掛好於 **台車上**

<div class="callout orange">
<span class="label">為什麼這樣排</span>
方便護理師<strong>套無菌套</strong>。Cable 散在地上 → 套無菌套時容易誤觸或纏住。
</div>

</div>
<div>

<img src="assets/vgh/cable-photo.png" alt="VGH cable arrangement on cart" />
<span class="fig-cap">VGH-TP cable 統一掛車邊管理</span>

</div>
</div>

Note:
這張照片是 Jason 在 VGH-TP lab 拍的實際 cable 配置。先把 PIU 端固定，cable 順序排好，無菌套套上去就不會打結。

---

## IC out 彩虹線 · PIN 配置

<div class="cols image-wide">
<div>

<img src="assets/vgh/piu-pins.png" alt="VGH PIU pin configuration with rainbow cable" />

</div>
<div>

### Pin 配置

| Pin 範圍 | 用途 |
| --- | --- |
| **Pin 1–4** | **MAP (TC)** — ablation catheter |
| **Pin 21–30** | **20pA (DECA)** — DECANAV 多極 |

<div class="callout red">
<span class="label">⚠️ 不要插錯</span>
PIN 插錯 → reference channel 訊號漂、LAT timing 不準、Pattern Matching template 抓不到。先核對顏色與 PIN 號再插。
</div>

</div>
</div>

Note:
VGH-TP 採彩虹色 cable 對應 PIU PIN，可以一眼看出哪根接哪。常見錯誤：MAP/DECA 對調 → mapping map 顏色錯。
