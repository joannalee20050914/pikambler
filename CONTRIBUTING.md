# Contributing to Pikambler

## Commit Message Convention

本專案採用 [Conventional Commits 1.0.0](https://www.conventionalcommits.org/zh-hant/v1.0.0/)。

格式：

`<type>(<optional-scope>): <description>`

### 規則

1. Type 使用小寫英文。
2. Description 使用簡短、清楚的英文，描述本次實際修改內容。
3. 優先使用動詞開頭，例如 `add`、`fix`、`update`、`remove`。
4. Scope 可省略；需要時使用模組名稱，例如 `math`、`ui`、`storage`、`questions`。
5. 每個 Commit 儘量只包含一個邏輯上完整的修改。
6. 複雜修改可補充 Commit Body，說明修改原因。
7. Commit 前必須檢查 Staged Diff，避免提交無關檔案、憑證或機密資訊。

### 允許的類型

- `feat`：新增功能
- `fix`：修復錯誤
- `docs`：文件修改
- `test`：測試修改
- `refactor`：不改變外部行為的程式重構
- `chore`：一般專案維護
- `ci`：持續整合與部署流程


## Commit Message 英文句型

Conventional Commits 的基本格式：

```
<type>(<scope>): <verb> <object> [details]
```

| 結構      | 意義       | 例子                       |
| ------- | -------- | ------------------------ |
| Type    | 修改類型     | `feat`                   |
| Scope   | 修改範圍，可省略 | `(math)`                 |
| Verb    | 做了什麼動作   | `add`                    |
| Object  | 修改了什麼東西  | `probability calculator` |
| Details | 額外說明，可省略 | `for variable set sizes` |

組合起來：

```
feat(math): add probability calculator for variable set sizes
```

意思是：在數學模組中，新增支援不同總款數的機率計算器。

### 動詞時態

建議統一採用 祈使語氣（Imperative Mood），也就是動詞原形。

| 建議使用     | 不建議       |
| -------- | --------- |
| `add`    | `added`   |
| `fix`    | `fixed`   |
| `update` | `updated` |
| `remove` | `removed` |

英文 Commit Message 可以理解成一個指令：

「套用這次 Commit，就會 add 某個功能。」

這是 Git Commit 常見的英文撰寫慣例；Conventional Commits 本身並未強制所有描述都必須使用祈使語氣，但我們可以將它訂成 Pikambler 的統一風格。

## 常用英文動詞字典

「所有可能的動詞」無法列完，而且沒有必要。先整理最常用、足以涵蓋我們 Stage 00～15 開發工作的詞彙。

| 動詞          | 中文    | 適用情境                   |
| ----------- | ----- | ---------------------- |
| `add`       | 新增    | 增加功能、檔案、選項             |
| `create`    | 建立    | 建立新物件、頁面、初始結構          |
| `implement` | 實作    | 完成某項功能或演算法             |
| `define`    | 定義    | 型別、規則、資料模型             |
| `update`    | 更新    | 更新既有功能或文件              |
| `revise`    | 修訂    | 修改文件、需求敘述              |
| `clarify`   | 釐清    | 消除文件或規則的歧義             |
| `document`  | 文件化   | 將規則、使用方法寫進文件           |
| `fix`       | 修復    | 修正 Bug                 |
| `correct`   | 修正    | 修正計算結果、錯誤內容            |
| `handle`    | 處理    | 處理例外情況                 |
| `prevent`   | 防止    | 避免重複提交、錯誤操作            |
| `refactor`  | 重構    | 改善程式結構但不改變功能           |
| `extract`   | 抽出    | 將函式或邏輯拆成獨立模組           |
| `simplify`  | 簡化    | 減少不必要的程式邏輯             |
| `remove`    | 移除    | 移除功能、程式碼               |
| `rename`    | 重新命名  | 修改變數、函式或檔案名稱           |
| `support`   | 支援    | 支援新的資料形式或使用情境          |
| `enable`    | 啟用    | 啟用特定能力                 |
| `validate`  | 驗證    | 檢查輸入、資料格式是否合法          |
| `test`      | 測試    | 新增測試行為                 |
| `cover`     | 涵蓋    | 補足測試案例                 |
| `configure` | 設定    | 設定建置工具或服務              |
| `persist`   | 持久化保存 | 將資料保存到 IndexedDB 等儲存系統 |
| `export`    | 匯出    | 將資料轉換並輸出               |
| `import`    | 匯入    | 讀取外部資料                 |
| `restore`   | 還原    | 從備份恢復資料                |
| `migrate`   | 遷移    | 調整資料結構或儲存位置            |
| `deploy`    | 部署    | 將網站發布到指定環境             |
| `rollback`  | 回滾    | 恢復先前的部署版本              |

有些字意思很接近，但使用情境不同。例如：

- `add` 強調增加某個東西。
- `implement` 強調將規格真正實作完成。
- `define` 強調確立結構或規則。
- `configure` 強調設定既有工具。

## 依照 Type 建立句型模板

這部分可以直接作為未來 `CONTRIBUTING.md` 的 Commit Writing Guide。

| Type       | 常用模板                      | Pikambler 範例                                      |
| ---------- | ------------------------- | ------------------------------------------------- |
| `feat`     | `add <feature>`           | `feat(journal): add observation history`          |
| `feat`     | `implement <feature>`     | `feat(math): implement expected draw calculation` |
| `fix`      | `fix <problem>`           | `fix(ui): fix incorrect progress display`         |
| `fix`      | `prevent <problem>`       | `fix(journal): prevent duplicate submissions`     |
| `docs`     | `document <subject>`      | `docs: document probability assumptions`          |
| `docs`     | `clarify <rule>`          | `docs: clarify observation recording rules`       |
| `test`     | `cover <cases>`           | `test(math): cover probability edge cases`        |
| `test`     | `add tests for <feature>` | `test(storage): add tests for backup import`      |
| `refactor` | `extract <module>`        | `refactor(storage): extract repository interface` |
| `refactor` | `simplify <logic>`        | `refactor(math): simplify probability functions`  |
| `chore`    | `configure <tool>`        | `chore: configure TypeScript compiler`            |
| `chore`    | `update <dependency>`     | `chore: update development dependencies`          |
| `ci`       | `add <workflow>`          | `ci: add pull request validation workflow`        |
| `ci`       | `run <checks>`            | `ci: run tests on pull requests`                  |

這些是建議的句型，不是每個英文描述都必須符合固定字串。

另外，`type` 與 `scope` 通常使用小寫，description 不加結尾句號，以保持風格一致。

1. 使用 Conventional Commits 格式。
2. Description 使用英文動詞原形開頭。
3. 描述這次 Commit 實際完成的修改，不只是檔案名稱。
4. 使用簡短、明確、可以從 Git Diff 驗證的描述，避免 `update stuff`、`fix things` 等模糊訊息。

### Agent 協作規則

- Agent 必須遵循本文件的 Commit Message Convention。
- 未經使用者明確授權，不得自行 Commit、Push 或 Merge。
- 核心程式由使用者親手撰寫；Agent 主要協助文件整理、程式審查與測試分析。
- Agent 修改文件後，須由使用者審核才可合併。