# 🧩 拼图游戏 PWA

**阶段：v1 可用** | 下个里程碑：部署到 GitHub Pages

把照片拆成碎片再拼回来的手机拼图游戏。PWA 实现，添加到桌面即用，无广告。

## 怎么用

1. 手机 Chrome 打开链接
2. 选照片 → 选难度 → 开始
3. 拖动碎片到拼图板上对应位置，接近自动吸附
4. 拼完弹庆祝动画
5. 点浏览器菜单 → "添加到主屏幕" → 桌面出现图标

## 文件

| 文件 | 说明 |
|------|------|
| [index.html](index.html) | [已实现] 主应用，含全部游戏逻辑、CSS、Canvas 渲染、触摸交互 |
| [manifest.json](manifest.json) | [已实现] PWA 清单（全屏/图标/名称） |
| [sw.js](sw.js) | [已实现] Service Worker（离线缓存） |
| icon-192.png / icon-512.png | [已实现] PWA 图标 |

## 技术

- 纯 HTML/CSS/JS，零依赖
- Canvas 渲染 jigsaw 碎片（简化版边缘凸起）
- Touch Events 移动端拖拽 + Mouse Events 桌面兼容
- Web App Manifest + Service Worker = PWA
- localStorage 可扩展（v1 未做进度持久化）

## 本地测试

```bash
cd jigsaw-puzzle-pwa
python -m http.server 3456
# 手机连同一 WiFi，访问 http://<电脑IP>:3456
```

## 部署（推荐 GitHub Pages）

```bash
git init && git add . && git commit -m "feat: jigsaw puzzle PWA v1"
git remote add origin <your-repo-url>
git push -u origin main
# Settings → Pages → Source: main branch → Save
```

## 演化日志

- **2026-06-09 v1** — 初始版本：照片上传、3 种难度、jigsaw 碎片渲染、触摸拖拽、吸附、计时器、步数、胜利动画、PWA 离线支持
