# 🔔 RingRing — Discord Utility Bot

> 一個以「實用性」為核心設計的 Discord Bot，專注於提醒、資料查詢與社群互動功能。

![Python](https://img.shields.io/badge/Python-3.11-blue?logo=python)
![discord.py](https://img.shields.io/badge/discord.py-2.3-5865F2?logo=discord)
![Status](https://img.shields.io/badge/Status-In%20Development-yellow)
![License](https://img.shields.io/badge/License-MIT-green)

---

## 📌 專案動機

在使用 Discord 管理日常事務與與朋友溝通的過程中，發現缺乏一個輕量、直覺的工具型 Bot。
RingRing 的目標是讓使用者不需要離開 Discord，就能完成提醒設定、即時資訊查詢與簡單的群體互動。

這也是我學習 Python 與非同步程式設計的實作專案。

---

## ✨ 功能模組

### 🕐 Module 1 — 提醒系統（Reminder）
| 指令 | 說明 | 範例 |
|------|------|------|
| `!remind <時間> <內容>` | 設定倒數提醒 | `!remind 30m 去吃飯` |
| `!remindlist` | 查看目前所有提醒 | `!remindlist` |
| `!cancelremind <id>` | 取消指定提醒 | `!cancelremind 2` |

> 技術重點：使用 `asyncio` 實作非阻塞式倒數，支援 `m`（分鐘）/ `h`（小時）格式解析

---

### 🌤️ Module 2 — 資料查詢（Data Fetch）
| 指令 | 說明 | 範例 |
|------|------|------|
| `!weather <城市>` | 查詢即時天氣 | `!weather 台北` |
| `!crypto <幣種>` | 查詢加密貨幣現價 | `!crypto BTC` |

> 技術重點：串接 OpenWeatherMap API 與 CoinGecko API，使用 `requests` 解析 JSON 回應

---

### 🛠️ Module 3 — 實用工具（Utilities）
| 指令 | 說明 | 範例 |
|------|------|------|
| `!ping` | 顯示 Bot 當前延遲 | `!ping` |
| `!calc <算式>` | 計算數學運算式 | `!calc 25*4+10` |
| `!poll <題目> <選項...>` | 發起 emoji 投票 | `!poll 吃什麼? 火鍋 壽司 拉麵` |

---

## 🏗️ 技術架構

```
ringring/
├── main.py              # Bot 進入點，載入所有 Cog
├── cogs/
│   ├── reminder.py      # 提醒模組（asyncio）
│   ├── datafetch.py     # API 查詢模組
│   └── utilities.py     # 工具指令模組
├── utils/
│   └── time_parser.py   # 時間格式解析工具
├── .env                 # Token 與 API Key（不上傳）
├── requirements.txt
└── README.md
```

---

## 🧰 使用技術

- **語言**：Python 3.11
- **主框架**：[discord.py 2.3](https://discordpy.readthedocs.io/)
- **非同步**：`asyncio` — 處理提醒倒數不阻塞主程序
- **HTTP 請求**：`requests` — 串接外部 API
- **環境變數**：`python-dotenv` — 保護 Token 安全
- **外部 API**：OpenWeatherMap、CoinGecko

---

## 📚 開發過程與學習紀錄

| 階段 | 內容 | 學到的概念 |
|------|------|------------|
| Week 1 | Python 基礎語法、函式、型別 | 變數、條件、迴圈、函式 |
| Week 2 | discord.py 環境建置、第一個 `!ping` | Bot Token、事件驅動架構 |
| Week 3 | 工具指令模組開發 | Cog 架構、指令錯誤處理 |
| Week 4 | 串接天氣與幣價 API | HTTP GET、JSON 解析、例外處理 |
| Week 5 | 提醒系統開發 | `asyncio.sleep`、非同步概念 |
| Week 6 | 重構與模組化 | 軟體架構設計、程式碼可讀性 |

---

## 🚀 本地執行方式

```bash
# 1. 複製專案
git clone https://github.com/konghao17/ringring.git
cd ringring

# 2. 安裝依賴套件
pip install -r requirements.txt

# 3. 設定環境變數
cp .env.example .env
# 編輯 .env，填入 DISCORD_TOKEN 與 API Keys

# 4. 啟動 Bot
python main.py
```

---

## 📋 requirements.txt

```
discord.py==2.3.2
requests==2.31.0
python-dotenv==1.0.0
```

---

## 🗺️ Roadmap

- [x] 專案架構規劃
- [x] `!ping` 基礎指令
- [ ] 提醒系統完整實作
- [ ] 天氣查詢模組
- [ ] 幣價查詢模組
- [ ] 投票功能
- [ ] 部署至雲端（Railway / Render）

---

## 👤 作者

**konghao17** — [github.com/konghao17](https://github.com/konghao17)

> 這是我從零開始學習 Python 的第一個實作專案，持續開發中。
