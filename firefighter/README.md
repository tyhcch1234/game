# 消防英雄 3D · Fire Rescue 3D

一個用 Three.js 製作的 3D 第一人稱消防員救援遊戲。夜晚的舊樓起火，你要在 **180 秒**內撲滅 6 處火頭、救出 3 位被困居民。

**遊玩網址：** https://tyhcch1234.github.io/game/firefighter/

## 玩法

| 操作 | 桌面 | 手機 |
| --- | --- | --- |
| 移動 | WASD / 方向鍵（Shift 加速） | 左下角虛擬搖桿 |
| 環視 | 拖曳畫面；點擊畫面可鎖定滑鼠視角（Esc 解除） | 拖曳畫面 |
| 噴水 | 按住滑鼠左鍵或空白鍵 | 按住「噴水」 |
| 救援 | 走近居民按 E | 按「救援」 |

- 水柱要對準火焰中心，火頭血量歸零即撲熄（+150 分）。
- 居民附近仍有火頭時無法救出，先滅火再救人（+300 分）。
- 太接近火焰會持續受傷（畫面變紅），離開火場數秒後會慢慢回復。
- 水量有限，用完要等水壓回升；連續猛噴會很快見底。
- 全部火頭撲滅 + 全部居民獲救 = 任務完成，剩餘時間每秒 +10 分，另加 500 分完成獎勵。

## 技術

- 單頁 `index.html`，內嵌全部 CSS 與 JavaScript，無建置步驟。
- `vendor/three.module.js`（Three.js r160）本地載入，不依賴 CDN，離線亦可用。
- 所有貼圖（火焰、煙、水珠、瀝青、樓宇外牆、招牌）由 Canvas 程序化生成，無外部圖片素材。
- 音效以 Web Audio API 即時合成（水聲、火聲、警報、撲熄、勝利／失敗音效），無音檔。
- 自訂第一人稱控制器（滑鼠鎖定 + 觸控拖曳 + 虛擬搖桿），支援桌面與手機。
- 火焰以加色混合 Sprite 配合閃爍點光源呈現；水柱為自訂 ShaderMaterial 粒子，具距離衰減與大小上限。

## 本機執行

```bash
python3 -m http.server 8000
# 開啟 http://localhost:8000
```

（需以 HTTP 提供，因為使用 ES Module 與 import map。）

## 檔案

```
index.html              遊戲本體（HTML + CSS + JS）
vendor/three.module.js  Three.js r160
```

## 授權

MIT。Three.js 為 MIT 授權，版權屬 three.js authors。
