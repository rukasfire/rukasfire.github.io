# Ruka Shih — Personal Resume

> 史詒君 · IP & Patent Strategy @ MicroLED Frontier

A single-page, zero-dependency personal resume / portfolio built for GitHub Pages.
Light theme (GitHub dimmed palette), mono-first typography, code-comment inspired sections, fully interactive (scroll-spy nav, keyboard `j`/`k` scrolling, click-to-expand career timeline, count-up metric animation).

## 內容來源

取材自兩份來源檔：

- `Ruka_Shih_履歷簡報_2026.pdf`（8 頁履歷簡報）
- `Ruka_Shih_CV.pdf`（詳細 CV）

整合後以單頁履歷方式重組，**內容可再微調**：姓名、Mail、Phone、GitHub URL 等欄位都在 `index.html` 內以獨立變數呈現（搜尋 `// @replaceable`），可直接編輯。

## 檔案結構

```
rukasfire-resume/
├── index.html       # 單頁主檔（含 inline CSS / JS）
└── README.md        # 你正在看的這個檔
```

## 在本地預覽

任何靜態伺服器都行，挑一個：

```bash
# option A: python
python3 -m http.server 8080
# → open http://localhost:8080

# option B: node
npx serve .
```

## 推到 GitHub Pages（推薦）

1. 在 GitHub 建一個新 repo，命名為 `<你的帳號>.github.io`（例：`rukasfire.github.io`）。
2. 把這個資料夾的內容 commit & push：

```bash
cd rukasfire-resume
git init
git add .
git commit -m "feat: initial personal resume site"
git branch -M main
git remote add origin git@github.com:<你的帳號>/<你的帳號>.github.io.git
git push -u origin main
```

3. 進到 GitHub repo → **Settings → Pages** → Source 選 `main` branch / root。
4. 等 1–2 分鐘，網址會是 `https://<你的帳號>.github.io`。

> 如果 repo 不想叫 `<帳號>.github.io`，也可以建 `resume` 這類名稱，最後網址會是 `https://<你的帳號>.github.io/resume/`。

## 自訂

打開 `index.html`，搜尋以下快速定位關鍵字：

| 關鍵字              | 用途                              |
| ------------------- | --------------------------------- |
| `Ruka Shih`         | 姓名 / 標題                        |
| `rukashih@gmail.com`| 主要聯絡 email                    |
| `+886 922 116 171`  | 電話                              |
| `github.com/rukasfire` | GitHub 個人頁連結               |
| `#hero`             | 主標 hook 文案                    |
| `data-count=`       | Key Metrics 數字（可調數值／單位） |
| `// D-0X`           | Major Deals 區的 case 卡          |

所有色票、字體、間距都在 `:root` CSS variable 區塊集中管理，換主題只改幾行。

## 技術備忘

- 不需要 build step。HTML + inline CSS + vanilla JS，零外部依賴。
- 互動細節：scroll-spy nav / `j` `k` 鍵盤翻頁 / 點擊 career tab 切換內容 / 滾到 metrics 時跑 e^3 ease-out 數字動畫。
- RWD 斷點 860px（桌機 / 手機單欄切換）。
- 鍵盤可達性：`j`/`k` 在 input/textarea 內自動失效。

## License

MIT — 歡迎 fork 自用，但請不要拿這份去發另一個 Ruka Shih 履歷。
