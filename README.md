# 五城市營業時段天氣與國定假日儀表板

這是一個可直接發布到 GitHub Pages 或 Cloudflare Pages 的靜態網站，不需要資料庫或伺服器程式。

## 發布方式

1. 將此資料夾的全部內容放進 GitHub repository。
2. 在 Cloudflare Pages 選擇該 repository。
3. Framework preset 選擇 `None`，Build command 留白，輸出目錄填 `/`。
4. 完成後，每次 GitHub 更新都會自動重新發布。

如果要讓社群分享預覽圖在所有平台都穩定顯示，發布後可將 `index.html` 內兩個 `og.png` 路徑改成網站的完整網址。

## 國定假日資料

`data/calendar.csv` 為獨立資料源，以 `date` 與天氣資料串接，不修改 `data/weather-hourly.csv`。目前涵蓋 2025-01-01 至 2026-12-31，來源為行政院人事行政總處 2025 修正版及 2026 官方政府行政機關辦公日曆。

網站會顯示國定假日、補假、連假序列、補班日、假期前後日與發薪日 proxy，並可用 Calendar signal 篩選。

## 每日更新

把新的完整彙整檔覆蓋到：

`data/weather-hourly.csv`

欄位名稱需維持：

`date,hour,city,station_id,station_name,rainfall_mm,rainy,measurable_rain,heavy_rain,weather,temp_c,humidity_pct,sunshine_hr`

網站會自動重新計算每日天氣與假日摘要、趨勢圖、逐時雨量熱力圖及排行榜。

預設顯示最近 7 天，也可快速切換最近 3、14、30 天、本月或自行指定日期。日期與城市篩選會同步控制每日天氣摘要、趨勢圖與逐時熱力圖；趨勢圖的城市圖例可直接點擊，以個別顯示或隱藏折線。

