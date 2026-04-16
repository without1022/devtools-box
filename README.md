# 开发工具箱

一个纯前端的开发者工具集合，单 HTML 文件，无需后端，无需构建。

## 工具列表

| 分类 | 工具 |
|---|---|
| 编码转换 | Base64、URL 编码、HTML 实体、Hex 转换、Unicode |
| 格式化 | JSON 格式化/压缩/校验、时间戳转换 |
| 加密哈希 | MD5 / SHA-1 / SHA-256 / SHA-512 |
| 生成器 | UUID v4、随机密码、二维码 |
| 文本处理 | 正则测试（实时高亮）、文本对比（Diff）、文本工具（大小写/去重/排序） |
| 小工具 | 世界时钟、秒表（支持全屏投屏）、颜色转换 |

## 部署方式

### 本地运行

直接用浏览器打开 `index.html` 即可，无需任何服务器。

> 注意：Hash 计算用到 `crypto.subtle`，本地 `file://` 协议下可能受限，建议用简单 HTTP 服务器：
> ```bash
> # Python
> python3 -m http.server 8080
> # Node.js
> npx serve .
> ```

### Vercel 部署

直接 fork 后在 [Vercel](https://vercel.com) 导入仓库，Framework 选 **Other**，无需任何配置，点 Deploy 即可。

### Nginx / 任意静态服务器

```nginx
location /tools/ {
    root /path/to/devtools-box;
    index index.html;
}
```

## 隐私

所有计算均在本地浏览器完成，没有任何数据上传到服务器。  
唯一的外部请求：二维码生成时从 jsDelivr CDN 动态加载 `qrcode.min.js`（仅首次使用）。
