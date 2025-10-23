<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "c8fc39a014d08247c082878122e2ba73",
  "translation_date": "2025-10-22T22:55:27+00:00",
  "source_file": "6-space-game/1-introduction/assignment.md",
  "language_code": "mo"
}
-->
# 模擬遊戲：應用設計模式

## 作業概述

運用您新學到的設計模式知識，創建一個簡單的遊戲原型！這項作業將幫助您練習架構模式（繼承或組合）以及課程中學到的發布/訂閱通信系統。

## 指導說明

創建一個簡單的遊戲表示，展示本課程中的設計模式。您的遊戲應該是功能性的，但不需要複雜的圖形——重點在於底層架構和通信模式。

### 要求

**選擇您的架構模式：**
- **選項 A**：使用基於類的繼承（例如 `GameObject` → `Movable` → `Hero` 的例子）
- **選項 B**：使用組合（例如使用混合行為的工廠函數方法）

**實現通信：**
- **包含**一個 `EventEmitter` 類，用於發布/訂閱消息
- **設置**至少 2-3 種不同的消息類型（例如 `PLAYER_MOVE`、`ENEMY_SPAWN`、`SCORE_UPDATE`）
- **連接**用戶輸入（鍵盤/鼠標）到通過事件系統的遊戲事件

**遊戲元素需包含：**
- 至少一個玩家控制的角色
- 至少一個其他遊戲物件（敵人、可收集物品或環境元素）
- 物件之間的基本交互（碰撞、收集或通信）

### 建議的遊戲想法

**可考慮的簡單遊戲：**
- **貪吃蛇遊戲**——蛇的身體跟隨蛇頭移動，食物隨機生成
- **乒乓球變體**——球拍響應輸入，球在牆壁上反彈
- **收集者遊戲**——玩家四處移動收集物品，同時避開障礙物
- **塔防基礎**——塔檢測並射擊移動的敵人

### 程式碼結構指南

```javascript
// Example starting structure
const Messages = {
  // Define your game messages here
};

class EventEmitter {
  // Your event system implementation
}

// Choose either class-based OR composition approach
// Class-based example:
class GameObject { /* base properties */ }
class Player extends GameObject { /* player-specific behavior */ }

// OR Composition example:
const gameObject = { /* base properties */ };
const movable = { /* movement behavior */ };
function createPlayer() { /* combine behaviors */ }
```

### 測試您的實現

**驗證您的程式碼是否有效：**
- **測試**物件在事件觸發時是否移動或改變
- **確認**多個物件是否能響應同一事件
- **檢查**是否可以在不修改現有程式碼的情況下添加新行為
- **確保**鍵盤/鼠標輸入能正確觸發遊戲事件

## 提交指南

**您的提交應包括：**
1. **JavaScript 文件**，包含您的遊戲實現
2. **HTML 文件**，用於運行和測試您的遊戲（可以很簡單）
3. **註解**，解釋您選擇的模式及原因
4. **簡要文檔**，描述您的消息類型及其功能

## 評分標準

| 評分標準 | 優秀 (3 分) | 合格 (2 分) | 需改進 (1 分) |
|----------|-------------|-------------|----------------|
| **架構模式** | 正確實現繼承或組合，具有清晰的類/物件層次結構 | 使用選擇的模式，但有輕微問題或不一致 | 嘗試使用模式，但實現存在重大問題 |
| **發布/訂閱實現** | EventEmitter 正常運作，具有多種消息類型和正確的事件流 | 基本的發布/訂閱系統運作，但事件處理有些問題 | 存在事件系統，但運作不可靠 |
| **遊戲功能** | 三個或以上的互動元素通過事件進行通信 | 兩個互動元素具有基本事件通信 | 一個元素響應事件或基本交互 |
| **程式碼質量** | 乾淨、註解清晰的程式碼，邏輯組織良好，使用現代 JavaScript | 程式碼組織良好，註解足夠 | 程式碼可運行，但缺乏組織或清晰註解 |

**加分項目：**
- **創意遊戲機制**，展示設計模式的有趣應用
- **多種輸入方式**（鍵盤和鼠標事件）
- **可擴展的架構**，易於添加新功能

---

**免責聲明**：  
本文件已使用 AI 翻譯服務 [Co-op Translator](https://github.com/Azure/co-op-translator) 進行翻譯。儘管我們努力確保翻譯的準確性，但請注意，自動翻譯可能包含錯誤或不準確之處。原始文件的母語版本應被視為權威來源。對於關鍵信息，建議使用專業人工翻譯。我們對因使用此翻譯而產生的任何誤解或誤釋不承擔責任。