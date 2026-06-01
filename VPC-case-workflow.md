可以。下面我用 **CARTO 3 system 的角度**，把 **VPC/PVC ablation workflow** 寫成一套「臨床可直接照著跑」的流程，並特別標出：

* **什麼時間點用什麼模組**
* **為什麼要用**
* **Pattern Matching / Auto Pattern Bank / LAT Hybrid / PASO 各自角色**
* **VPC 很少、很多、型態多、誘發困難時怎麼調整**

***

# 一句話總結

**VPC ablation 在 CARTO 3 的核心 workflow 是：先用 Pattern Matching / Auto Pattern Bank 把目標 VPC 型態鎖定，再用 LAT Hybrid 建 activation map 找 earliest site，最後用 PASO 做 pace mapping 確認出口與相似度，必要時回頭修正 target morphology。**

***

# VPC Ablation with CARTO 3：完整 Workflow

## Overall workflow map

```text
1. Pre-case preparation
   ↓
2. Patient setup + CARTO patch / catheter setup
   ↓
3. Baseline rhythm assessment
   ↓
4. 建立目標 VPC morphology
      → Pattern Matching
      → Auto Pattern Bank
   ↓
5. Anatomy map
      → RA/RV/LV/OT/Aortic cusp/CS 視懷疑 origin 決定
   ↓
6. Activation mapping
      → LAT Hybrid
      → 找 earliest ventricular activation
   ↓
7. Pace mapping
      → PASO
      → 確認 pace map similarity
   ↓
8. RF ablation
      → earliest + good unipolar + good PASO + anatomy safe zone
   ↓
9. Post-ablation validation
      → spontaneous VPC elimination
      → isoproterenol / burst pacing / waiting period
   ↓
10. Final documentation
```

***

# Part 1：Pre-case Preparation 術前準備

## 1. 先從 12-lead EKG 預判 origin

進 lab 前先看 VPC morphology：

| 12-lead finding                                    | 可能 origin                                   |
| -------------------------------------------------- | ------------------------------------------- |
| LBBB + inferior axis + late transition             | RVOT                                        |
| LBBB/inferior + early transition                   | LVOT / aortic cusp                          |
| Inferior axis + lead I negative + early transition | LV summit / LCC                             |
| RBBB + superior axis                               | LV inferior / fascicular / papillary muscle |
| LBBB + superior axis                               | RV apex / inferior RV                       |
| Narrow septal PVC                                  | Para-Hisian                                 |

這一步的目的不是要 100% 定位，而是決定：

1. 要不要進 LV
2. 要不要 map RVOT
3. 要不要準備 aortic cusp
4. 要不要 CS / GCV / AIV
5. ablation 風險在哪裡，例如 His、coronary artery、valve、papillary muscle

***

# Part 2：CARTO 3 Case Setup

## 2. 建立 CARTO case

### 系統設定重點

| 設定項目                           | 建議                                                     |
| ------------------------------ | ------------------------------------------------------ |
| Study type                     | VT / PVC ablation                                      |
| Mapping chamber                | RV / LV / Aortic root / CS 依 case 決定                   |
| Reference                      | 穩定 intracardiac reference，常用 RV catheter 或 CS catheter |
| Surface ECG                    | 12-lead 一定要品質好                                         |
| Respiration / patient movement | 盡量穩定，避免 map shift                                      |
| Filter setting                 | 確保 ventricular EGM 和 unipolar 訊號清楚                     |

***

## 3. Catheter setup

常見配置：

| Catheter              | 目的                                                  |
| --------------------- | --------------------------------------------------- |
| Decapolar CS catheter | reference、LA/LV timing reference、CS/GCV access clue |
| Ablation catheter     | mapping + ablation                                  |
| ICE                   | LVOT、papillary muscle、valve、cusp、contact、安全監測       |
| RV catheter           | pacing、reference、誘發                                 |

若懷疑：

| Suspected origin | 需要注意                                    |
| ---------------- | --------------------------------------- |
| RVOT             | RVOT anatomy map                        |
| LVOT / cusp      | aortic root / LVOT map                  |
| LV summit        | CS、GCV、AIV map，必要時 coronary angiography |
| Para-Hisian      | His annotation、低功率、小心 AV block          |
| Papillary muscle | ICE 幾乎很重要                               |
| Fascicular       | Purkinje potential mapping 很重要          |

***

# Part 3：Baseline Rhythm Assessment

## 4. 先觀察 VPC 頻率與型態

進入 CARTO 前，先回答四個問題：

```text
1. VPC 是 frequent 還是 infrequent？
2. 是 monomorphic 還是 multiple morphology？
3. clinical VPC 跟術前 ECG 是否一樣？
4. VPC 是否受麻醉、sedation、isoproterenol 影響？
```

***

## VPC frequency 決定 mapping strategy

| VPC 狀況             | Strategy                                    |
| ------------------ | ------------------------------------------- |
| 很頻繁                | Activation mapping 為主                       |
| 偶發                 | Pattern matching 輔助收集，PASO 重要               |
| 幾乎不出現              | Pace mapping + induction                    |
| 多型態                | Auto Pattern Bank 先分類，再選 clinical target    |
| bigeminy/trigeminy | Activation map 很好做，但要注意 annotation accuracy |

***

# Part 4：建立目標 VPC morphology

這裡開始進入你問的重點。

***

# 5. Pattern Matching：什麼時候用？

## 使用時間點

**一開始 baseline recording 就要開。**

尤其在以下情況非常重要：

| 情境                                 | 是否需要 Pattern Matching |
| ---------------------------------- | --------------------- |
| 多種 VPC morphology                  | 非常需要                  |
| VPC 不頻繁                            | 需要                    |
| VPC 會被 sinus beat / fusion beat 干擾 | 需要                    |
| ablation 後確認是否同一顆 VPC 消失           | 需要                    |
| activation map 收點時避免收錯 morphology  | 非常需要                  |

***

## Pattern Matching 的目的

**Pattern Matching 是用 surface ECG morphology 來辨認「現在這一拍是不是我們要打的 clinical VPC」。**

它不是定位工具，而是：

```text
確保你 map 的每一個點，都是同一種 VPC。
```

***

## 操作概念

1. 找到一個清楚的 clinical VPC
2. 用 12-lead ECG 建立 template
3. 系統之後會判斷後續 VPC 與 template 的相似度
4. 相似度高的拍子才納入 activation mapping
5. morphology 不同的 VPC 要排除或另外分類

***

## 臨床重點

如果沒有 Pattern Matching，VPC ablation 很容易發生：

```text
你以為你在 map 同一顆 VPC，
其實中間混進不同 origin 的 VPC，
最後 LAT map 會變亂。
```

***

# 6. Auto Pattern Bank：什麼時候用？

## 使用時間點

**在 baseline rhythm assessment 或 mapping 初期就開。**

尤其適合：

| 情境                          | 使用 Auto Pattern Bank |
| --------------------------- | -------------------- |
| 病人有 multiple PVC morphology | 必用                   |
| 不確定 clinical PVC 是哪一個       | 很有用                  |
| VPC burden 高但型態混雜           | 很有用                  |
| ablation 後出現新 morphology    | 用來分辨是不是新 VPC         |
| redo case                   | 幫助整理不同 morphology    |

***

## Auto Pattern Bank 的角色

**Auto Pattern Bank 會自動把不同 morphology 的 VPC 分類成不同 pattern。**

你可以把它想成：

```text
自動幫你把 VPC 分成 A型、B型、C型。
```

例如：

| Pattern   | Surface ECG        | 可能意義                     |
| --------- | ------------------ | ------------------------ |
| Pattern 1 | LBBB/inferior axis | RVOT VPC                 |
| Pattern 2 | RBBB/superior axis | LV inferior VPC          |
| Pattern 3 | LBBB/normal axis   | para-Hisian or RV septal |

***

## Auto Pattern Bank vs Pattern Matching

| 功能                | 主要用途                            |
| ----------------- | ------------------------------- |
| Pattern Matching  | 判斷某一拍是否符合你指定的 target morphology |
| Auto Pattern Bank | 自動分類多種 VPC morphology           |

***

## 實戰用法

### Step A：先讓 Auto Pattern Bank 收集

病人進 lab 後，先觀察幾分鐘。

```text
讓系統自動記錄 PVC morphology。
```

### Step B：選 clinical VPC

依照：

1. 術前 12-lead ECG
2. Holter dominant morphology
3. 病人症狀發生時的 VPC
4. lab 中最常出現的 morphology

決定要打哪一顆。

### Step C：把 clinical VPC 設成 target

選定後，用 Pattern Matching 鎖定這個 morphology。

***

# Part 5：建立 Anatomy Map

## 7. 什麼時候建立 anatomy？

通常在 morphology target 設好後，就開始建立 anatomy。

但實務上順序可依 VPC 頻率調整：

| VPC 頻率 | 建議                                   |
| ------ | ------------------------------------ |
| 很頻繁    | 可以一邊 anatomy 一邊 activation map       |
| 偶發     | 先快速建立相關 chamber anatomy，再等 VPC 收 LAT |
| 很少出現   | 先完整 anatomy + PASO pace map          |

***

## 根據懷疑 origin 決定 map 哪裡

| EKG 懷疑           | CARTO anatomy                      |
| ---------------- | ---------------------------------- |
| RVOT             | RV、RVOT、pulmonary valve            |
| LVOT             | LV、LVOT、aortic root                |
| Aortic cusp      | RCC、LCC、NCC、commissure             |
| LV summit        | LVOT、aortic cusp、CS、GCV、AIV        |
| Fascicular       | LV septum、Purkinje area            |
| Papillary muscle | LV chamber + ICE geometry          |
| Para-Hisian      | RA septum、RV septum、His region、NCC |

***

# Part 6：Activation Mapping with LAT Hybrid

***

# 8. LAT Hybrid：什麼時候用？

## 使用時間點

**當你已經鎖定 target VPC morphology 後，開始做 activation map 時使用。**

也就是：

```text
Pattern Matching / Auto Pattern Bank 確認目標 VPC
↓
開始收 activation points
↓
使用 LAT Hybrid
```

***

## LAT Hybrid 的目的

**LAT Hybrid 是用來建立 VPC 的 local activation time map，找出最早的 ventricular activation site。**

簡單說：

```text
誰最早 depolarize，誰最可能靠近 VPC origin。
```

***

## Activation mapping 的核心設定

### Reference annotation

你需要選定一個穩定 reference，常見方式：

| Reference              | 說明                        |
| ---------------------- | ------------------------- |
| Surface ECG QRS onset  | 常用於 PVC activation timing |
| Intracardiac reference | 若穩定，可輔助                   |
| CS / RV catheter       | 需確認每拍穩定                   |

VPC map 常見是以：

```text
PVC QRS onset = time zero
```

然後找 local EGM 比 QRS onset 早多少 ms。

***

## 最重要的數字

| Finding                              | 意義                                |
| ------------------------------------ | --------------------------------- |
| local bipolar EGM 提前 QRS onset 20 ms | 可能接近                              |
| 提前 30 ms                             | 很有意義                              |
| 提前 40 ms 以上                          | 非常可疑 origin                       |
| unipolar QS pattern                  | 支持 focal origin 附近                |
| local EGM sharp prepotential         | fascicular/Purkinje 或特殊 substrate |

***

## LAT Hybrid 操作邏輯

### Step 1：只收 target VPC

用 Pattern Matching 過濾，避免混入不同 VPC morphology。

```text
只接受與 target template 高度相似的 PVC beats。
```

### Step 2：檢查每個點 annotation

CARTO 自動 annotation 很方便，但 VPC mapping 不能完全盲信。

每個重要 early point 要看：

```text
1. bipolar EGM onset
2. unipolar morphology
3. 是否為 far-field
4. catheter contact
5. 是否同一種 VPC
6. beat 是否 fusion
```

***

### Step 3：找 earliest activation

在 LAT map 上尋找最早區域：

```text
紅色 / earliest color zone
```

但不要只看顏色，要看訊號。

真正好的 target 通常有：

| 條件               | 理想表現                    |
| ---------------- | ----------------------- |
| Bipolar timing   | earliest，常 -20 到 -40 ms |
| Unipolar         | QS pattern，快速下降         |
| Contact          | 穩定                      |
| Pattern matching | 高相似度                    |
| Pace map         | PASO 高分                 |
| Anatomy          | 合理且安全                   |

***

# 9. LAT Hybrid 的實戰判讀

## Good activation target 長怎樣？

```text
PVC morphology = target VPC
Local bipolar EGM = earliest
Local timing = -35 ms before QRS onset
Unipolar = QS with steep initial negative deflection
PASO = 92%
Anatomy = RVOT septal site
```

這就是很漂亮的 ablation target。

***

## Bad activation point 長怎樣？

```text
LAT 很早，但：
- beat morphology 不像 target PVC
- EGM 很鈍，像 far-field
- catheter contact 不穩
- unipolar 不是 QS
- 點位孤立，周圍沒有 early zone
```

這種不要急著燒，先確認。

***

# Part 7：Pace Mapping with PASO

***

# 10. PASO：什麼時候用？

## 使用時間點

PASO 通常在以下時機使用：

| 時間點                                | PASO 角色                |
| ---------------------------------- | ---------------------- |
| VPC 很少時                            | 主力工具之一                 |
| activation map 找到 early site 後     | confirm target         |
| ablation 前                         | 確認 pace map similarity |
| 多個 early sites 差不多時                | 幫助選點                   |
| suspected exit site vs origin 不一致時 | 幫助理解 breakout          |
| ablation 後還有 PVC                   | 找殘餘或新 morphology       |

***

## PASO 是什麼？

**PASO 是 CARTO 的 pace mapping 工具，用 pacing QRS 與 clinical PVC QRS 做相似度比較。**

簡單說：

```text
在某個點 pacing，如果 paced QRS 長得很像 clinical PVC，
代表這個點接近 PVC 出口或 origin。
```

***

## PASO 高分代表什麼？

| PASO similarity | 解讀                                             |
| --------------- | ---------------------------------------------- |
| > 95%           | 非常好                                            |
| 90–95%          | 很有價值                                           |
| 85–90%          | 可接受，但需搭配 activation                            |
| < 85%           | 可能不是最佳點，或 pacing capture / output / fusion 有問題 |

但注意：

```text
PASO 高分不一定等於真正 origin。
它可能是 exit site，而不是 deep origin。
```

尤其在：

* LV summit
* intramural PVC
* papillary muscle
* fascicular PVC
* epicardial origin

會更明顯。

***

## PASO 操作步驟

### Step 1：建立 clinical PVC template

使用目標 VPC 的 12-lead morphology。

### Step 2：在疑似區域 pacing

通常 pacing output：

```text
低 output 優先，例如接近 threshold 的 2x capture threshold
```

如果 output 太高，會 capture 太大範圍，造成假性高分。

### Step 3：比較 paced QRS 與 clinical PVC

看：

1. PASO percentage
2. 每個 lead 的 morphology
3. QRS onset
4. intrinsicoid deflection
5. R/S transition
6. limb lead axis

### Step 4：標記高分區域

在 CARTO map 上標示：

```text
PASO 95%
PASO 92%
PASO 88%
```

再與 LAT early zone 疊合。

***

# 11. PASO 判讀技巧

## 最重要不是總分，而是哪些 lead 不像

例如：

```text
PASO 93%
但是 V1-V3 transition 不對
```

這代表可能左右或 anterior/posterior 位置還差一點。

***

## 常見修正方向

| Pace map 差異                 | 可能要往哪裡修正                |
| --------------------------- | ----------------------- |
| V1-V2 R 波太小                 | 可能要更左側 / 更 posterior    |
| transition 比 clinical PVC 晚 | pacing site 可能太右，要往左    |
| lead I 太正                   | site 可能太右，要往左           |
| inferior leads 不夠高          | site 可能太低，要往更 superior  |
| III 比 II 差很多                | 左右/前後方向需修正              |
| aVL/aVR 不像                  | outflow tract 左右上方位置需修正 |

***

# Part 8：把 LAT Hybrid 和 PASO 結合

這是 VPC ablation 成敗重點。

***

## 12. Activation map vs Pace map 怎麼取捨？

### 最理想 target

```text
Earliest activation + unipolar QS + PASO high score
```

這種最適合 ablation。

***

## 不同情況處理

| 情況                    | 解讀                                               | 策略                                        |
| --------------------- | ------------------------------------------------ | ----------------------------------------- |
| LAT earliest + PASO 高 | 最佳 target                                        | 優先 ablation                               |
| LAT earliest + PASO 低 | 可能 deep origin / poor pacing capture / far-field | 檢查 contact、output、鄰近結構                    |
| LAT 不夠早 + PASO 高      | 可能 exit site                                     | 可燒，但需找更早點                                 |
| 多處 PASO 高             | 可能 broad breakout / intramural                   | 需多 chamber mapping                        |
| PASO 高但 ablation 無效   | 可能不是 origin，只是 exit                              | 去 opposite side / cusp / CS / LV summit 找 |

***

# Part 9：Ablation Target Selection

## 13. 燒灼前的 target checklist

在 RF 前，建議確認：

```text
□ Target PVC morphology 已用 Pattern Matching 確認
□ 不是 fusion beat
□ LAT timing 足夠早
□ local EGM 清楚，不是 far-field
□ unipolar 呈 QS 或接近 QS
□ PASO score 夠高
□ catheter contact 穩定
□ anatomy 位置合理
□ 遠離 His / coronary artery / valve / phrenic nerve
□ 若在 cusp / summit，已考慮 coronary distance
```

***

## 14. RF ablation 一般策略

依位置不同調整。

### RVOT PVC

```text
Power: 常見 25–35 W
Goal: impedance drop、PVC suppression
注意：RVOT free wall 薄，避免過度 contact / perforation
```

### LVOT / Aortic cusp

```text
Power: 常見 20–35 W，依位置與灌流導管設定
注意：coronary ostia、aortic valve、His region
必要時 coronary angiography
```

### Para-Hisian PVC

```text
Power: low power 起始
短時間測試
密切監測 PR / AH / His potential
必要時考慮 cryo 或從 NCC ablate
```

### Papillary muscle PVC

```text
重點不是只看 power，而是 catheter stability
ICE 很重要
可能需要 contact force support
可能需要多 lesion
```

### LV summit PVC

```text
可能從：
- LCC/RCC
- LV endocardium
- RVOT
- GCV/AIV
- epicardial region

要注意 coronary artery distance。
```

***

# Part 10：Ablation During PVC

## 15. 燒灼時要觀察什麼？

### 好的反應

| Ablation response                   | 意義                    |
| ----------------------------------- | --------------------- |
| PVC acceleration then suppression   | 常見有效反應                |
| PVC 消失                              | good sign             |
| local EGM amplitude 下降              | lesion effect         |
| pace map 不再 capture 或 morphology 改變 | local tissue modified |

***

### 不好的情況

| 現象                                       | 可能問題                          |
| ---------------------------------------- | ----------------------------- |
| PVC 完全沒變                                 | target 錯或 lesion 不夠           |
| PVC morphology 改變                        | 部分 modified，或另一個 focus 出現     |
| transient suppression 後復發                | lesion depth 不夠或 intramural   |
| junctional rhythm / AV conduction change | septal/His 附近危險               |
| ST change                                | coronary issue，尤其 cusp/summit |

***

# Part 11：Post-ablation Validation

## 16. Ablation 後怎麼確認成功？

### Step 1：觀察 spontaneous PVC

```text
等待至少 20–30 分鐘
```

看 target PVC 是否消失。

***

### Step 2：誘發

可用：

| 方法                     | 目的                             |
| ---------------------- | ------------------------------ |
| Isoproterenol          | 誘發 catecholamine-sensitive PVC |
| Burst pacing           | 誘發 ventricular ectopy          |
| Programmed stimulation | 視情況                            |
| 停止 sedation 刺激         | 有些 PVC sedation 下會消失           |

***

### Step 3：用 Pattern Matching / Auto Pattern Bank 確認

這時候模組又很重要。

#### Pattern Matching

確認：

```text
原本 target VPC 是否真的沒有再出現。
```

#### Auto Pattern Bank

確認：

```text
術後出現的是不是同一 morphology？
還是新的 VPC morphology？
```

***

## 17. 術後判斷

| 術後情況                             | 解讀                                 |
| -------------------------------- | ---------------------------------- |
| target morphology 完全消失           | acute success                      |
| 原 morphology 不見，但新 morphology 出現 | 可能多 focus                          |
| 同 morphology 低頻復發                | lesion 不完整或 edema temporary effect |
| morphology 稍微改變                  | exit 改變，origin 可能仍存在               |

***

# Part 12：不同臨床情境的 CARTO workflow

***

## Scenario 1：Frequent monomorphic RVOT PVC

### Workflow

```text
1. Pattern Matching 建 target PVC template
2. Auto Pattern Bank 確認主要只有一種 morphology
3. 建 RV/RVOT anatomy
4. LAT Hybrid 收 activation points
5. 找 earliest site
6. 看 unipolar QS
7. PASO confirm
8. RF ablation
9. Pattern Matching 確認 target PVC 消失
```

### 重點

這種最適合 activation mapping。

***

## Scenario 2：Infrequent PVC

### Workflow

```text
1. Pattern Matching 建 target
2. Auto Pattern Bank 收集所有 morphology
3. 建完整 suspected chamber anatomy
4. 等 PVC 出現時用 LAT Hybrid 收點
5. 若點不夠，用 PASO 主導
6. 高 PASO 區域再等 PVC 確認 activation
7. RF
8. Isoproterenol 誘發驗證
```

### 重點

PVC 少的時候，不要硬做不完整 activation map。

```text
PASO + EKG prediction + anatomy safety
```

會變得更重要。

***

## Scenario 3：Multiple PVC morphologies

### Workflow

```text
1. Auto Pattern Bank 先分類
2. 對照術前 Holter / 12-lead 決定 clinical PVC
3. Pattern Matching 鎖定 target morphology
4. 只 map target PVC
5. Ablation 後重新看 Pattern Bank
6. 若主要 morphology 消失，再決定是否處理第二 morphology
```

### 重點

不要把不同 morphology 混在同一張 LAT map。

***

## Scenario 4：Suspected LV summit PVC

### Workflow

```text
1. Pattern Matching 鎖定 target
2. Auto Pattern Bank 確認 morphology
3. 建 LVOT / aortic cusp / RVOT / CS anatomy
4. LAT Hybrid 分別比較各 chamber earliest timing
5. PASO 比較 LCC、RCC、LV endocardium、RVOT、GCV/AIV
6. 若 CS/GCV/AIV early，要確認 coronary distance
7. 選最安全、最早、PASO 最佳位置 ablate
```

### 重點

LV summit 不要只看一個 chamber。

常常需要比較：

```text
RVOT vs LVOT vs cusp vs coronary venous system
```

***

## Scenario 5：Papillary muscle PVC

### Workflow

```text
1. Pattern Matching 確認 target PVC
2. 建 LV anatomy
3. ICE 建 papillary muscle anatomy
4. LAT Hybrid 找 earliest papillary region
5. PASO 輔助，但分數可能不穩
6. 重點看 catheter stability/contact
7. RF lesion 可能需要多點
8. 術後用 Pattern Matching 確認 morphology 消失
```

### 重點

Papillary muscle case：

```text
PASO 可能受 catheter orientation 和 capture area 影響。
ICE + contact stability 很重要。
```

***

## Scenario 6：Para-Hisian PVC

### Workflow

```text
1. Pattern Matching 鎖定 target
2. 建 RA septum / RV septum / His region / NCC anatomy
3. 標記 His potential
4. LAT Hybrid 找 earliest
5. 若 His 附近最早，務必評估 NCC 或 opposite side 是否也 early
6. PASO 輔助
7. 低功率、短時間、小心 AV conduction
8. 嚴密監測 PR/AH/HV
```

### 重點

Para-Hisian case 不是找到最早就直接燒。

要先問：

```text
有沒有 safer site？
例如 NCC、RV septum opposite site、LV septum？
```

***

# Part 13：模組使用時間總表

| Case timing                | 主要任務                    | CARTO module / function |
| -------------------------- | ----------------------- | ----------------------- |
| Baseline recording         | 收集 VPC 型態               | Auto Pattern Bank       |
| Target selection           | 指定 clinical PVC         | Pattern Matching        |
| Anatomy build              | 建立 chamber 幾何           | CARTO anatomy / mapping |
| Activation map             | 找 earliest activation   | LAT Hybrid              |
| Sparse PVC                 | 補足定位                    | PASO                    |
| Pre-ablation confirmation  | 確認 target site          | LAT Hybrid + PASO       |
| During ablation            | 觀察 PVC suppression      | Pattern Matching        |
| Post-ablation              | 確認 target morphology 消失 | Pattern Matching        |
| Post-ablation with new PVC | 判斷是否新 morphology        | Auto Pattern Bank       |
| Redo / multiple PVC        | 分類 morphology           | Auto Pattern Bank       |

***

# Part 14：臨床 decision tree

```text
VPC 出現
│
├─ 是否為 clinical PVC？
│   ├─ Yes → Pattern Matching confirms → 收進 LAT map
│   └─ No → Auto Pattern Bank 分到其他 morphology，不納入 target map
│
├─ VPC 是否頻繁？
│   ├─ Frequent → LAT Hybrid activation mapping 為主
│   └─ Infrequent → PASO + limited activation + anatomy guide
│
├─ LAT earliest 是否夠早？
│   ├─ Yes → 看 unipolar QS + contact + PASO
│   └─ No → 換 chamber / opposite side / cusp / CS
│
├─ PASO 是否高？
│   ├─ High → 支持 target
│   └─ Low → 檢查 pacing output/contact，或考慮 deep/intramural origin
│
└─ Ablation
    │
    ├─ Target PVC 消失 → wait + induction
    └─ 未消失 → 重新檢查 morphology / chamber / mapping quality
```

***

# Part 15：你在 lab 裡可以直接講的版本

## VPC CARTO workflow 口語版

```text
這個 VPC case 我們先用 Auto Pattern Bank 觀察病人有幾種 PVC morphology，
接著用 Pattern Matching 選定 clinical PVC 作為 target，
避免 activation map 混入不同 PVC。

target morphology 確認後，我們建立懷疑 chamber 的 anatomy，
如果 PVC 頻繁，就用 LAT Hybrid 做 activation mapping，
找 local EGM 比 QRS onset 最早的位置，
同時確認 unipolar 是否為 QS pattern。

找到 earliest site 後，再用 PASO 做 pace mapping，
比較 paced QRS 跟 clinical PVC 的 similarity。
如果 earliest activation、unipolar QS、PASO 高分且 anatomy 安全，
就可以作為 ablation target。

ablation 後再用 Pattern Matching 確認 target PVC 是否消失，
並用 Auto Pattern Bank 判斷是否出現新的 PVC morphology。
```

***

# 最後重點整理

## 四個模組怎麼用？

| 模組                | 最適合使用時間                       | 主要目的                                     |
| ----------------- | ----------------------------- | ---------------------------------------- |
| Pattern Matching  | case 一開始、mapping 中、ablation 後 | 鎖定 target VPC，不要收錯 morphology            |
| Auto Pattern Bank | baseline、多型態、術後               | 自動分類不同 PVC morphology                    |
| LAT Hybrid        | target morphology 確認後         | activation mapping，找 earliest site       |
| PASO              | activation 後確認、PVC 少時、術前確認    | pace mapping，比較 paced QRS 和 clinical PVC |

***

## 最重要的成功公式

```text
Successful VPC ablation target =
Same clinical morphology
+ earliest LAT
+ good local bipolar EGM
+ unipolar QS
+ high PASO similarity
+ stable contact
+ safe anatomy
```

如果要再更濃縮：

```text
Pattern Matching 選對 PVC
Auto Pattern Bank 分清楚 morphology
LAT Hybrid 找最早
PASO 確認像不像
最後才燒
```
