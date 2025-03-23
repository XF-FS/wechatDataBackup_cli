# wechatDataBackup
PC微信聊天记录数据导出工具

[![GitHub stars](https://img.shields.io/github/stars/git-jiadong/wechatDataBackup)](https://github.com/git-jiadong/wechatDataBackup/stargazers)
[![GitHub all releases](https://img.shields.io/github/downloads/git-jiadong/wechatDataBackup/total)](https://github.com/git-jiadong/wechatDataBackup/releases)
[![GitHub release](https://img.shields.io/github/v/release/git-jiadong/wechatDataBackup)](https://github.com/git-jiadong/wechatDataBackup/releases)
[![GitHub last commit](https://img.shields.io/github/last-commit/git-jiadong/wechatDataBackup)](https://github.com/git-jiadong/wechatDataBackup/commits/main)
[![GitHub top language](https://img.shields.io/github/languages/top/git-jiadong/wechatDataBackup)](https://github.com/git-jiadong/wechatDataBackup)
[![GitHub repo size](https://img.shields.io/github/repo-size/git-jiadong/wechatDataBackup)](https://github.com/git-jiadong/wechatDataBackup)
[![GitHub license](https://img.shields.io/github/license/git-jiadong/wechatDataBackup)](https://github.com/git-jiadong/wechatDataBackup/blob/main/LICENSE)

* 基于wails开发 + React前端，实现PC端微信聊天记录一键导出功能
* 支持命令行和图形界面两种操作模式
* 支持选择性备份（基础/完整）
* 导出后数据可以做永久化保存，即使微信停止支持，聊天记录也可以随时查看
* 前端界面尽量与微信界面保持一致，减少使用成本
* 理论上支持所有Windows 32/64位微信版本
* 感谢git-jiadong大佬开源，基础功能都是基于这个大佬的版本进行修改的[跳转链接](https://github.com/git-jiadong/wechatDataBackup)

效果图如下：

![](./res/result.png)
![](./res/result2.png)

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

如果遇到什么问题，或者有更好的建议与优化点欢迎给作者提 [ISSUE](https://github.com/XF-FS/wechatDataBackup_cli/issues)


## Star History

[![Star History Chart](https://api.star-history.com/svg?repos=XF-FS/wechatDataBackup_cli&type=Date)](https://star-history.com/?utm_source=bestxtools.com#XF-FS/wechatDataBackup_cli&Date)

## 免责声明
**⚠️ 本项目仅供学习、研究使用，严禁商业使用**<br/>
**⚠️ 用于网络安全用途的，请确保在国家法律法规下使用**<br/>
**⚠️ 本项目完全免费，问你要钱的都是骗子**<br/>
**⚠️ 使用本项目初衷是作者研究微信数据库的运行使用，您使用本软件导致的后果，包含但不限于数据损坏，记录丢失等问题，作者不承担相关责任。**<br/>
**⚠️ 因软件特殊性质，请在使用时获得微信账号所有人授权，你当确保不侵犯他人个人隐私权，后果自行承担**<br/>

