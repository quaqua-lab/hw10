# 居家烹飪科學：牛排的「梅納反應」與低溫舒肥（Sous-Vide）安全指南 — LLM Wiki

本專案為「用 LLM Wiki 做一份教學 HTML 簡報」作業成果，採用 **「先討論、後生成」** 與 **「純文字 Markdown + 雙向連結 (`[[條目]]`) + 強制查核規範」** 架構建立知識庫，並以此 Wiki 為唯一知識來源生成可互動瀏覽的教學型 HTML 簡報。

## 資料夾架構

```text
cooking-science-wiki/
├── README.md                 # Wiki 總覽、知識地圖與簡報 1 對 1 對應表
├── WIKI_RULES.md             # 給 AI 的系統規範（條目模板、雙向連結、單位與食安查核規則）
├── raw_sources/              # 5 篇原始 Ingest 資料（含故意埋設之 °F/°C 與時間前提易錯點）
│   ├── 01_maillard_reaction.md
│   ├── 02_protein_denaturation.md
│   ├── 03_steak_doneness.md
│   ├── 04_sous_vide_safety.md
│   └── 05_searing_troubleshooting.md
├── wiki/                     # AI 執行 Ingest 與查核後生成的 6 篇結構化 Wiki 條目
│   ├── 梅納反應.md
│   ├── 焦糖化反應.md
│   ├── 蛋白質變性與肉汁流失.md
│   ├── 牛排中心溫度與靜置回溫.md
│   ├── 低溫舒肥巴氏殺菌曲線.md
│   └── 表面水分與水煮效應.md
├── logs/                     # 實際執行、攔截錯誤與 Workflow 調整紀錄
│   └── execution_and_check_log.md
└── presentation/             # 步驟二產出的教學型 HTML 簡報
    └── index.html
```

## Wiki 條目與教學簡報 1 對 1 對應表

| 簡報頁次 | 簡報主題 | 對應 Wiki 條目 | 對應原始資料 |
| :--- | :--- | :--- | :--- |
| Slide 1–2 | 封面與學習地圖：為什麼牛排會香、雞胸會柴？ | 總覽導引（連結全 6 篇） | 全部 5 篇 |
| Slide 3 | 核心原理 ①：梅納反應 vs. 焦糖化反應 | `[[梅納反應]]`、`[[焦糖化反應]]` | `01_maillard_reaction.md` |
| Slide 4 | 核心原理 ②：蛋白質變性與肉汁流失 | `[[蛋白質變性與肉汁流失]]` | `02_protein_denaturation.md` |
| Slide 5 | 黃金參數 ①：牛排熟度與靜置回溫 | `[[牛排中心溫度與靜置回溫]]` | `03_steak_doneness.md` |
| Slide 6 | 黃金參數 ②：低溫舒肥巴氏殺菌曲線 | `[[低溫舒肥巴氏殺菌曲線]]` | `04_sous_vide_safety.md` |
| Slide 7 | 實戰排錯：為什麼煎不出焦香？（水煮效應） | `[[表面水分與水煮效應]]` | `05_searing_troubleshooting.md` |
| Slide 8 | 系統揭密：Loop / Graph 流程與食安查核反思 | `logs/execution_and_check_log.md` | 系統執行紀錄 |
