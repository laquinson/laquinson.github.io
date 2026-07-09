# 🪐 中一數學智能練習系統 (完美星空霧化版)

這是一套專為中一學生設計的跨網頁獨立分流數學智能練習系統。採用同一個 GitHub Repository 下的多檔案獨立分流架構，內建完善的保安閘門與數據儲存機制。

## 🌌 系統視覺與美術風格
- **背景圖片**：採用 Imgur 高清太空壁紙（100% 寬度平鋪展開）`https://i.imgur.com/f118Qxn.jpeg`
- **防禦底色**：`#0b1424`（與圖片邊緣完美融合）
- **全局外觀**：12% 極致半透明輕霧化磨砂玻璃質感 (Glassmorphism)
- **文字優化**：針對暗色背景進行高能見度亮白優化。

## 🏗️ 檔案架構與跳轉邏輯
本專案由四個核心 HTML 檔案組成，彼此各司其職：
1. `index.html`：**系統登入入口**。負責驗證學生/教師身份，紀錄憑證至 `localStorage`，成功後跳轉至大廳。
2. `home.html`：**中央大廳分流首頁**。顯示挑戰者資訊，並提供兩個遊戲模式的傳送門。
3. `Substitution.html`：**多變數代數式求值系統**。包含闖關模式、錯題庫、數據報告與隱形括號逐步破譯教學。
4. `Polynomial.html`：**多項式智能練習系統**。包含多項式化簡與展開，內建田字格分配律操作與逐步黑板程序。

## 🛡️ 保安閘門機制 (Security Gate)
各遊戲檔案與大廳皆內建以下即時抽查機制：
```javascript
(function checkSecurityGate(){
    currentRole = localStorage.getItem("Active_User_Role");
    // 若無憑證，立刻遣返回 index.html 登入頁面
})();
