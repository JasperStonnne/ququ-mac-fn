# 蛐蛐 macOS 魔改说明

## Fn 触发

Electron `globalShortcut` **不能**直接注册单独的 Fn/Globe 键。本 fork 默认热键改为 **F18**，并用 Karabiner-Elements 把 Fn/Globe 映射到 F18，效果等同「按 Fn 开始/停止录音」。

1. 安装 [Karabiner-Elements](https://karabiner-elements.pqrs.org/)
2. 导入 `mods/karabiner-fn-to-f18.json`（Complex Modifications → Add rule）
3. 系统设置里把「按下 🌐 键」设为「无动作」，避免和映射冲突

若以后要做 Wispr 式原生 Fn 长按，需 CGEventTap 原生 helper（未包含在本版）。

## 粘贴

开发模式进程名是 Electron，自动 ⌘V 依赖 osascript→System Events，常遇 TCC 1002。打成 `.app` 后请在「辅助功能」里授权「蛐蛐」。
