# 03. 安全与格式转换

> 📌 **模块分类**：底座与环境设置  
> 💡 **核心定位**：跨平台 Telegram 账号凭据桥梁，实现 TData、Telethon Session、Pyrogram Session、JSON 格式无损双向转换。

---

## 一、解决的核心商业痛点
市场上买到的账号格式各异（有的只有电脑桌面端 TData 文件夹，有的只有 Session），格式不通导致工具无法使用。

---

## 二、界面实战图解
<p align="center">
  <img src="../manual_images/09_设置_安全与格式转换.png" alt="安全与格式转换 界面截图" width="98%" style="border-radius: 8px; box-shadow: 0 4px 16px rgba(0,0,0,0.3);">
</p>

---

## 三、功能特性一览
- 桌面端 TData 转 Telethon .session（秒级提取无需重新接收短信码）
- Telethon Session 与 Pyrogram Session 互转，支持跨开源项目无缝迁移
- 批量提取账号详情元数据并导出为标准 JSON/CSV 清单
- 内置 2FA 两步验证密码批量核验与重设功能

---

## 四、标准实战操作指南
1. 在转换类型中选择「TData 转 Session」或「Session 互转」；
2. 选择包含 TData 文件夹的父级目录或 Session 文件列表；
3. 如果账号带 2FA 两步验证密码，在密码栏填入默认密码或指定映射文件；
4. 点击「开始批量转换」，转换成功的 Session 将自动保存至 output 目录并支持一键直接导入至账号管理池。

---

## 五、工业级防封与实战秘诀
- 从 TData 转换 Session 时，务必确保对应的 Telegram 官方桌面端已完全退出，避免本地 SQLite 锁死；
- 转换完成后建议使用「安全检测」跑一次状态诊断，验证 AuthKey 的持久有效性。

---

<p align="center">
  <a href="../USER_MANUAL.md">⬅️ 返回总目录</a> | <a href="https://github.com/ChiSonKon/tg-sender-releases">🏠 返回项目首页</a>
</p>
