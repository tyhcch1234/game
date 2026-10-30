# game · 遊戲收藏

由 AI 製作的網頁遊戲收藏館，每個遊戲都是獨立、免安裝的單頁網頁。

**網站：** https://tyhcch1234.github.io/game/

## 遊戲清單

| 遊戲 | 類型 | 連結 |
| --- | --- | --- |
| 消防英雄 3D（Fire Rescue 3D） | 3D / 動作 | [/game/firefighter/](https://tyhcch1234.github.io/game/firefighter/) |

## 結構

```
index.html          收藏館首頁（讀取 games.json 自動生成卡片）
games.json          遊戲清單（新增遊戲只需在這裡加一筆）
assets/             首頁縮圖
firefighter/        遊戲：消防英雄 3D
  index.html
  vendor/three.module.js
```

## 新增一個遊戲

1. 在根目錄建立 `你的遊戲/index.html`（自帶 CSS/JS 的單頁）。
2. 在 `games.json` 的 `games` 陣列加入：

```json
{
  "title": "遊戲名稱",
  "en": "English Name",
  "desc": "一句話介紹玩法",
  "tags": ["類型", "技術"],
  "date": "2026-11-01",
  "thumb": "./assets/你的縮圖.png",
  "url": "./你的遊戲/"
}
```

3. 更新 `updated` 日期並 push，首頁會自動出現新卡片。

## 授權

MIT。各遊戲內的第三方函式庫依其原授權（Three.js 為 MIT）。
