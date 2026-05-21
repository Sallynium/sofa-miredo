# Miredo 沙發色彩搭配預覽

線上即時預覽沙發布料顏色搭配的靜態工具，部署於 GitHub Pages。

## 功能

- 點選色票，即時預覽坐墊與靠枕的顏色搭配
- 兩個區域獨立選色，可自由組合
- 手機與桌機皆可使用

## 色票來源

| 區域 | 系列 | 數量 |
|------|------|------|
| 坐墊・本體 | 7901 – 7918 | 18 色 |
| 靠枕 | V123-01 – V123-21 | 14 色 |

## 本機開啟

直接用瀏覽器開啟 `index.html` 即可。

> 注意：部分瀏覽器對本機 `file://` 的跨來源限制可能影響圖片載入，建議用 Live Server 或直接看 GitHub Pages 版本。

## 部署（GitHub Pages）

1. 推送至 GitHub repo
2. Settings → Pages → Source 選 `main` branch `/` (root)
3. 等約一分鐘，網址為 `https://<username>.github.io/<repo-name>/`

## 檔案結構

```
/
├── index.html                          # 主程式（單一檔案）
├── 沙發本體分為坐墊與靠枕不同區塊.jpg    # 沙發本體圖
├── 坐墊顏色表.jpg                       # 坐墊布料色票
├── 靠枕顏色表1.jpg                      # 靠枕布料色票（V123-15~21）
├── 靠枕顏色表2.jpg                      # 靠枕布料色票（V123-01~07）
└── README.md
```

## 技術說明

純 HTML + CSS + JS，無任何框架與套件依賴。

換色原理為 SVG 雙層疊色：
1. `mix-blend-mode: saturation` 先將原圖對應區域去飽和度（轉灰階）
2. `mix-blend-mode: color` 再疊上選擇的顏色，保留布料紋理與光影

> 色彩預覽為模擬效果，實際色彩請以布料色票為準。
