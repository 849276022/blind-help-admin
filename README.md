# 公安调度控制台 Web 前端

## 项目结构
- `index.html`：公安控制台页面
- `config.js`：云托管后端地址与演示开关

## 当前配置
`config.js`：
- `API_BASE_URL`：现有云托管后端地址
- `USE_DEMO_DATA: true`：后端工单接口尚未上线时使用演示数据
- `POLL_INTERVAL_MS: 5000`：每 5 秒读取一次云端工单

## 对接接口约定
- `GET /help-orders`
- `PUT /help-orders/:id/status`，请求体 `{ "status": "assigned|arrived|completed|cancelled", "operator": "调度员" }`

## 部署
这是纯静态 Web 项目，可上传到支持静态站点的平台。部署前请确认后端已配置 CORS，并把 `config.js` 中的 `USE_DEMO_DATA` 改为 `false`。

当前版本尚未执行平台部署，也没有修改云托管配置。
