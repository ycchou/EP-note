以下為\*\*整理完成、適合直接放入 Markdown 編輯器（Typora / Obsidian / HackMD / VS Code / Marp / Reveal.js）\*\*的版本。

我已保留所有內容，不刪減任何資訊，並修正：

* Markdown 標題階層
* 引用區塊格式
* 表格格式
* 清單縮排
* 流程圖 Code Block
* 中英文術語一致性
* 閱讀性與簡報轉換相容性

***

# 臨床電生理核心教材：心房撲動（Atrial Flutter）定位診斷與電燒實戰指南

> **課前核心觀念提示：**
>
> 12-lead ECG 的 F wave 與 CS activation sequence 是我們在 EP lab 裡極具價值的「機轉預測工具」，但它們並非 100% 絕對。
>
> 最終的黃金診斷仍必須仰賴：
>
> * EP study
> * Entrainment mapping（PPI-TCL）
> * 3D 高密度激發製圖（Activation Mapping）

***

# 核心單元一：如何利用 12-Lead ECG 判斷 RA vs LA AFL

心房撲動（AFL）本質上屬於 **大折返性心搏過速（Macro-reentry Tachycardia）**。

在動手燒之前，必須先區分折返環（Circuit）位於：

* 右心房（RA）
* 左心房（LA）

***

## 1. 臨床常見大分類

| 分類               | 常見電生理機轉                                        | 最常見解剖位置                            |
| ---------------- | ---------------------------------------------- | ---------------------------------- |
| **Typical AFL**  | CTI-dependent Macro-reentry                    | Right Atrium（RA）                   |
| **Atypical AFL** | Non-CTI-dependent Macro-reentry / Scar-related | Left Atrium（LA）、RA 或 Biatrial 複雜線路 |

***

## 2. 第一步：12-Lead ECG 的 F Wave 型態學解碼

### A. 典型逆時針右心房撲動（Counterclockwise Typical RA Flutter）

這是臨床上最常見的型態。

折返環繞著三尖瓣環（Tricuspid Annulus）逆時針旋轉，並通過：

* 三尖瓣環（TA）
* 下腔靜脈（IVC）

之間的：

**三尖瓣峽部（Cavotricuspid Isthmus, CTI）**

#### ECG 特徵

* **Inferior Leads（II, III, aVF）**
  * 呈現經典負向鋸齒波（Negative Sawtooth Pattern）
  * 因激發波於心房中隔向上傳導，遠離肢體導程

* **Lead V1**
  * 呈現正向（Positive / Upright）波型
  * 激發波由後壁往前壁傳導

* **Baseline**
  * 缺乏明顯等電位線（Isoelectric Interval）
  * F 波連續不間斷

> **觀察重點**
>
> 請引導學員注意 Lead II 連續不間斷的鋸齒波。
>
> 這代表 Macro-reentry Circuit 正持續活化整個心房，幾乎沒有任何等電位（Isoelectric）時段。

***

### B. 順時針右心房撲動（Clockwise / Reverse Typical RA Flutter）

折返環於 CTI 與三尖瓣環周圍以順時針方向旋轉。

#### ECG 特徵

* **Inferior Leads（II, III, aVF）**
  * 正向（Positive）
  * 或 Biphasic 波型

* **Lead V1**
  * 負向（Negative）
  * 或 Biphasic 波型

***

### C. 左心房撲動（LA Flutter / Atypical Flutter）

常見於：

* Prior AF Ablation
* Prior PVI
* Prior Atriotomy
* Extensive Atrial Scar

#### ECG 特徵

##### 缺乏典型 Sawtooth

波形通常：

* 不規則
* 鈍挫
* 變異性高

##### 出現 Isoelectric Line

提示：

* Localized Reentry
* Focal Atrial Tachycardia

##### V1 強烈正向波

若：

* 左心房後壁
* 左心房側壁

大量向右心房方向活化時，

V1 常出現高大正向波。

***

# 核心單元二：看懂冠狀靜脈竇（CS）的激發順序

## Coronary Sinus（CS）導管的重要性

CS 導管是 EP Lab 最重要的定位雷達之一。

解剖位置：

### CS Proximal（CS 9,10）

靠近：

* RA
* Interatrial Septum

***

### CS Distal（CS 1,2）

深入：

* Left Atrial Lateral Wall

***

## CS Activation Sequence 解讀法

> **觀察重點**
>
> 當 CS 1,2（Distal）比 CS 9,10（Proximal）更早出現電位時，會形成由下往上的斜向活化。
>
> 這種 **Distal-to-Proximal Activation** 在臨床上高度懷疑為 LA Origin。

***

### 1. CS Proximal → Distal

#### 電位現象

最早出現在：

* CS 9,10

依序傳導至：

* CS 7,8
* CS 5,6
* CS 3,4
* CS 1,2

#### 電生理解讀

激發波：

RA → Septum → LA Lateral Wall

#### 臨床推論

高度支持：

**RA Flutter**

尤其合併典型 Sawtooth ECG 時。

***

### 2. CS Distal → Proximal

#### 電位現象

最早出現在：

* CS 1,2

再往回傳導至：

* CS 9,10

#### 電生理解讀

激發波：

LA Lateral Wall → Septum → RA

#### 臨床推論

高度支持：

**LA Flutter**

例如：

* Peri-mitral Flutter

***

### 3. 陷阱提示：CS Sequence 並非 100% 絕對

即使出現 Distal-to-Proximal Activation，也不能直接判定為 LA Flutter。

可能原因：

#### Biatrial Flutter

折返環跨越雙心房。

#### Bachmann's Bundle

巴赫曼氏束造成異常傳導。

#### Septal Breakthrough

特殊中隔突破口改變活化方向。

***

# 核心單元三：整合判斷流程（RA vs LA AFL）

實際臨床中，必須整合：

* ECG
* CS Activation

共同判讀。

```text
                    [ 誘發心房撲動 (Induced AFL) ]
                                │
                        看 12-lead ECG F波
                                │
                ┌───────────────┴───────────────┐
         Typical Sawtooth?               Atypical Pattern?
                │                               │
        (先考慮 RA CTI)                  (懷疑 LA / Atypical)
                │                               │
         看 CS Activation                看 CS Activation
          ┌─────┴─────┐                   ┌─────┴─────┐
     Prox→Dist   Dist→Prox           Prox→Dist   Dist→Prox
          │           │                   │           │
     【情境 A】   【情境 C】          【情境 D】   【情境 B】
```

***

## 臨床決策矩陣表

| 情境    | ECG 型態                         | CS 活化順序     | 臨床懷疑與策略                                             |
| ----- | ------------------------------ | ----------- | --------------------------------------------------- |
| **A** | Typical Sawtooth               | Prox → Dist | 標準 CTI-dependent RA Flutter，直接評估 CTI Ablation       |
| **B** | Atypical + AF Ablation History | Dist → Prox | 高度懷疑 LA Flutter（Peri-mitral Flutter），進入 LA Mapping  |
| **C** | Typical Sawtooth               | Dist → Prox | 特殊陷阱，可能為 LA Source 或 Double Loop Reentry，不宜直接盲燒 CTI |
| **D** | Atypical F Wave                | Prox → Dist | Atypical RA Flutter，如 Scar-related RA Flutter       |

***

# 核心單元四：Mitral Line 的正確解剖與電燒概念

當確認為：

**Peri-mitral Macro-reentry**

最常需要切斷的關鍵通道：

**Mitral Isthmus Line**

***

## 1. 正確解剖定義：它是到 LIPV 內部嗎？

### 正確答案：

**不是。**

不可進入 LIPV 內部燒灼。

否則可能造成：

**Pulmonary Vein Stenosis**

***

### 正確的解剖路徑

Mitral Isthmus Line：

```text
Mitral Annulus
      ↓
LIPV Antrum
```

而非：

```text
Mitral Annulus
      ↓
Inside LIPV
```

***

### 解剖構造解析

心內膜面：

* Endocardial Layer

電燒路徑：

```text
Mitral Annulus
      ↓
LIPV Antrum
```

心外膜面則有：

* Coronary Sinus（CS）
* Vein of Marshall（VOM）

這些結構中的心肌纖維可能形成：

**Epicardial Breakthrough**

因此：

* Endocardial Line 完成
* 傳導仍未中斷

並不少見。

***

## 2. 如何確認 Bidirectional Block

Mitral Line 完成後，

必須進行雙側 Pacing 驗證。

***

### LAA Pacing

刺激：

Left Atrial Appendage（LAA）

觀察：

CS Activation 是否轉為：

```text
Proximal → Distal
```

***

### CS Distal Pacing

刺激：

CS Distal

觀察：

LAA Activation Time

是否明顯延遲。

***

> **阻滯失敗常見原因**
>
> * 心肌厚度過厚
> * CS Muscular Connection
> * Vein of Marshall Conduction
>
> 可能需要：
>
> * Epicardial Ablation within CS
> * Ethanol Infusion of VOM

***

# 核心單元五：AFL 電燒過程中 CL 變化的臨床判讀

EP Lab 常見情境：

```text
原 AFL
   ↓
RF Ablation
   ↓
AFL 終止
   ↓
立即誘發另一個 AFL
```

此時：

Cycle Length（CL）

變化往往提供重要線索。

```text
              [ 原本 AFL 遭受 RF Ablation ]
                              │
                ┌─────────────┴─────────────┐
              CL 變長                    CL 變短
                │                          │
       ┌────────┴────────┐        ┌────────┴─────────┐
   Circuit 變大     Conduction Slowing   Gap形成   Smaller Loop
```

***

## 1. 當 CL 變長（240 ms → 310 ms）

最常見情況。

### Circuit Expansion

Short Circuit 被阻斷後：

激發波被迫繞遠路。

例如：

```text
LIPV Loop
    ↓
Mitral Annulus Loop
```

***

### Conduction Slowing

同樣路徑，

但傳導速度下降。

因此：

```text
CL ↑
```

***

### Chamber Switching

例如：

```text
RA CTI Flutter
     ↓ RF
成功終止
     ↓
LA Flutter 出現
```

***

## 2. 當 CL 變短（300 ms → 240 ms）

通常屬於警訊。

***

### Gap Conduction

形成新的捷徑：

```text
Ablation Line
      ↓
Small Gap
      ↓
Shortcut
```

***

### Smaller Loop Reentry

形成：

* Localized Reentry
* Scar-related Reentry

不再繞大型解剖構造。

***

## 3. CL 與 CS Activation 聯動判讀

| CL 變化        | CS Sequence 變化              | 電生理解讀                              |
| ------------ | --------------------------- | ---------------------------------- |
| 260 → 320 ms | Prox→Dist → Dist→Prox       | RA Flutter 終止，轉為 LA Flutter        |
| 280 → 330 ms | 完全不變                        | 同一 Circuit 變慢或繞遠路                  |
| 310 → 240 ms | Activation 改變且訊號 Fragmented | Gap Conduction 或 Localized Reentry |

***

# 💡 Take-Home Messages

## 1. 區分左右心房來源

```text
CS Proximal 最早 → 多想 RA Flutter

CS Distal 最早 → 多想 LA Flutter
```

***

## 2. 看懂典型 F Wave

若出現：

* II、III、aVF 負向鋸齒波
* V1 正向

高度支持：

```text
Counterclockwise CTI-dependent
Typical RA Flutter
```

***

## 3. 正確解讀 Ablation 後 CL 的變化

### CL 變長

通常代表：

* Circuit 被迫繞遠
* 傳導變慢

***

### CL 變短

高度警惕：

* Gap Conduction
* Localized Reentry
* Smaller Loop Reentry

因為這往往代表新的病灶通路已經形成。
