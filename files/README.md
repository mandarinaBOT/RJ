# 彩虹餐盤 — 設定說明（Gemini 免費版）

## 你只要做兩件事

### 一、申請免費金鑰

1. 打開 `aistudio.google.com`
2. 用 Google 帳號登入
3. 點左側或右上角的 **Get API key** / **取得 API 金鑰**
4. 按 **Create API key**（建立 API 金鑰）
5. 複製出現的那串金鑰

不用信用卡，不用付費。

### 二、把金鑰填進網頁

用記事本打開 `health-diet.html`，用 Ctrl+F 搜尋 `GEMINI_API_KEY`，找到這一行：

```js
const GEMINI_API_KEY = "在這裡貼上你的金鑰";
```

把引號中間換成你的金鑰：

```js
const GEMINI_API_KEY = "AIzaSy...你的金鑰...";
```

存檔，上傳到 GitHub，完成。

---

## 部署

檔名改成 `index.html`，上傳到 GitHub 倉庫即可。
GitHub Pages、Cloudflare Pages、Netlify 都可以，不需要任何後端設定。

---

## 建議：限制金鑰只能從你的網站使用

因為金鑰寫在網頁裡，別人看得到。免費金鑰被拿走不會產生帳單，
但額度可能被用掉。加一道限制比較安心：

1. 到 `console.cloud.google.com` → APIs & Services → Credentials
2. 點你的金鑰 → Application restrictions
3. 選 **Websites**，加入你的網址（例如 `https://你的網站.pages.dev/*`）
4. 儲存

---

## 常見問題

| 症狀 | 原因 |
|---|---|
| 「還沒填入金鑰」 | 金鑰沒貼，或貼錯位置 |
| 「金鑰無效」 | 複製不完整，或前後有多餘空格 |
| 「今天的免費額度用完了」 | 等幾小時後重置 |
| 分享頁顯示示範模式 | Firebase 尚未設定（另一件事，可之後再做） |

---

## 備註

網頁會自動嘗試 `gemini-2.5-flash`、`gemini-3.5-flash`、`gemini-2.5-flash-lite`，
挑到能用的就固定使用，所以 Google 換模型名稱時通常不用你手動改。
