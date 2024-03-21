# CVE-2024-21412_Water-Hydra

通过 CVE-2024-21412 传递恶意软件

## usage

依次启动服务，并访问 web server

## webserver

在文件夹内启动 web server: `python -m http.server`
- Initial Access: 使用 Windows 高级查询语法（AQS）链接回 WebDAV 共享的 JPEG 木马。
- Initial Access：使用 search: 协议来自定义 Windows 资源管理器窗口
  - 它使用 search: 应用协议搜索来执行照片搜索
  - 它使用 crumb 参数来限制搜索范围到恶意的 WebDAV 共享。
  - 它使用 DisplayName 元素来欺骗用户，使他们认为这是本地的下载文件夹。

## samba-compose

在文件夹内执行 `docker compose up`
- 使用 crazymax/samba docker 的 samba 服务器

## loader

编写 `a2.cmd` 并压缩为 `a2.zip` 文件，放在 `samba-compose/pictures` 文件夹内
- Execution: 利用 CVE-2024-21412 (ZDI-CAN-23100) 绕过 Microsoft Defender SmartScreen
> CVE-2024-21412 围绕互联网快捷方式。这些.url 文件是简单的 INI 配置文件，它们采用“URL=”参数指向一个 URL。虽然.url 文件格式没有官方文档，但 URL 参数是这种文件类型所必需的唯一参数。
