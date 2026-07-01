# VSCode 开发 uni-app 环境配置

## 1. 环境配置

HBuilderX-cli 会自动检测已启动的 HBuilderX 进程，无需额外配置。

如果自动检测失败，可以设置环境变量：

**macOS / Linux**

```bash
export HBUILDERX_CLI_PATH="/Applications/HBuilderX.app/Contents/MacOS/cli"
```

**Windows**

```powershell
set HBUILDERX_CLI_PATH="C:\Program Files\HBuilderX\cli.exe"
```

---

## 2. 安装依赖包

```powershell
npm install @dcloudio/hbuilderx-cli --save-dev
```

安装后 `package.json` 中会新增：

```json
"devDependencies": {
  "@dcloudio/hbuilderx-cli": "^1.2.0"
}
```

---

## 3. 配置 npm 命令

在 `package.json` 的 `scripts` 中添加：

```json
"scripts": {
  "dev:web":            "uni-launch web --browser Chrome",
  "dev:app-android":    "uni-launch app-android",
  "dev:app-ios":        "uni-launch app-ios --iosTarget simulator",
  "dev:mp-weixin":      "uni-launch mp-weixin --runtime-log true",

  "logcat:web":         "uni-logcat web",
  "logcat:app-android": "uni-logcat app-android",
  "logcat:mp-weixin":   "uni-logcat mp-weixin"
}
```

**常用命令：**

| 命令 | 说明 |
|------|------|
| `npm run dev:web` | 启动 Web 端开发 |
| `npm run dev:app-android` | 启动 Android 端开发 |
| `npm run dev:mp-weixin` | 启动微信小程序开发 |
| `npm run logcat:web` | 查看 Web 端运行日志 |

---

## 4. 版本注意事项

| 功能 | 最低要求 |
|------|----------|
| HBuilderX 版本 | ≥ 4.87 |
| `uni-launch` 命令 | HBuilderX ≥ 5.0 |
| `uni-logcat` 命令 | HBuilderX ≥ 4.87 |
| Node.js | ≥ 12 |

---

## 5. 故障排除

**找不到 HBuilderX**

```bash
# 确保 HBuilderX 已启动，或设置环境变量
export HBUILDERX_CLI_PATH="/path/to/hbuilderx/cli"
```

**HBuilderX 版本过低**

```bash
# 检查 HBuilderX 版本
cli --version
```

部分功能需要 HBuilderX **4.87** 或更高版本，请更新到最新版本。

---

## 6. 参考链接

- [npm 包](https://www.npmjs.com/package/@dcloudio/hbuilderx-cli)
- [CLI 文档](https://hx.dcloud.net.cn/cli/README)
- [GitHub](https://github.com/dcloudio/hbuilderx-cli)
