# Pikambler

**Pikmin Bloom 高中數學模擬器**

Pikambler 是一個結合《Pikmin Bloom》普通飾品觀察紀錄與高中機率數學的網頁學習專案。

玩家可以為一個飾品系列設定初始收集狀態，逐筆記錄後續觀察到的款式，並透過理論機率模型理解新款、重複、期望值與等待時間等數學概念。

本專案以學習與娛樂為目的，不用於推估或驗證遊戲的真實掉落機率。

## Project Status

**Status: Early Development（早期開發）**

目前處於基礎開發與 Git 版本管理學習階段，尚未發布可供一般玩家使用的正式版本。

目標版本為 v1.0。

## Planned Features

v1.0 預計提供：

- 建立普通飾品系列挑戰，設定初始已擁有的款式。
- 記錄每次觀察到的款式，不論是否在遊戲內收下。
- 查閱、補登、更正和刪除歷史紀錄。
- 計算新款、重複、連續失敗和等待次數的理論機率。
- 根據觀察紀錄生成高中數學題目與解析。
- 在瀏覽器本機保存紀錄，並支援 JSON 匯出及還原。
- 提供適合手機與桌面瀏覽器使用的網頁。

上述為預定功能，不代表目前已完成實作。

## Tech Stack

v1.0 規劃採用以下技術：

| 用途 | 技術 |
|---|---|
| 網頁介面 | HTML / CSS / TypeScript |
| 開發與建置 | Node.js / Vite |
| 本機資料儲存 | IndexedDB |
| 測試 | Vitest |
| 版本管理 | Git / GitHub |
| 部署 | Cloudflare Workers Static Assets |

第一版不需要使用者帳號、後端 API 或雲端資料庫。

## Getting Started

本專案規劃使用 Vite 的 `vanilla-ts` 模板。

待應用程式原始碼與 `package.json` 正式納入 Repository 後，預定的本機開發流程為：

1. 安裝專案依賴：`npm install`
2. 啟動開發伺服器：`npm run dev`
3. 建立正式建置檔案：`npm run build`

目前遠端 Repository 尚未包含完整的 Vite 專案檔案，因此上述指令尚不能保證在全新 Clone 的環境中正常執行。

## Mathematical Assumptions

Pikambler 使用理想化機率模型，並遵守下列前提：

1. 一場挑戰對應單一普通飾品系列。
2. 假設系列共有 `N` 款，每款出現機率皆為 `1/N`。
3. 每次屬於目標系列的觀察結果互相獨立。
4. 不考慮保底機制、個人權重、地點權重或取得來源的機率差異。
5. 計算單位為已登記的目標系列觀察次數，不等於實際天數或探測器使用次數。

以上均為數學教學假設，並非對《Pikmin Bloom》真實遊戲機制的聲明。

## Data and Privacy

v1.0 規劃將挑戰與觀察紀錄儲存在使用者自己的瀏覽器中，不提供帳號及跨裝置自動同步。

瀏覽器資料可能因清除網站資料、裝置故障等原因遺失，因此正式版將提供手動備份及還原功能。

網站託管服務仍可能處理必要的網路連線中繼資料。

## Documentation

- [Product Scope](docs/SCOPE.md)：產品需求、資料定義、數學假設與非目標。
- [Development Roadmap](docs/ROADMAP.md)：開發與學習階段、實作順序及驗收條件。
- [Contributing Guide](CONTRIBUTING.md)：Git Commit 命名慣例與協作規則。

## Disclaimer

Pikambler 是非官方粉絲學習專案，與《Pikmin Bloom》的官方營運及開發單位沒有隸屬關係。

本專案提供的所有機率計算均基於明確聲明的理論假設，不代表遊戲實際掉率或玩家真實排名。