# Tap Confirm - 打卡确认工具

一个简洁、克制的移动优先 PWA 打卡应用。

## 📱 设计哲学

这是一个"现实动作确认工具"：

- **克制**：无云同步、无复杂功能
- **快速**：单屏操作、即时反馈
- **无干扰**：本地存储、隐私优先
- **解决焦虑**："我打卡了吗？" → 一眼确认

## ✨ 核心功能

- ✅ 上班/下班打卡（每天各一次，自动锁定）
- ✅ 智能倒计时（根据上班时间自动计算下班时间）
- ✅ 下班提醒（可配置 5/10/15 分钟提前通知）
- ✅ 提前下班模式（应对节假日等特殊场景）
- ✅ 最近 10 条记录查看
- ✅ 完全离线可用
- ✅ 支持深色模式

## 🎯 使用场景

- 弹性工时的上下班打卡记录
- 自动推算下班时间，无需手动计算
- 下班前自动提醒，不错过打卡

## 🛠️ 技术栈

- 原生 HTML/CSS/JavaScript
- PWA (Progressive Web App)
- LocalStorage 本地存储
- Service Worker 离线支持
- Web Notifications API

## 🚀 部署

### Vercel 一键部署

```bash
npm i -g vercel
vercel
```

### 本地运行

```bash
python3 -m http.server 8000
# 或
npx serve
```

访问 `http://localhost:8000`

## 📂 项目结构

```
did-i-clock/
├── index.html          # 主页面（包含样式和逻辑）
├── manifest.json       # PWA 配置
├── sw.js              # Service Worker (离线支持)
├── image/
│   ├── icon-192.png   # 应用图标 192x192
│   └── icon-512.png   # 应用图标 512x512
└── README.md          # 项目说明
```

## 💾 数据结构

### 每日打卡记录
```javascript
// localStorage: dailyRecords
{
  "2026-02-13": {
    clockIn: 1739425920000,      // 上班时间戳
    clockOut: 1739458320000,     // 下班时间戳
    expectedOut: 1739458320000   // 预计下班时间
  }
}
```

### 用户设置
```javascript
// localStorage: settings
{
  reminderMinutes: 5,      // 提前提醒分钟数
  workHours: 9,            // 工作时长（小时）
  earlyLeaveDate: null     // 提前下班日期（仅当天有效）
}
```

## 🌐 浏览器支持

- ✅ Chrome/Edge (Android/Desktop)
- ✅ Safari (iOS/macOS)
- ✅ Firefox
- ⚠️ 需要 HTTPS（本地开发可用 localhost）

## 📝 License

MIT