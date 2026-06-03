<!-- .slide: class="section-title" -->

<div class="part-no">PART I · 01</div>

# VPC Origin 三步驟

<div class="subtitle">不死記解剖，用心電向量定位</div>

Note:
三個簡單的向量步驟（分左右、判上下、定前後）就能在進 lab 前大致定位 origin，決定 setup 策略。

---

## Step 1 · 分左右 — 看 V1

<div class="cols image-text">
<div>

### LBBB pattern
主要向下，QS 或 rS → 源自 **右心室 (RV)**

<div class="callout">
訊號從右心室發出，朝向左心室（遠離 V1）→ 負向波。
</div>

</div>
<div>

<img src="assets/ecg/Left_bundle_branch_block_ECG_characteristics.svg" alt="LBBB pattern V1 vs V6" class="no-shadow" style="background:#fff;padding:8px;" />
<span class="fig-cap">LBBB pattern · V1 rS, V6 R</span>

</div>
</div>

<div class="cols image-text">
<div>

### RBBB pattern
主要向上，單峰 R 或 rsR' → 源自 **左心室 (LV)**

<div class="callout red">
訊號從左心室發出，往右前方（朝向 V1）→ 正向波。
</div>

</div>
<div>

<img src="assets/ecg/Right_bundle_branch_block_ECG_characteristics.svg" alt="RBBB pattern V1 vs V6" class="no-shadow" style="background:#fff;padding:8px;" />
<span class="fig-cap">RBBB pattern · V1 rsR'</span>

</div>
</div>

---

## Step 2 · 判上下 — 看下壁導程 II / III / aVF

<div class="cols image-wide">
<div>

### Inferior Axis（下壁全正）
源自 **上方流出道 (OT)**
訊號由上往下跑 → 朝向下壁導程 → 正向波

### Superior Axis（下壁全負）
源自 **下方心尖 / 下壁**
訊號由下往上跑 → 遠離下壁導程 → 負向波

</div>
<div>

<img src="assets/diagrams/vpc-origin-3steps.svg" alt="Step 2 axis interpretation" />

</div>
</div>

Note:
下壁導程的 axis 直接告訴你 origin 在上方流出道結構還是下方 apex / inferior wall。

---

## Step 3 · OT 細分 — Transition Zone

<div class="cols image-wide">
<div>

### Transition Zone 是什麼？
胸前導程 QRS 從負向轉正向的交界導程，**R/S ≈ 1** 的位置。

| 移行帶 | 位置 |
| --- | --- |
| **Normal** | V3 / V4 |
| **Early**（逆時針旋轉） | V1 / V2 |
| **Late**（順時針旋轉） | V5 / V6 |

</div>
<div>

<img src="assets/ecg/transition-zone-progression.png" alt="Transition zone V1-V6 progression: Normal / Early / Late" />

</div>
</div>

Note:
正常人 transition 落在 V3-V4，這是 R wave progression 的「平衡點」。

---

## Step 3 · 早移行 vs 晚移行 → LVOT vs RVOT

<div class="cols">
<div>

### 早移行 → LVOT / Aortic cusp
- Transition 在 **V1 / V2**
- LVOT / cusp 偏後方、偏左側、較深
- 電流朝前胸 → R 波早變大

<div class="callout orange">
越早轉正，越要懷疑 <strong>左側流出道</strong>。
</div>

</div>
<div>

### 晚移行 → RVOT
- Transition 在 **V4 / V5**
- RVOT 偏前方、偏右側
- 電流往後 → S 波較深較久

<div class="callout red">
越晚轉正，越要懷疑 <strong>右室流出道</strong>。
</div>

</div>
</div>

---

## Step 3 · 關鍵：與 Sinus Rhythm 比較

<div class="callout gold">
<span class="label">⚠️ 實戰最重要的一點</span>
不要只看 VPC transition 的絕對位置 — 要對照<strong>病人自己 sinus rhythm 的 transition</strong>。
</div>

<div class="cols">
<div>

### 為什麼
- 有些人天生就早 / 晚 transition
- 貼片位置 / 心臟旋轉 / 體型 都會影響
- 絕對位置會誤導你

</div>
<div>

### 怎麼判斷
- VPC transition **比 sinus 早** → LVOT / cusp
- VPC transition **比 sinus 晚** → RVOT
- 這個相對關係才精準

</div>
</div>

Note:
這是教科書不太強調但 lab 裡最實用的判讀方式 — 永遠跟病人自己的 sinus rhythm 比較。

---

## Step 3 · Lead I 細分 Septal vs Free wall

| Lead I 極性 | 位置 | 為什麼 |
| --- | --- | --- |
| **Lead I 正向** | **Septal**（隔膜側） | 右 → 左 朝向 Lead I |
| **Lead I 負向 / QS** | **Free wall**（游離壁） | 外側 → 內側 遠離 Lead I |

<div class="callout">
Septal site 通常 ablation 較安全有效；free wall 要小心 perforation 與 catheter contact。
</div>

---

## 三步驟視覺化總覽

<img src="assets/diagrams/vpc-origin-3steps.svg" alt="VPC origin 3-step localization full overview" />

---

## 快速總結複習表

| 步驟 | 觀察導程 | 判讀結果 |
| --- | --- | --- |
| **1. 左右** | **V1** | 向下 (LBBB) → **RV** <br/> 向上 (RBBB) → **LV** |
| **2. 上下** | **II, III, aVF** | 全正 → **上方 OT** <br/> 全負 → **下方 apex / 下壁** |
| **3. OT 細分** | **V1–V4 Transition** | 早 (V1–V2) → **LVOT / cusp** <br/> 晚 (V4+) → **RVOT** <br/>＋ Lead I 判 septal / free wall |

口訣：**V1 判左右 → 下壁判上下 → Transition + Lead I 定 OT 來源**，並一律對照 sinus rhythm 的 transition。
