<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "650e63282e1dfa032890fcf5c1c4119d",
  "translation_date": "2025-10-22T22:46:42+00:00",
  "source_file": "3-terrarium/1-intro-to-html/assignment.md",
  "language_code": "mo"
}
-->
# HTML 練習作業：建立部落格模擬版面

## 學習目標

透過設計和編寫完整的部落格首頁結構來應用您的 HTML 知識。這項實作作業將加強您對語義化 HTML 概念的理解、可訪問性最佳實踐，以及在網頁開發過程中使用的專業代碼組織技能。

**完成此作業後，您將能夠：**
- 練習在編碼前規劃網站版面
- 適當地應用語義化 HTML 元素
- 創建可訪問且結構良好的標記
- 培養專業的編碼習慣，包括添加註解和組織代碼

## 專案要求

### 第一部分：設計規劃（視覺模擬版面）

**創建您的部落格首頁的視覺模擬版面，需包含以下內容：**
- 帶有網站標題和導航的頁首
- 主內容區域，至少包含 2-3 篇部落格文章預覽
- 側邊欄，包含額外資訊（關於區塊、近期文章、分類）
- 頁尾，包含聯絡資訊或連結

**模擬版面創建選項：**
- **手繪草圖**：使用紙和鉛筆，然後拍照或掃描您的設計
- **數位工具**：Figma、Adobe XD、Canva、PowerPoint 或任何繪圖應用程式
- **線框工具**：Balsamiq、MockFlow 或類似的線框設計軟體

**為您的模擬版面各部分標註您計劃使用的 HTML 元素**（例如，「頁首 - `<header>`」、「部落格文章 - `<article>`」）。

### 第二部分：HTML 元素規劃

**創建一份清單，將模擬版面的每個部分映射到特定的 HTML 元素：**

```
Example:
- Site Header → <header>
- Main Navigation → <nav> with <ul> and <li>
- Blog Post → <article> with <h2>, <p>, <time>
- Sidebar → <aside> with <section> elements
- Page Footer → <footer>
```

**必須包含的元素：**
您的 HTML 必須至少包含以下清單中的 10 個不同語義化元素：
- `<header>`、`<nav>`、`<main>`、`<article>`、`<section>`、`<aside>`、`<footer>`
- `<h1>`、`<h2>`、`<h3>`、`<p>`、`<ul>`、`<li>`、`<a>`
- `<img>`、`<time>`、`<blockquote>`、`<strong>`、`<em>`

### 第三部分：HTML 實作

**按照以下標準編寫您的部落格首頁：**

1. **文件結構**：包含正確的 DOCTYPE、html、head 和 body 元素
2. **語義化標記**：使用 HTML 元素完成其預期用途
3. **可訪問性**：為圖片添加正確的 alt 文本，並使用有意義的連結文字
4. **代碼品質**：使用一致的縮排和有意義的註解
5. **內容**：包含真實的部落格內容（可以使用佔位文字）

**範例 HTML 結構：**
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>My Personal Blog</title>
</head>
<body>
    <!-- Main site header -->
    <header>
        <h1>My Blog Title</h1>
        <nav>
            <!-- Navigation menu -->
        </nav>
    </header>
    
    <!-- Main content area -->
    <main>
        <!-- Blog posts go here -->
    </main>
    
    <!-- Sidebar content -->
    <aside>
        <!-- Additional information -->
    </aside>
    
    <!-- Site footer -->
    <footer>
        <!-- Footer content -->
    </footer>
</body>
</html>
```

### 第四部分：反思

**撰寫簡短的反思（3-5 句），回答以下問題：**
- 您最有信心使用哪些 HTML 元素？
- 在規劃或編碼過程中遇到了哪些挑戰？
- 語義化 HTML 如何幫助組織您的內容？
- 在下一個 HTML 專案中，您會做哪些不同的事情？

## 提交清單

**提交前，請確保您已完成以下事項：**
- [ ] 帶有 HTML 元素標註的視覺模擬版面
- [ ] 完整的 HTML 文件，具有正確的文件結構
- [ ] 至少適當使用 10 個不同的語義化 HTML 元素
- [ ] 有意義的註解，解釋您的代碼結構
- [ ] 有效的 HTML 語法（在瀏覽器中測試）
- [ ] 撰寫反思，回答提示問題

## 評估標準

| 評估標準 | 卓越 (4) | 熟練 (3) | 發展中 (2) | 初學 (1) |
|----------|----------|----------|----------|----------|
| **規劃與設計** | 詳細且標註清晰的模擬版面，顯示對版面和 HTML 語義結構的清楚理解 | 清晰的模擬版面，大部分部分標註適當 | 基本模擬版面，部分標註，顯示一般理解 | 模糊或不清楚的模擬版面，缺乏適當的部分標註 |
| **語義化 HTML 使用** | 適當使用 10 個以上的語義化元素，展現對 HTML 結構和可訪問性的深刻理解 | 正確使用 8-9 個語義化元素，展現對語義化標記的良好理解 | 使用 6-7 個語義化元素，對適當使用有些許困惑 | 使用少於 6 個元素或錯誤使用語義化元素 |
| **代碼品質與組織** | 代碼組織極佳，縮排正確，註解全面，HTML 語法完美 | 代碼組織良好，縮排適當，註解有幫助，語法有效 | 代碼大致組織良好，有一些註解，存在小的語法問題 | 組織差，註解少，存在多個語法錯誤 |
| **可訪問性與最佳實踐** | 可訪問性考量極佳，alt 文本有意義，標題層次正確，遵循所有現代 HTML 最佳實踐 | 良好的可訪問性功能，適當使用標題和 alt 文本，遵循大部分最佳實踐 | 有一些可訪問性考量，基本的 alt 文本和標題結構 | 可訪問性功能有限，標題結構差，未遵循最佳實踐 |
| **反思與學習** | 深刻的反思，展現對 HTML 概念的深刻理解和對學習過程的深入分析 | 良好的反思，展現對關鍵概念的理解和一定的學習自我認知 | 基本的反思，對 HTML 概念或學習過程的洞察有限 | 反思簡短或缺失，顯示對所學概念的理解不足 |

## 學習資源

**基本參考：**
- [MDN HTML 元素參考](https://developer.mozilla.org/docs/Web/HTML/Element) - HTML 元素的完整指南
- [HTML5 語義化元素](https://developer.mozilla.org/docs/Web/HTML/Element#content_sectioning) - 理解語義化標記
- [網頁可訪問性指南](https://www.w3.org/WAI/WCAG21/quickref/) - 創建可訪問的網頁內容
- [HTML 驗證工具](https://validator.w3.org/) - 檢查您的 HTML 語法

**成功的專業提示：**
- 在編寫任何代碼之前先完成模擬版面
- 使用瀏覽器的開發者工具檢查您的 HTML 結構
- 在不同的螢幕尺寸下測試您的頁面（即使不使用 CSS）
- 大聲朗讀您的 HTML，檢查結構是否合乎邏輯
- 考慮螢幕閱讀器如何解讀您的頁面結構

> 💡 **記住**：此作業重點在於 HTML 結構和語義化。不必擔心視覺樣式——這是 CSS 的工作！您的頁面可能看起來很簡單，但它應該結構良好且具有意義。

---

**免責聲明**：  
本文件已使用 AI 翻譯服務 [Co-op Translator](https://github.com/Azure/co-op-translator) 進行翻譯。儘管我們努力確保翻譯的準確性，但請注意，自動翻譯可能包含錯誤或不準確之處。原始文件的母語版本應被視為權威來源。對於關鍵信息，建議使用專業人工翻譯。我們對因使用此翻譯而引起的任何誤解或誤釋不承擔責任。