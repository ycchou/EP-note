<!-- .slide: class="section-title" -->

<div class="part-no">PART I · 01</div>

# 12-Lead ECG · 向量基礎

<div class="subtitle">ECG 不是死背 — 是「方向感」<br/>看 12 個 lead 各自的角度，就能反推電氣訊號從哪冒出來</div>

Note:
這一章是 VPC origin localization 的基礎。理解每個 lead 看心臟的「角度」之後，後面三步驟（V1 判左右、下壁判上下、Transition 定 OT）就會變成直覺。

---

## 12 個 Lead = 12 個攝影機角度

<div class="cols image-wide">
<div>

### 6 個 limb leads（額狀面 / 上下左右）
- **I, II, III** — 三個雙極導程（兩個電極）
- **aVR, aVL, aVF** — 三個 augmented 單極導程

### 6 個 precordial leads（水平面 / 前後內外）
- **V1, V2** 靠近右前胸
- **V3, V4** 前胸中間
- **V5, V6** 左側胸壁

每個 lead 都從固定角度「看」心臟的電氣活動。

</div>
<div>

<img src="assets/ecg/anatomy-274af716.png" alt="12-lead ECG electrode placement diagram" />
<span class="fig-cap">12-lead ECG 電極位置 · 6 個肢體 + 6 個胸前</span>

</div>
</div>

Note:
6 + 6 = 12 個 lead。把每個 lead 想成一台攝影機，從不同角度看同一顆心臟，組合起來就能立體推斷電氣方向。

---

## Einthoven's Triangle · 三個肢體導程的根基

<img src="assets/diagrams/einthovens-triangle.svg" alt="Einthoven's Triangle: RA / LA / LL with Lead I/II/III vectors" class="svg-fit" />

Note:
1903 年 Willem Einthoven 設計的肢體導程系統：在右手、左手、左腳三個位置貼電極，形成等邊三角形。Lead I = LA - RA、Lead II = LL - RA、Lead III = LL - LA。Einthoven's Law：Lead I + Lead III = Lead II（向量加法）。

---

## Hexaxial Reference · 六軸參考（加入 aVR / aVL / aVF）

<img src="assets/diagrams/hexaxial-reference.svg" alt="Hexaxial reference circle showing 6 limb leads at 30 degree intervals" class="svg-fit" />

Note:
把 Einthoven 三角的三條邊「平移」到心臟中心，再加入 augmented leads（aVR/aVL/aVF），就形成 6 個方向、每 30° 一個的參考軸。每個導程的「正向 = 電氣訊號朝這個方向」。這是判讀 axis（軸向）的基礎。下壁 II/III/aVF 都指向下方，所以只要這三個 lead 正向 → origin 一定在心臟上方（OT）。

---

## Precordial Leads · 水平面的 V1–V6

<img src="assets/diagrams/precordial-leads.svg" alt="V1 to V6 chest electrode positions horizontal plane" class="svg-fit" />

Note:
胸前導程在水平面上沿著前胸到左側胸壁排成一弧線：V1/V2 在右前胸看 RVOT 最清楚；V5/V6 在左側看 LV 最清楚；V3/V4 在中間就是 transition zone 出現的位置。下一章 VPC origin 三步驟，會直接運用這些 lead 的方向觀念。

