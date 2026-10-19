# ClaudeCLI-ExplorerMenu
一个没什么用的小工具，可以让你在资源管理器中直接调用claudeCLI，纯懒虫来的

用 Claude CLI 打开 —— 资源管理器右键菜单插件
================================================

功能
----
在任意文件夹的空白处点右键，提供两个入口：
- “用 Claude CLI 打开”：以当前文件夹为工作目录开始新对话。
- “用 Claude CLI 继续上次对话”：恢复该文件夹最近一次对话（claude --continue）。

系统要求
--------
- Windows 10 / Windows 11
- 已安装 Claude Code CLI，并且 claude 命令可用
  未安装可执行：winget install Anthropic.ClaudeCode
- 不需要管理员权限

安装
----
1. 先把压缩包完整解压到任意文件夹（不要在压缩包预览里直接运行）。
2. 双击 install.cmd。
3. 安装程序会自动查找 claude.exe / claude.cmd 的位置，并写入当前用户的注册表。
4. 看到“安装完成”即可。

使用
----
在文件夹空白处点右键：
- Windows 11：选择“显示更多选项”（或按 Shift+F10），即可看到两个菜单项。
- Windows 10：直接出现在右键菜单中。

“继续上次对话”恢复的是该文件夹下最近一次 Claude Code 会话。
如果这个文件夹从未使用过 Claude CLI，请改用“用 Claude CLI 打开”开始新对话。

卸载
----
双击 uninstall.cmd。

说明
----
- 仅写入 HKEY_CURRENT_USER，不修改系统级设置，也不修改 PATH。
- 如果 Claude CLI 的安装位置发生变化（例如换了安装方式），重新运行 install.cmd 即可。
- Windows 11 新版一级右键菜单只能由带签名的 MSIX 扩展添加，
  因此本菜单项位于“显示更多选项”中。
- 首次运行时 Windows 可能提示“已保护你的电脑”（SmartScreen）：
  点击“更多信息 -> 仍要运行”。也可以先用记事本查看 install.ps1 的内容。
- 如果系统禁止运行 PowerShell 脚本，可在 PowerShell 中手动执行：
  powershell -NoProfile -ExecutionPolicy Bypass -File .\install.ps1

