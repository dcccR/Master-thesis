# 公開無人機農田空拍資料集對照表

> 主題：可公開取得的 UAV 農田空拍資料集，涵蓋作物（小麥、玉米、水稻等），具處理（施肥／灌溉）或病害程度差異、同地點多時序與地真資料、定位與色彩／輻射校正。
> 整理日期：2026-06-15
> 備注：#1 欄位依隨附 Excel（Table S1–S7）補充；#2 欄位依隨附 PDF 補充完整細節。

---

## 一、資料集內容對照

| # / 資料集 | 作物 | 收集用途 | 處理 / 差異來源 | 拍攝日期與次數 | 光譜波段 | 地真資料 | 定位 / 校正 | 取得與授權 |
|---|---|---|---|---|---|---|---|---|
| **1. 水稻白葉枯病**<br>(Plant Phenomics 2023) | 水稻 | 白葉枯病（Xanthomonas oryzae）抗病性田間高通量表型評估，供抗病育種篩選 | 品種抗性差異（R／MR／LR）→ 病害嚴重度連續梯度（0–5 級），結合積溫（AT）、SPAD、水分含量（WC）多源資料建模 | **6 次**（2 地點各 3 次）<br>**Zhuji：** 2021/07/12（分蘗期）、2021/08/19（拔節期）、2021/09/26（灌漿期）<br>**Longyou：** 2021/07/13（早分蘗期）、2021/08/30（抽穗期）、2021/09/25（灌漿末期） | **26 波段**<br>Band 1–3：RGB（R、G、B）<br>Band 4–26：23 個多光譜波段（610.5–870.8 nm，涵蓋紅邊與近紅外區） | 病害嚴重度（0–5 級，3 位評分者獨立評分 + 平均值）、SPAD 葉綠素值、水分含量（WC）、積溫（AT） | GCP 定位；仿射轉換幾何校正；37% 已知反射率灰布做 DN→反射率輻射校正 | ⚠️ 論文 CC BY 4.0（統計補充表 Excel 可直接下載）；**UAV 影像資料需聯繫作者索取**<br>https://spj.science.org/doi/10.34133/plantphenomics.0019 |
| **2. 甜菜葉斑病 CLS**<br>(GigaScience 2022) | 甜菜（⚠️ 非指定作物） | Cercospora beticola 葉斑病早期偵測與植株目錄建立；開發多時序植株個體化工作流程 | 三級病害處理：① 對照+殺菌劑、② 接種+殺菌劑、③ 接種不施殺菌劑（Aluco 品種，人工以乾燥病葉感染） | **24 次**（每週一次）<br>2020/05/07 → 2020/10/12（完整生長季） | **6 波段（MicaSense Altum）：**<br>Blue（475 nm，BW 32 nm）、Green（560 nm，BW 27 nm）、Red（668 nm，BW 14 nm）、RedEdge（717 nm，BW 12 nm）、NIR（842 nm，BW 57 nm）、長波熱紅外（8000–14000 nm）+ DLS2 下行光感測器 | 人工標注各植株中心位置（地真）；病害嚴重度 1–10 級（KWS SAAT 量表） | 四角+中央 GCP；D-RTK 2 Mobile Station 定位修正；Agisoft Metashape v1.6.3 正射影像；QGIS v3.16 圈選；飛行高度 14 m、GSD 4 mm、75% 縱橫重疊 | ⚠️ **僅釋出子集**（完整資料用於進行中研究）<br>GigaDB 開放子集：http://dx.doi.org/10.5524/102225 |
| **3. 冬小麥 水×氮**<br>(Frontiers 2020) | 小麥 | 水分與氮素利用效率（WUE/NUE）高通量表型 | 4 灌溉（0／80／120／160 mm）× 4 氮肥（0／120／180／240 kg/ha），3 基因型、2 地點 | 整個生長季多次（確切次數見論文） | Parrot Sequoia 4 波段（綠／紅／紅邊／NIR）+ 陽光感測器 | 生物量、氮含量等破壞性地面採樣 | 陽光感測器後製 + 已知反射率校正板；30 m 高度、GSD 2.5 cm | ⚠️ 來函索取，非直接下載<br>https://www.frontiersin.org/journals/plant-science/articles/10.3389/fpls.2020.00927/full |
| **4. WeedsGalore**<br>(WACV 2025) | 玉米 | 玉米田作物／雜草語意與實例分割 | 玉米 + 4 種雜草類別；前 3 期為除草前，末期施除草劑（非施肥／病害） | **4 次：** 2023/05/25、05/30、06/06、06/15（V1 幼苗→接近全覆蓋） | **5 波段（DJI Phantom P4 Multispectral）：** R／G／B／紅邊／NIR | 密集像素標註（語意 + 實例，5 類） | 5 m 高度、GSD 2.5 mm；Agisoft 正射；附 GeoTIFF 全場正射影像（12 GB） | CC BY，完全開放 ✓<br>https://github.com/GFZ/weedsgalore |
| **5. Sri Lanka 稻田氮素**<br>(Data in Brief 2024) | 水稻 | 稻田氮素需求估算 | 氮素需求相關；跨物候期光譜變化 | 涵蓋**三個物候週期** | DJI Mavic 3M：RGB + 4 多光譜（G／R／紅邊／NIR） | SPAD 讀值 | 30 m 高度、GSD 0.1 m、0.06 ha 稻田 | Data in Brief，開放 ✓<br>https://www.sciencedirect.com/science/article/pii/S2352340924004487 |
| **6. Dryad CIMMYT 春小麥** | 小麥 | 小麥育種產量預測（基因體 + 表型多模態） | 育種品系／基因型差異（⚠️ 非施肥／灌溉處理） | YT 與 EYT 多期試驗，飛行時間 11am–2pm | MicaSense RedEdge-M **5 波段**（B／G／R／紅邊／NIR），未壓縮 TIFF | 小區級植被指數、冠層高度（DEM）、冠層溫度、產量、基因型 | RTK 測量公分級 GCP；影像縱橫各 80% 重疊 | Dryad，開放 ✓<br>https://datadryad.org/dataset/doi:10.5061/dryad.kprr4xh5p |

---

## 二、六項條件逐項符合度

判讀符號：✓ 完全符合　△ 部分符合／需確認　✗ 不符合

| # / 資料集 | ① 公開可取得 | ② 指定作物<br>(小麥/玉米/水稻) | ③ 施肥灌溉<br>或病害差異 | ④ 同地點多時序<br>+ 地真 | ⑤ 定位<br>(georeferencing) | ⑥ 色彩/輻射<br>校正 |
|---|:--:|:--:|:--:|:--:|:--:|:--:|
| **1. 水稻白葉枯病** | ⚠️ 補充表可下載；影像需來函 | ✓ 水稻 | ✓ 病害嚴重度 0–5 | ✓ 6 次，3 位評分者 | ✓ GCP + 幾何校正 | ✓ 37% 灰布反射率 |
| **2. 甜菜葉斑病 CLS** | ⚠️ 僅子集開放 | ✗ 甜菜 | ✓ 病害三級處理 | ✓ 24 次全季 | ✓ D-RTK GCP | ✓ DLS2 下行光感測器 |
| **3. 冬小麥 水×氮** | ✗ 來函索取 | ✓ 小麥 | ✓ 施肥+灌溉 | ✓ | △ 未特別強調 GCP | ✓ 反射率校正板 |
| **4. WeedsGalore** | ✓ | ✓ 玉米 | △ 雜草，非施肥/病害 | ✓ 4 次 GeoTIFF | ✓ GeoTIFF | △ 多光譜對齊，輻射校正未強調 |
| **5. Sri Lanka 稻田氮素** | ✓ | ✓ 水稻 | △ 氮素需求，無明確對照梯度 | ✓ SPAD | △ 細節未明 | △ 未明確 |
| **6. Dryad CIMMYT 春小麥** | ✓ | ✓ 小麥 | ✗ 育種基因型 | ✓ | ✓ RTK 公分級 | △ MicaSense，校正流程未強調 |

---

## 三、#1 水稻白葉枯病 ── 詳細資料背景（來自 Table S1–S7）

### 3.1 實驗設計

| 項目 | Experiment 1（Zhuji 諸暨，浙江） | Experiment 2（Longyou 龍游，浙江） |
|---|---|---|
| 品種數 | 14 個（YY31、JHY2、Y1578、ZZY8、CX7860、YY15、JHY7245、YY7860、YY1540、J67、ZJ100、ZJ165、HXY2171、YY7860-1） | ~60 個（BI1–BI60 系列） |
| 抗性分類 | R（高抗）、MR（中抗）、LR（低抗） | 同左 |

### 3.2 拍攝日期與生長期

| 地點 | 拍攝日期 | 生長期 |
|---|---|---|
| Zhuji | 2021/07/12 | 分蘗期（Tillering） |
| Zhuji | 2021/08/19 | 拔節期（Jointing） |
| Zhuji | 2021/09/26 | 灌漿期（Filling） |
| Longyou | 2021/07/13 | 早分蘗期（Early tillering） |
| Longyou | 2021/08/30 | 抽穗期（Heading） |
| Longyou | 2021/09/25 | 灌漿末期（Late filling） |

### 3.3 光譜波段明細（Table S2，共 26 個波段）

| 波段 | 波長（nm） | 說明 |
|:--:|---|---|
| 1 | R（可見光紅） | RGB Band |
| 2 | G（可見光綠） | RGB Band |
| 3 | B（可見光藍） | RGB Band |
| 4 | 610.5 | 多光譜起始（紅邊前緣） |
| 5–11 | 618.5–682.7 | 紅邊前段，含葉綠素吸收峰（665.8 nm） |
| 12–14 | 698.4–736.6 | 紅邊區段 |
| 15–26 | 750.5–870.8 | NIR 平台至高端 |

### 3.4 地真資料欄位（Table S1）

| 欄位 | 說明 |
|---|---|
| Acquisition time | UAV 拍攝日期 |
| Location | Zhuji 或 Longyou |
| Cultivars | 品種代號 |
| Resistance | 抗性等級：R／MR／LR |
| Growth stage | 生長期 |
| Disease severity（Rater 1–3） | 三位評分者獨立給分（0–5 級） |
| Disease severity（Average） | 三者平均值（用於建模） |

> 附加量測：SPAD 葉綠素值、水分含量（WC）、積溫（AT）——均用於多源融合建模（Table S3）。

### 3.5 模型表現摘要（Table S4）

| 輸入資料 | 最佳模型 | R²（驗證集） | RMSE（驗證集） |
|---|---|---|---|
| 光譜（Spectra） | SVR | 0.83 | 0.70 |
| 光譜 + 積溫（Spectra+AT） | SVR | **0.86** | **0.65** |
| 光譜 + 紋理/色彩 + 積溫 | SVR | 0.84 | 0.69 |

---

## 四、#2 甜菜葉斑病 CLS ── 詳細資料背景（來自 GigaScience 2022 PDF）

### 4.1 實驗設計

| 項目 | 內容 |
|---|---|
| 地點 | 德國哥廷根（Göttingen，51°33'N 9°53'E） |
| 年份 | 2020 |
| 作物 | 甜菜（Sugar beet），Aluco 品種（對 CLS 易感） |
| 播種日期 | 2020/04/06 |
| 行距 | 48 cm（行間）× 18 cm（行內），約 110,000 株/公頃 |
| 小區數 | 19 個，各 172 m² |
| 病害 | Cercospora leaf spot（CLS），*Cercospora beticola* |
| 處理 | ① 對照 + 殺菌劑、② 接種 + 殺菌劑、③ 接種，不施殺菌劑 |
| 感染方式 | 人工以乾燥病葉材料接種 |

### 4.2 拍攝規格

| 項目 | 規格 |
|---|---|
| 無人機 | DJI Matrice 210（四旋翼） |
| 定位 | GPS + GLONASS，D-RTK 2 Mobile Station 差分修正 |
| 相機 | MicaSense Altum 多光譜（6 波段 + DLS2 下行光感測器） |
| 飛行高度 | 約 14 m AGL |
| 飛行速度 | 0.5 m/s |
| 地面解析度（GSD） | 4 mm/px |
| 影像重疊率 | 縱橫各 75% |

### 4.3 光譜波段明細（MicaSense Altum）

| 波段 | 中心波長（nm） | 頻寬（nm） |
|---|:--:|:--:|
| Blue | 475 | 32 |
| Green | 560 | 27 |
| Red | 668 | 14 |
| Red Edge | 717 | 12 |
| NIR | 842 | 57 |
| 長波熱紅外（LWIR） | 8,000–14,000 | 寬帶 |
| *(+ DLS2 下行光感測器，用於輻射校正)* | | |

### 4.4 拍攝日期（24 次，每週一次）

2020/05/07 起至 2020/10/12 止，貫穿完整生長季。圖 7 顯示的對齊點雲顏色從 2020/05/07 到 2020/12/10（含補充影像）。

### 4.5 後處理與定位

| 步驟 | 工具/方法 |
|---|---|
| 正射影像生成 | Agisoft Metashape Professional v1.6.3 |
| 地面控制點（GCP） | 設置於四角及中央，WGS84 座標系 |
| 小區圈選 | QGIS v3.16 |
| 植株定位 | 電腦視覺工作流程（植土分割 → 高斯模糊峰值偵測 → 播種行辨識 → 時序植株目錄） |
| 定位精度 | 最大容許偏差 8 cm（true positive 判斷標準） |

### 4.6 地真資料

- 人工標注各植株中心位置（early growth stage 優先標注）
- 病害嚴重度 1–10 級（KWS SAAT SE 量表：1 = 完全健康，10 = 完全病害）
- 子集（約 4,000 張植株影像）已做病害嚴重度標注，供 ResNet-50 分類訓練

### 4.7 資料取得說明

> 「兩個資料集均用於進行中之研究，**無法完整公開**。子集已上傳至 GigaDB，足以重現本文結果。」
> — 原文 Data Availability 段

完整資料需聯繫作者；子集連結：http://dx.doi.org/10.5524/102225

---

## 五、選用建議

- **病害梯度 + 多時序 + 校正最完整：** #2 甜菜葉斑病（24 次拍攝，熱紅外 + 6 波段多光譜），但作物不在指定清單，且只有子集開放；影像資料需來函聯繫。
- **指定作物且補充統計資料可直接下載：** #1 水稻白葉枯病（UAV 影像本身需聯繫作者）。
- **施肥+灌溉處理設計最嚴謹：** #3 冬小麥水×氮，同樣需來函索取。
- **完全開放且可直接下載：** #4 WeedsGalore（玉米）、#5 Sri Lanka 稻田（水稻）、#6 CIMMYT（小麥），差異來源分別為雜草／氮素／育種基因型，非嚴格施肥灌溉對照。

> **開放性說明：** 六筆資料中，**沒有任何一筆在「指定作物 + 病害或施肥處理 + UAV 影像完全開放下載」三項條件同時滿足**。需要 UAV 影像的研究者，對 #1 和 #3 均需去信聯繫，#2 子集雖在 GigaDB 但不完整。

---

## 六、來源連結

1. **水稻白葉枯病**（Plant Phenomics 2023）：https://spj.science.org/doi/10.34133/plantphenomics.0019
2. **甜菜葉斑病 CLS**（GigaScience 2022）：https://academic.oup.com/gigascience/article/doi/10.1093/gigascience/giac054/6610009 ｜ 資料子集：http://dx.doi.org/10.5524/102225
3. **冬小麥 水×氮**（Frontiers 2020）：https://www.frontiersin.org/journals/plant-science/articles/10.3389/fpls.2020.00927/full
4. **WeedsGalore**（WACV 2025）：https://github.com/GFZ/weedsgalore ｜ 論文：https://arxiv.org/abs/2502.13103
5. **Sri Lanka 稻田氮素**（Data in Brief 2024）：https://www.sciencedirect.com/science/article/pii/S2352340924004487
6. **Dryad CIMMYT 春小麥**：https://datadryad.org/dataset/doi:10.5061/dryad.kprr4xh5p

### 延伸彙整入口
- ICAERUS-EU Zenodo Datasets（歐盟 UAV 農業資料集總表）：https://github.com/ICAERUS-EU/Zenodo_Datasets
- msuav500k（跨感測器輻射一致的基礎資料集）：https://www.ncbi.nlm.nih.gov/pmc/articles/PMC12595141/
