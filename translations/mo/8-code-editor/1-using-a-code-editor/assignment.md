<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "effe56ba51c38d7bdfad1ea38288666b",
  "translation_date": "2025-10-22T22:36:40+00:00",
  "source_file": "8-code-editor/1-using-a-code-editor/assignment.md",
  "language_code": "mo"
}
-->
# 使用 VSCode.dev 建立履歷網站

透過建立一個專業的履歷網站，以互動且現代化的形式展示您的技能和經驗，改變您的職業前景。與其傳送傳統的 PDF 檔案，不如想像一下，您可以提供給招聘人員一個流暢且響應式的網站，既能展示您的資格，也能展現您的網頁開發能力。

這項實作任務將讓您運用所有的 VSCode.dev 技能，並創造出對您的職業生涯真正有用的成果。在瀏覽器中，您將體驗完整的網頁開發工作流程——從建立儲存庫到部署。

完成此專案後，您將擁有一個專業的線上形象，能輕鬆分享給潛在雇主，並隨著技能的提升進行更新，還能根據個人品牌進行自訂。這正是展示真實世界網頁開發技能的實用專案。

## 學習目標

完成此任務後，您將能夠：

- **建立**並管理一個完整的網頁開發專案，使用 VSCode.dev
- **結構化**一個專業網站，使用語義化的 HTML 元素
- **設計**使用現代 CSS 技術的響應式佈局
- **實現**使用基本網頁技術的互動功能
- **部署**一個可透過分享 URL 存取的線上網站
- **展示**在開發過程中遵循版本控制的最佳實踐

## 先決條件

在開始此任務之前，請確保您已完成以下事項：

- 擁有 GitHub 帳戶（如有需要，可在 [github.com](https://github.com/) 建立）
- 完成 VSCode.dev 課程，涵蓋介面導航和基本操作
- 具備 HTML 結構和 CSS 設計概念的基本理解

## 專案設置與儲存庫建立

讓我們從設置您的專案基礎開始。此過程模仿真實世界的開發工作流程，專案通常從適當的儲存庫初始化和結構規劃開始。

### 步驟 1：建立您的 GitHub 儲存庫

設置專用儲存庫可確保您的專案從一開始就得到妥善組織和版本控制。

1. **前往** [GitHub.com](https://github.com) 並登入您的帳戶
2. **點擊**右上角的綠色「New」按鈕或「+」圖示
3. **命名**您的儲存庫為 `my-resume`（或選擇個性化名稱，例如 `john-smith-resume`）
4. **添加**簡短描述：「使用 HTML 和 CSS 建立的專業履歷網站」
5. **選擇**「Public」，使您的履歷對潛在雇主可見
6. **勾選**「Add a README file」，以建立初始專案描述
7. **點擊**「Create repository」完成設置

> 💡 **儲存庫命名提示**：使用描述性且專業的名稱，清楚表明專案的目的。這有助於與雇主分享或進行作品集審查時的展示。

### 步驟 2：初始化專案結構

由於 VSCode.dev 需要至少一個檔案才能開啟儲存庫，我們將直接在 GitHub 上建立主要的 HTML 檔案，然後再切換到網頁編輯器。

1. **點擊**新儲存庫中的「creating a new file」連結
2. **輸入**檔案名稱為 `index.html`
3. **添加**以下初始 HTML 結構：

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Your Name - Professional Resume</title>
</head>
<body>
    <h1>Your Name</h1>
    <p>Professional Resume Website</p>
</body>
</html>
```

4. **撰寫**提交訊息：「添加初始 HTML 結構」
5. **點擊**「Commit new file」保存更改

![在 GitHub 上建立初始檔案](../../../../translated_images/new-file-github.com.c886796d800e8056561829a181be1382c5303da9d902d8b2dd82b68a4806e21f.mo.png)

**以下是此初始設置的作用：**
- **建立**具有語義元素的正確 HTML5 文件結構
- **包含**視窗元標籤以支援響應式設計
- **設置**在瀏覽器標籤中顯示的描述性頁面標題
- **創建**專業內容組織的基礎

## 在 VSCode.dev 中工作

現在您的儲存庫基礎已建立，讓我們切換到 VSCode.dev 進行主要的開發工作。這款基於網頁的編輯器提供了所有專業網頁開發所需的工具。

### 步驟 3：在 VSCode.dev 中開啟您的專案

1. **前往** [vscode.dev](https://vscode.dev) 並開啟新的瀏覽器分頁
2. **點擊**歡迎頁面上的「Open Remote Repository」
3. **複製**您的 GitHub 儲存庫 URL 並貼上到輸入框中

   格式：`https://github.com/your-username/my-resume`
   
   *將 `your-username` 替換為您的實際 GitHub 使用者名稱*

4. **按下** Enter 鍵以載入您的專案

✅ **成功指標**：您應該能在 Explorer 側邊欄中看到您的專案檔案，並在主編輯區域中編輯 `index.html`。

![在 VSCode.dev 中載入專案](../../../../translated_images/project-on-vscode.dev.e79815a9a95ee7feac72ebe5c941c91279716be37c575dbdbf2f43bea2c7d8b6.mo.png)

**您在介面中會看到：**
- **Explorer 側邊欄**：**顯示**您的儲存庫檔案和文件結構
- **編輯區域**：**顯示**所選檔案的內容以供編輯
- **活動欄**：**提供**存取版本控制和擴展功能的途徑
- **狀態欄**：**顯示**連接狀態和當前分支資訊

### 步驟 4：建立您的履歷內容

將 `index.html` 中的佔位內容替換為完整的履歷結構。此 HTML 提供了專業展示您資格的基礎。

<details>
<summary><b>完整的 HTML 履歷結構</b></summary>

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link href="style.css" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.15.4/css/all.min.css">
    <title>Your Name - Professional Resume</title>
</head>
<body>
    <header id="header">
        <h1>Your Full Name</h1>
        <hr>
        <p class="role">Your Professional Title</p>
        <hr>
    </header>
    
    <main>
        <article id="mainLeft">
            <section>
                <h2>CONTACT</h2>
                <p>
                    <i class="fa fa-envelope" aria-hidden="true"></i>
                    <a href="mailto:your.email@domain.com">your.email@domain.com</a>
                </p>
                <p>
                    <i class="fab fa-github" aria-hidden="true"></i>
                    <a href="https://github.com/your-username">github.com/your-username</a>
                </p>
                <p>
                    <i class="fab fa-linkedin" aria-hidden="true"></i>
                    <a href="https://linkedin.com/in/your-profile">linkedin.com/in/your-profile</a>
                </p>
            </section>
            
            <section>
                <h2>SKILLS</h2>
                <ul>
                    <li>HTML5 & CSS3</li>
                    <li>JavaScript (ES6+)</li>
                    <li>Responsive Web Design</li>
                    <li>Version Control (Git)</li>
                    <li>Problem Solving</li>
                </ul>
            </section>
            
            <section>
                <h2>EDUCATION</h2>
                <h3>Your Degree or Certification</h3>
                <p>Institution Name</p>
                <p>Start Date - End Date</p>
            </section>
        </article>
        
        <article id="mainRight">
            <section>
                <h2>ABOUT</h2>
                <p>Write a compelling summary that highlights your passion for web development, key achievements, and career goals. This section should give employers insight into your personality and professional approach.</p>
            </section>
            
            <section>
                <h2>WORK EXPERIENCE</h2>
                <div class="job">
                    <h3>Job Title</h3>
                    <p class="company">Company Name | Start Date – End Date</p>
                    <ul>
                        <li>Describe a key accomplishment or responsibility</li>
                        <li>Highlight specific skills or technologies used</li>
                        <li>Quantify impact where possible (e.g., "Improved efficiency by 25%")</li>
                    </ul>
                </div>
                
                <div class="job">
                    <h3>Previous Job Title</h3>
                    <p class="company">Previous Company | Start Date – End Date</p>
                    <ul>
                        <li>Focus on transferable skills and achievements</li>
                        <li>Demonstrate growth and learning progression</li>
                        <li>Include any leadership or collaboration experiences</li>
                    </ul>
                </div>
            </section>
            
            <section>
                <h2>PROJECTS</h2>
                <div class="project">
                    <h3>Project Name</h3>
                    <p>Brief description of what the project accomplishes and technologies used.</p>
                    <a href="#" target="_blank">View Project</a>
                </div>
            </section>
        </article>
    </main>
</body>
</html>
```
</details>

**自訂指南：**
- **替換**所有佔位文字為您的實際資訊
- **根據**您的經驗水平和職業重點調整各部分
- **根據需要**添加或移除部分（例如：證書、志願者工作、語言能力）
- **包含**指向您實際個人檔案和專案的連結

### 步驟 5：建立支援檔案

專業網站需要有組織的檔案結構。建立 CSS 樣式表和專案所需的配置檔案。

1. **將滑鼠移至** Explorer 側邊欄中的專案文件夾名稱
2. **點擊**出現的「新建檔案」圖示 (📄+)
3. **逐一建立**以下檔案：
   - `style.css`（用於樣式和佈局）
   - `codeswing.json`（用於預覽擴展配置）

**建立 CSS 檔案 (`style.css`)：**

<details>
<summary><b>專業 CSS 樣式設計</b></summary>

```css
/* Modern Resume Styling */
body {
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    font-size: 16px;
    line-height: 1.6;
    max-width: 960px;
    margin: 0 auto;
    padding: 20px;
    color: #333;
    background-color: #f9f9f9;
}

/* Header Styling */
header {
    text-align: center;
    margin-bottom: 3em;
    padding: 2em;
    background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
    color: white;
    border-radius: 10px;
    box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
}

h1 {
    font-size: 3em;
    letter-spacing: 0.1em;
    margin-bottom: 0.2em;
    font-weight: 300;
}

.role {
    font-size: 1.3em;
    font-weight: 300;
    margin: 1em 0;
}

/* Main Content Layout */
main {
    display: grid;
    grid-template-columns: 35% 65%;
    gap: 3em;
    margin-top: 3em;
    background: white;
    padding: 2em;
    border-radius: 10px;
    box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
}

/* Typography */
h2 {
    font-size: 1.4em;
    font-weight: 600;
    margin-bottom: 1em;
    color: #667eea;
    border-bottom: 2px solid #667eea;
    padding-bottom: 0.3em;
}

h3 {
    font-size: 1.1em;
    font-weight: 600;
    margin-bottom: 0.5em;
    color: #444;
}

/* Section Styling */
section {
    margin-bottom: 2.5em;
}

#mainLeft {
    border-right: 1px solid #e0e0e0;
    padding-right: 2em;
}

/* Contact Links */
section a {
    color: #667eea;
    text-decoration: none;
    transition: color 0.3s ease;
}

section a:hover {
    color: #764ba2;
    text-decoration: underline;
}

/* Icons */
i {
    margin-right: 0.8em;
    width: 20px;
    text-align: center;
    color: #667eea;
}

/* Lists */
ul {
    list-style: none;
    padding-left: 0;
}

li {
    margin: 0.5em 0;
    padding: 0.3em 0;
    position: relative;
}

li:before {
    content: "▸";
    color: #667eea;
    margin-right: 0.5em;
}

/* Work Experience */
.job, .project {
    margin-bottom: 2em;
    padding-bottom: 1.5em;
    border-bottom: 1px solid #f0f0f0;
}

.company {
    font-style: italic;
    color: #666;
    margin-bottom: 0.5em;
}

/* Responsive Design */
@media (max-width: 768px) {
    main {
        grid-template-columns: 1fr;
        gap: 2em;
    }
    
    #mainLeft {
        border-right: none;
        border-bottom: 1px solid #e0e0e0;
        padding-right: 0;
        padding-bottom: 2em;
    }
    
    h1 {
        font-size: 2.2em;
    }
    
    body {
        padding: 10px;
    }
}

/* Print Styles */
@media print {
    body {
        background: white;
        color: black;
        font-size: 12pt;
    }
    
    header {
        background: none;
        color: black;
        box-shadow: none;
    }
    
    main {
        box-shadow: none;
    }
}
```
</details>

**建立配置檔案 (`codeswing.json`)：**

```json
{
    "scripts": [],
    "styles": []
}
```

**理解 CSS 功能：**
- **使用** CSS Grid 建立響應式、專業的佈局結構
- **實現**現代配色方案，包含漸層標題
- **包含**懸停效果和流暢過渡，增強互動性
- **提供**適用於所有設備尺寸的響應式設計
- **添加**適合列印的樣式，用於生成 PDF

### 步驟 6：安裝和配置擴展

擴展功能能夠提升您的開發體驗，提供即時預覽功能和改進的工作流程工具。CodeSwing 擴展對於網頁開發專案特別有用。

**安裝 CodeSwing 擴展：**

1. **點擊**活動欄中的擴展圖示 (🧩)
2. **在市場搜索框中搜索**「CodeSwing」
3. **從搜索結果中選擇** CodeSwing 擴展
4. **點擊**藍色「Install」按鈕

![安裝 CodeSwing 擴展](../../../../8-code-editor/images/install-extension.gif)

**CodeSwing 提供的功能：**
- **啟用**在編輯時即時預覽您的網站
- **顯示**變更，無需手動刷新
- **支援**包括 HTML、CSS 和 JavaScript 在內的多種檔案類型
- **提供**整合的開發環境體驗

**安裝後的即時效果：**
安裝 CodeSwing 後，您將看到履歷網站的即時預覽出現在編輯器中。這讓您能夠在進行更改時即時查看網站的外觀。

![CodeSwing 擴展顯示即時預覽](../../../../translated_images/after-codeswing-extension-pb.0ebddddcf73b550994947a9084e35e2836c713ae13839d49628e3c764c1cfe83.mo.png)

**理解增強的介面：**
- **分屏視圖**：**顯示**一側的程式碼和另一側的即時預覽
- **即時更新**：**立即反映**您輸入的變更
- **互動式預覽**：**允許**測試連結和互動功能
- **移動模擬**：**提供**響應式設計測試功能

### 步驟 7：版本控制與發布

現在您的履歷網站已完成，使用 Git 保存您的工作並使其在線上可用。

**提交您的更改：**

1. **點擊**活動欄中的版本控制圖示 (🌿)
2. **檢查**「Changes」部分中您創建和修改的所有檔案
3. **通過點擊**每個檔案旁的「+」圖示來暫存更改
4. **撰寫**描述性提交訊息，例如：
   - 「添加完整的履歷網站，具有響應式設計」
   - 「實現專業的樣式和內容結構」
5. **點擊**勾選 (✓) 以提交並推送您的更改

**有效的提交訊息範例：**
- 「添加專業履歷內容和樣式」
- 「實現響應式設計，適用於移動設備」
- 「更新聯繫資訊和專案連結」

> 💡 **專業提示**：良好的提交訊息有助於追蹤專案的演變，並展示細心的工作態度——這是雇主非常看重的品質。

**存取您的已發布網站：**
提交後，您可以使用左上角的漢堡菜單 (☰) 返回您的 GitHub 儲存庫。您的履歷網站現在已進行版本控制並準備好進行部署或分享。

## 結果與下一步

**恭喜！🎉** 您已成功使用 VSCode.dev 建立了一個專業的履歷網站。您的專案展示了以下內容：
**展示的技術技能：**
- **儲存庫管理**：建立並組織完整的專案結構
- **網頁開發**：使用現代 HTML5 和 CSS3 建立響應式網站
- **版本控制**：實施正確的 Git 工作流程，並撰寫有意義的提交訊息
- **工具熟練度**：有效使用 VSCode.dev 的介面和擴展系統

**達成的專業成果：**
- **線上形象**：一個可分享的 URL，展示您的資格
- **現代格式**：傳統 PDF 履歷的互動替代方案
- **可展示的技能**：具體證明您的網頁開發能力
- **輕鬆更新**：一個可持續改進和自訂的基礎

### 部署選項

為了讓您的履歷能被雇主存取，請考慮以下主機選項：

**GitHub Pages（推薦）：**
1. 前往 GitHub 上您的儲存庫設定
2. 滾動到「Pages」部分
3. 選擇「Deploy from a branch」，並選擇「main」
4. 您的網站將可在 `https://your-username.github.io/my-resume` 存取

**其他平台：**
- **Netlify**：自動部署，支援自訂域名
- **Vercel**：快速部署，提供現代化主機功能
- **GitHub Codespaces**：內建預覽的開發環境

### 增強建議

透過添加以下功能，繼續提升您的技能：

**技術改進：**
- **JavaScript 互動性**：添加流暢滾動或互動元素
- **深色模式切換**：實現用戶偏好的主題切換
- **聯繫表單**：啟用潛在雇主的直接溝通
- **SEO 優化**：添加元標籤和結構化數據，以提高搜索可見性

**內容增強：**
- **專案作品集**：連結到 GitHub 儲存庫和線上展示
- **技能可視化**：創建進度條或技能評分系統
- **推薦部分**：包含同事或導師的推薦
- **部落格整合**：添加部落格部分，展示您的學習歷程

## GitHub Copilot Agent 挑戰 🚀

使用 Agent 模式完成以下挑戰：

**描述：** 使用進階功能增強您的履歷網站，展示專業的網頁開發能力和現代設計原則。

**挑戰內容：** 在現有的履歷網站基礎上，實現以下進階功能：
1. 添加深色/淺色主題切換，並具有流暢過渡效果
2. 創建互動式技能部分，包含動畫進度條
3. 實現具有表單驗證的聯繫表單
4. 添加專案作品集部分，包含懸停效果和模態彈窗
5. 包括部落格部分，至少包含 3 篇關於您的學習歷程的範例文章
6. 使用適當的元標籤、結構化數據和性能優化進行 SEO 優化
7. 使用 GitHub Pages 或 Netlify 部署增強版網站
8. 在您的 README.md 中記錄所有新功能，並附上截圖

您的增強版網站應展示現代網頁開發實踐的掌握，包括響應式設計、JavaScript 互動性和專業的部署工作流程。

## 挑戰延伸

準備好進一步提升您的技能了嗎？嘗試以下進階挑戰：

**📱 移動優先重新設計：** 使用 CSS Grid 和 Flexbox 徹底重建您的網站，採用移動優先的設計方法

**🔍 SEO 優化：** 實現全面的 SEO，包括元標籤、結構化數據和性能優化

**🌐 多語言支援：** 添加國際化功能，支援多種語言

**📊 分析整合：** 添加 Google Analytics，追蹤訪客參與度並優化您的內容

**🚀 性能優化：** 在所有類別中達到完美的 Lighthouse 分數

## 回顧與自學

透過以下資源擴展您的知識：

**進階 VSCode.dev 功能：**
- [VSCode.dev 文件](https://code.visualstudio.com/docs/editor/vscode-web?WT.mc_id=academic-0000-alfredodeza) - 網頁編輯的完整指南
- [GitHub Codespaces](https://docs.github.com/en/codespaces) - 雲端開發環境

**網頁開發最佳實踐：**
- **響應式設計**：學習 CSS Grid 和 Flexbox，打造現代化佈局
- **無障礙性**：學習WCAG指南以設計包容性網頁  
- **效能**：探索像Lighthouse這樣的工具進行優化  
- **SEO**：了解搜索引擎優化的基本原理  

**職業發展：**  
- **作品集建立**：創建更多項目以展示多樣化技能  
- **開源**：參與現有項目以獲得協作經驗  
- **人脈建立**：在開發者社群中分享你的履歷網站以獲得反饋  
- **持續學習**：保持對網頁開發趨勢和技術的更新  

---

**你的下一步：**  
將你的履歷網站分享給朋友、家人或導師以獲得反饋。根據他們的建議進行迭代和改進設計。記住，這個項目不僅僅是一份履歷——它是你作為網頁開發者成長的展示！

---

**免責聲明**：  
本文件已使用 AI 翻譯服務 [Co-op Translator](https://github.com/Azure/co-op-translator) 進行翻譯。雖然我們致力於提供準確的翻譯，但請注意，自動翻譯可能包含錯誤或不準確之處。原始文件的母語版本應被視為權威來源。對於關鍵信息，建議使用專業人工翻譯。我們對因使用此翻譯而引起的任何誤解或誤釋不承擔責任。