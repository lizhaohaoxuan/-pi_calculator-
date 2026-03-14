# Pi Calculator for Wii

在 Wii 上计算 π 值的图形化程序，支持 SD 卡保存/读取。

## 功能特性

- 🎮 使用 Wii 遥控器操作
- 📺 图形界面显示（GX 渲染）
- 💾 SD 卡文件读写
- ☁️ 支持 GitHub Codespaces 云端开发

## 云端开发（无需本地配置）

### 使用 GitHub Codespaces（推荐）

1. 点击仓库页面的 **Code** → **Codespaces** → **Create codespace on main**
2. 等待环境初始化（约 2-3 分钟）
3. 在浏览器中直接编写代码
4. 按 `Ctrl+Shift+B` 选择 **Build Wii Project** 构建
5. 构建完成后，下载 `boot.dol` 和 `meta.xml`

### 使用 GitHub Actions

每次推送代码会自动构建，在 Actions 页面下载构建产物。

## 本地开发

### 安装 devkitPro

```bash
# Windows/macOS/Linux 下载安装器
https://devkitpro.org/wiki/Install
```

### 构建

```bash
make
```

## 安装到 Wii

1. 将 SD 卡格式化为 FAT32
2. 创建目录 `apps/pi_calculator/`
3. 复制 `boot.dol` 和 `meta.xml` 到该目录
4. 插入 Wii，通过 Homebrew Channel 运行

## 操作说明

| 按键 | 功能 |
|------|------|
| A | 保存结果到 SD 卡 |
| B | 从 SD 卡读取结果 |
| 1 | 重新计算 |
| HOME | 退出 |

## 技术细节

- 使用 Bailey-Borwein-Plouffe 公式计算 π
- 基于 libogc 和 libfat 开发
- 双缓冲渲染避免闪烁
