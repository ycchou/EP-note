<!-- .slide: class="section-title" -->

<div class="part-no">PART I · 02</div>

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

<img src="assets/diagrams/step2-axis.svg" alt="Step 2 axis interpretation: inferior vs superior" class="svg-fit" />

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

<img src="assets/diagrams/sinus-vs-vpc-transition.svg" alt="Sinus rhythm vs VPC transition zone comparison" class="svg-fit" />

Note:
這是教科書不太強調但 lab 裡最實用的判讀方式 — 永遠跟病人自己的 sinus rhythm 比較。圖中病人 sinus 在 V4 才轉正（稍偏晚），同一病人的 VPC 在 V3 就轉正 → VPC 比 sinus 早 1 個導程 → 偏 LVOT / cusp。

---

## Step 3 · Lead I 細分 Septal vs Free wall

<div class="lead1-grid">

<div class="lead1-card septal">
  <span class="badge">Septal Origin</span>
  <h3>Lead I 正向 R 波</h3>

  <div class="waveform">
    <svg viewBox="0 0 220 80" xmlns="http://www.w3.org/2000/svg">
      <line x1="0" y1="48" x2="220" y2="48" stroke="#3A4A5C" stroke-width="0.6"/>
      <path d="M0,48 L65,48 L72,46 L78,8 L86,68 L94,48 L220,48"
            fill="none" stroke="#F39200" stroke-width="2.5" stroke-linejoin="round"/>
      <text x="10" y="20" fill="#F39200" font-size="11" font-weight="700"
            font-family="Inter, sans-serif">Lead I</text>
    </svg>
    <div class="wave-label">主要向上 (Tall R wave)</div>
  </div>

  <div class="vec-line"><strong>向量方向</strong> · 右 → 左（朝向 Lead I）</div>

  <div class="reason">
    Septal site 位於 IV septum，VPC 由右向左傳導 → 與 Lead I 方向相同 → 正向波。<br/>
    Ablation 通常較安全有效。
  </div>
</div>

<div class="lead1-card freewall">
  <span class="badge">Free Wall Origin</span>
  <h3>Lead I 負向 / QS 波</h3>

  <div class="waveform">
    <svg viewBox="0 0 220 80" xmlns="http://www.w3.org/2000/svg">
      <line x1="0" y1="32" x2="220" y2="32" stroke="#3A4A5C" stroke-width="0.6"/>
      <path d="M0,32 L65,32 L72,34 L80,72 L92,32 L220,32"
            fill="none" stroke="#FB7185" stroke-width="2.5" stroke-linejoin="round"/>
      <text x="10" y="20" fill="#FB7185" font-size="11" font-weight="700"
            font-family="Inter, sans-serif">Lead I</text>
    </svg>
    <div class="wave-label">主要向下 (QS / negative)</div>
  </div>

  <div class="vec-line"><strong>向量方向</strong> · 外側 → 內側（遠離 Lead I）</div>

  <div class="reason">
    Free wall 位於 LV 外緣，VPC 由外向內傳導 → 與 Lead I 方向相反 → 負向波。<br/>
    要小心 perforation、catheter contact 與 LV thrombus。
  </div>
</div>

</div>

Note:
新版用直接的 ECG 波形比較取代心臟剖面圖 — operator 看到的就是 lab 螢幕上實際長相。Septal site 對應 tall R wave，free wall 對應 QS。

---

## 三步驟視覺化總覽

<img src="assets/diagrams/vpc-origin-3steps.svg" alt="VPC origin 3-step localization full overview" class="svg-fit" />
