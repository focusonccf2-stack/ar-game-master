# 接住魔王的小魔雲！（AR 網頁遊戲）

用手機瀏覽器就能玩的 AR 小遊戲：魔王站在畫面中央，用雙手丟出紫色小魔雲，玩家伸出雙手在鏡頭前把魔雲接住；漏接就會被攻擊、扣一顆心。

## 玩法
- **自己玩（前鏡頭）**：把手機立起來，人站遠一點，讓雙手都在畫面中。
- **朋友幫拍（後鏡頭）**：一人拿手機對著玩家，玩家用雙手接。
- 開始時魔王固定在畫面正中央（世界錨點）。轉動手機時魔王會留在原地；魔王離開畫面時，邊緣會出現紫色箭頭指出魔王的方向。
- 🎯 把魔王重新放回畫面中央；🔄 切換前／後鏡頭；🔊 音效開關。
- 一隻手接住 +1，雙手一起接住 +2；每接 8 朵升一級，魔王丟得更快，也會雙手同時丟。
- 5 顆心，全部扣完遊戲結束。最高分會記在這支手機的瀏覽器裡。

## 技術
- 相機畫面：`getUserMedia`
- 魔王固定位置：手機陀螺儀（`deviceorientation`），3DoF 旋轉追蹤
- 手部辨識：Google MediaPipe Hand Landmarker（從 CDN 載入）
- 3D 繪製：three.js（從 CDN 載入）
- 若手部辨識模型載入失敗，會自動改成「點魔雲」也能接住

## 放上 GitHub Pages
1. 在 GitHub 建立新的 repository（例如 `ar-demon-game`），設成 Public。
2. 把 `index.html`、`demon.png`、`README.md` 上傳到 repository 根目錄（Add file → Upload files）。
3. 到 **Settings → Pages**，Source 選 **Deploy from a branch**，Branch 選 `main`、資料夾 `/ (root)`，按 Save。
4. 約 1 分鐘後，網址會是 `https://<你的帳號>.github.io/ar-demon-game/`，用手機開啟即可。

> 相機與陀螺儀都必須在 **https** 網址下才能使用；GitHub Pages 預設就是 https。
> iPhone 請用 Safari 開啟，第一次會跳出「動作與方向」權限，請按允許。
