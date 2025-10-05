# 🧩 專案任務可視化 (PERT / CPM / Gantt)

這個頁面示範如何 **不寫任何程式**，只用 GitHub 的 Mermaid 語法，
在 `README.md` 中同時呈現：

1. 📊 PERT / CPM 任務關係圖  
2. 📅 甘特圖 (Gantt Chart)  
3. 🚩 關鍵路徑（Critical Path）以紅色顯示  

---

## 📘 1️⃣ PERT / CPM 任務圖
```mermaid
graph TD
    A[任務A：需求分析]:::critical --> B[任務B：系統設計]:::critical
    B --> C[任務C：程式開發]:::critical
    C --> D[任務D：測試]
    D --> E[任務E：上線]

    %% 樣式設定
    classDef critical fill=#ff9999,stroke=#d33,stroke-width=3px;

gantt
    dateFormat  YYYY-MM-DD
    title 專案開發進度表
    section 規劃階段
    需求分析        :a1, 2025-10-01, 3d
    系統設計        :a2, after a1, 4d
    section 實作階段
    程式開發        :a3, after a2, 7d
    測試階段        :a4, after a3, 4d
    上線部署        :a5, after a4, 2d

graph LR
    A[需求分析]:::critical --> B[系統設計]:::critical --> C[程式開發]:::critical --> D[測試] --> E[上線]
    classDef critical fill=#ffcccc,stroke=#ff0000,stroke-width=3px;
