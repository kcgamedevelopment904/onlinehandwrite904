# 網上手寫輸入法 KC904

以繁體中文介面呈現的網頁手寫輸入法。使用者可在畫布上書寫，選取辨識候選字或詞語，再將文字及標點插入輸入框。

## 開始使用

主要入口是 [`VS code & Github Cppilot AI.html`](./VS%20code%20%26%20Github%20Cppilot%20AI.html)。建議在專案資料夾啟動本機靜態伺服器：

```bash
python -m http.server 8000
```

然後在瀏覽器開啟 <http://localhost:8000/>，並選擇主要 HTML 檔案。也可以直接在瀏覽器開啟該 HTML，但部分瀏覽器在 `file://` 模式下會限制網路請求。

## 功能

- 在畫布上以滑鼠、觸控或觸控筆書寫並取得中文字候選。
- 從萌典詞目索引提供相關詞語候選。
- 插入常用標點、復原上一筆、清空畫布、刪除文字及複製文字。
- 使用 OpenCC 在繁體中文與簡體中文之間轉換。
- 同一資料夾內的 `code_artifact*.html` 是其他版本或版本變體。

## 網路服務與相依項目

此專案是單頁 HTML，沒有建置步驟或套件安裝程序。頁面會從 CDN 載入 Tailwind CSS 與 OpenCC，並連線至以下服務：

- Google Input Tools：送出手寫筆跡以取得辨識候選。
- 萌典：載入詞目索引以提供詞語候選。

因此，使用完整功能需要網際網路連線。手寫筆跡會傳送至 Google Input Tools；詞目索引則由萌典載入。

## 技術

- HTML、CSS、原生 JavaScript
- Tailwind CSS CDN
- OpenCC JS
- Google Input Tools 手寫辨識
- 萌典詞目索引
