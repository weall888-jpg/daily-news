# 📰 國教盟每日新聞日報系統

## ⚠️ 重要規則

- **新聞稿統計**：只統計 2026 年開始發出的新聞稿
- **週報追蹤**：追蹤「最新一週」，不是去年同期
- **月報追蹤**：追蹤「當月」，不是去年同月
- **來源資料夾**：`~/clawd/新聞稿已發出/`

---

## 資料夾結構

```
每日新聞日報/
├── index.html          ← 當日日報（每天覆蓋）
├── archive/
│   ├── daily/          ← 每日存檔
│   │   ├── 2026-03-11.html
│   │   ├── 2026-03-12.html
│   │   └── ...
│   ├── weekly/         ← 週報彙整
│   │   ├── 2026-W11.html
│   │   └── ...
│   └── monthly/        ← 月報彙整
│       ├── 2026-03.html
│       └── ...
└── README.md
```

## 運作流程

### 📰 每日（自動）
1. 抓取今日新聞（NewsAPI）
2. 生成日報 `index.html`
3. 同時存檔到 `archive/daily/YYYY-MM-DD.html`
4. 上傳 GitHub Pages

### 📅 每週日（彙整）
1. 讀取本週 7 天的日報
2. 提取重點新聞
3. 生成週報 `archive/weekly/YYYY-W##.html`

### 📊 每月底（彙整）
1. 讀取本月所有日報
2. 統計議題趨勢
3. 生成月報 `archive/monthly/YYYY-MM.html`

## 網址

| 類型 | 網址 |
|------|------|
| 今日日報 | https://weall888-jpg.github.io/daily-news/ |
| 日報存檔 | https://weall888-jpg.github.io/daily-news/archive/daily/2026-03-11.html |
| 週報 | https://weall888-jpg.github.io/daily-news/archive/weekly/2026-W11.html |
| 月報 | https://weall888-jpg.github.io/daily-news/archive/monthly/2026-03.html |

## 使用方式

```bash
# 生成今日日報
~/clawd/tools/generate-daily-news.sh

# 生成週報（每週日執行）
~/clawd/tools/generate-weekly-report.sh

# 生成月報（每月底執行）
~/clawd/tools/generate-monthly-report.sh
```

---

*建立日期：2026-03-11*
