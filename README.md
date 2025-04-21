# wechatDataBackup
PC微信聊天记录数据导出工具

[![GitHub stars](https://img.shields.io/github/stars/XF-FS/wechatDataBackup_cli)](https://github.com/XF-FS/wechatDataBackup_cli/stargazers)
[![GitHub all releases](https://img.shields.io/github/downloads/XF-FS/wechatDataBackup_cli/total)](https://github.com/XF-FS/wechatDataBackup_cli/releases)
[![GitHub release](https://img.shields.io/github/v/release/XF-FS/wechatDataBackup_cli)](https://github.com/XF-FS/wechatDataBackup_cli/releases)
[![GitHub last commit](https://img.shields.io/github/last-commit/XF-FS/wechatDataBackup_cli)](https://github.com/XF-FS/wechatDataBackup_cli/commits/main)
[![GitHub top language](https://img.shields.io/github/languages/top/XF-FS/wechatDataBackup_cli)](https://github.com/XF-FS/wechatDataBackup_cli)
[![GitHub repo size](https://img.shields.io/github/repo-size/XF-FS/wechatDataBackup_cli)](https://github.com/XF-FS/wechatDataBackup_cli)
[![GitHub license](https://img.shields.io/github/license/XF-FS/wechatDataBackup_cli)](https://github.com/XF-FS/wechatDataBackup_cli/blob/main/LICENSE)

* 这个工具是二开后用于授权的攻防项目，因为可获取的东西太多了，感觉直接发布有点风险，需要使用可以在Issues中留下邮箱，我会给你发邮件通过审核后方可使用,**请在使用时获得微信账号所有人授权，你当确保不侵犯他人个人隐私权，后果自行承担,因导出记录导致的封号本人不承担任何责任**
* 基于wails开发 + React前端，实现PC端微信聊天记录一键导出功能
* 支持命令行和图形界面两种操作模式
* 支持选择性备份（基础/完整）
* 导出后数据可以做永久化保存，即使微信停止支持，聊天记录也可以随时查看
* 前端界面尽量与微信界面保持一致，减少使用成本
* 理论上支持所有Windows 32/64位微信版本
* 感谢git-jiadong大佬开源，基础功能都是基于这个大佬的版本进行修改的[跳转链接](https://github.com/git-jiadong/wechatDataBackup)

效果图如下：

![PixPin_2025-03-23_12-29-28](https://github.com/user-attachments/assets/a97c0bb6-0eab-4eff-9d22-30875e8831d8)

![PixPin_2025-03-23_12-26-43](https://github.com/user-attachments/assets/bdc65206-7f26-4ffe-ad76-f985cf691472)

![PixPin_2025-03-23_12-27-52](https://github.com/user-attachments/assets/318863b9-ad8f-48df-bb1a-1202651f2d67)


## 声明
1. ⚠️ 本项目仅供学习、研究使用，严禁商业使用
2. ⚠️ 用于网络安全用途的，请确保在国家法律法规下使用
3. ⚠️ 本项目完全免费，问你要钱的都是骗子
4. ⚠️ 使用本项目初衷是作者研究微信数据库的运行使用，您使用本软件导致的后果，包含但不限于数据损坏，记录丢失等问题，作者不承担相关责任。
5. ⚠️ 因软件特殊性质，请在使用时获得微信账号所有人授权，你当确保不侵犯他人个人隐私权，后果自行承担

## 读取导出数据
1. 从 GitHub 获取源码参考：[wechatDataBackup 开源项目](https://github.com/git-jiadong/wechatDataBackup)
2. 确保已安装 wechatDataBackup_cli.exe 工具

## 读取导出数据使用流程

### 方法一：直接导出使用
1. 运行 `wechatDataBackup_cli.exe` 导出数据，会生成 `wxid_xxx.zip` 文件
2. 解压该 zip 文件，找到其中的 `Msg` 文件夹
3. 将解压出的 `wxid_xxx` 文件夹复制到 `\app\Database\Msg\` 目录下

### 方法二：替换已有数据（推荐）
1. 先使用工具抓取一次您当前登录微信的记录（这会在 `\app\Database\Msg\` 生成正确的目录结构）
2. 解压导出的 `wxid_xxx.zip` 文件
3. 用解压出的 `Msg` 文件夹内容替换 `\app\Database\Msg\wxid_xxx` 中的内容
   - 注意：`Multi` 文件夹包含聊天记录，如不需要可不复制

## 常见问题解决
- **如果无法读取数据**：
  1. 先使用工具抓取一次当前微信记录
  2. 再按照上述方法替换文件
  3. 确保目录结构为：`\app\Database\Msg\wxid_xxx\...`

## 注意事项
1. 操作前建议备份原始数据
2. 确保微信已退出再进行数据操作
3. 如遇问题，重复"先抓取再替换"的步骤通常能解决

## 高级说明
- 工具图形化界面可通过添加参数启动
- 源码与开源版本基本一致，仅入口调用部分有所调整


## 使用方法

### 命令行模式
```shell
# 基础备份（仅聊天记录、头像和账号信息）
./wechatDataBackup

# 完整备份（包含所有文件）
./wechatDataBackup -file

# 指定输出目录
./wechatDataBackup -output /path/to/backup [-file]
```

### 图形界面模式
```shell
# 启动图形界面
./wechatDataBackup -gui

# 加载已备份的数据
./wechatDataBackup -gui -load /path/to/backup/wxid_xxx
```


## 功能特点

基础备份包含：
- 聊天记录数据库
- 用户头像
- 账号信息

完整备份额外包含：
- 图片消息
- 视频消息
- 语音消息
- 文件消息
- 其他多媒体内容

本项目目前的规划与实现进度：
- [x] 支持图片消息
- [x] 支持视频消息
- [x] 支持链接消息
- [x] 支持语音消息
- [x] 支持文件消息
- [x] 支持名片消息
- [x] 支持定位消息
- [x] 支持视频/语音通话消息
- [x] 支持QQ音乐消息
- [x] 支持第三方视频软件分享消息
- [x] 支持分享表情集消息
- [x] 支持小程序消息
- [x] 支持视频号/直播消息
- [x] 支持转账消息
- [x] 支持腾讯游戏分享消息
- [x] 支持原始表情显示
- [x] 支持按类型检索
- [x] 支持日期检索
- [x] 支持按群成员检索
- [x] 支持增量式导出
- [x] 多开账号选择导出
- [x] 多开账号数据切换
- [x] 头像使用本地头像
- [ ] 支持更多消息类型显示
- [x] 图片查看器重绘
- [x] 支持会话导出分享
- [x] 支持自动定位到最后浏览位置
- [x] 支持书签功能
- [x] 支持单聊会话对话人位置调换功能
- [ ] 显示联系人微信号，备注

如果遇到什么问题，或者有更好的建议与优化点欢迎给作者提 [ISSUE](https://github.com/XF-FS/wechatDataBackup_cli/issues)


## Star History

[![Star History Chart](https://api.star-history.com/svg?repos=XF-FS/wechatDataBackup_cli&type=Date)](https://star-history.com/?utm_source=bestxtools.com#XF-FS/wechatDataBackup_cli&Date)

## 免责声明
**⚠️ 本工具仅用于授权的企业安全建设**<br/>
**⚠️ 使用本工具时需确保符合当地法律法规**<br/>
**⚠️ 使用本工具造成的任何非法后果由使用者承担**<br/>
**⚠️ 使用本工具即视为同意本免责声明**<br/>
**⚠️ 本工具仅能在取得足够合法授权的企业安全建设中使用，在使用本工具过程中，您应确保自己所有行为符合当地的法律法规。**<br/>
**⚠️ 如您在使用本工具的过程中存在任何非法行为，您将自行承担所有后果，本工具所有开发者和所有贡献者不承担任何法律及连带责任。**<br/>
**⚠️ 除非您已充分阅读、完全理解并接受本协议所有条款，否则，请您不要安装并使用本工具。**<br/>
**⚠️ 您的使用行为或者您以其他任何明示或者默示方式表示接受本协议的，即视为您已阅读并同意本协议的约束。**<br/>

