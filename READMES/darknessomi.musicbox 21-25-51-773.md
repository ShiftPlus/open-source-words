netease musicbox 感谢为 musicbox 的开发付出过努力的每一个人！ 高品质网易云音乐命令行版本，简洁优雅，丝般顺滑，基于python编写。 功能特性 320kbps的高品质音乐 歌曲，艺术家，专辑检索 网易22个歌曲排行榜 网易新碟推荐 网易精选歌单 网易主播电台 私人歌单，每日推荐 随心打碟 本地收藏，随时加❤ 播放进度及播放模式显示 现在播放及桌面歌词显示 歌曲评论显示 一键进入歌曲专辑 定时退出 vimer式快捷键让操作丝般顺滑 可使用数字快捷键 可使用自定义全局快捷键 键盘快捷键 j down 下移 k up 上移 h back 后退 l forword 前进 u prev page 上一页 d next page 下一页 f search 快速搜索 prev song 上一曲 next song 下一曲 volume 音量增加 volume 音量减少 space play pause 播放 暂停 shuffle 手气不错 m menu 主菜单 p present history 当前 历史播放列表 i music info 当前音乐信息 ⇧ p playing mode 播放模式切换 a add 添加曲目到打碟 ⇧ a enter album 进入专辑 g to the first 跳至首项 ⇧ g to the end 跳至尾项 z dj list 打碟列表 s star 添加到收藏 c collection 收藏列表 r remove 删除当前条目 ⇧ j move down 向下移动当前项目 ⇧ k move up 向上移动当前项目 ⇧ c cache 缓存歌曲到本地 like 喜爱 trash fm 删除 fm next fm 下一fm q quit 退出 t timing exit 定时退出 w quit clear 退出并清除用户信息 pypi安装（推荐） pip 3 install netease musicbox git clone最新版 git clone https github com darknessomi musicbox git cd musicbox python 3 setup py install macos安装 pip 3 install netease musicbox brew install mpg123 linux安装 fedora 首先添加fzug源，然后sudo dnf install musicbox（通过此方法安装可能仍然需要pip install netease musicbox更新到最新版）。 ubuntu debian sudo pip install netease musicbox sudo apt get install mpg123 arch linux pacaur s netease musicbox git or yaourt musicbox 依赖 必选 mpg123 用于播放歌曲 可选 aria2 用于缓存歌曲 libnotify bin 用于支持消息提示（linux平台） pyqt python dbus dbus qt 用于支持桌面歌词 mac 用户需要 brew install qt with dbus 获取支持 dbus 的 qt 配置文件 配置文件地址 netease musicbox config json 可配置缓存，快捷键，消息，桌面歌词。 由于歌曲 api 只接受中国大陆地区访问，港澳台及海外用户请自行设置代理： bash export http proxy http ip port curl ip cn 显示ip属于中国大陆地区即可。 已测试的系统兼容列表 macos 10 13 10 12 10 11 ubuntu 14 04 kali 1 1 0 2 0 rolling centos 7 opensuse 13 2 fedora 22 arch rolling 错误处理 当某些歌曲不能播放时，总时长为 00 01 时，请检查是否为版权问题导致。 如遇到在特定终端下不能播放问题，首先检查此终端下mpg123能否正常使用，其次检查其他终端下musicbox能否正常使用，报告issue的时候请告知以上使用情况以及出问题终端的报错信息。 同时，您可以通过tail f netease musicbox musicbox log自行查看日志。 已知问题及解决方案 374 i3wm下播放杂音或快进问题，此问题常见于arch linux。尝试更改mpg123配置。 405 32位python下cookie时间戳超出了32位整数最大值。尝试使用64位版本的python或者拷贝cookie文件到对应位置。 347 暂停时间超过一定长度（数分钟）之后mpg123停止输出，导致切换到下一首歌。此问题是mpg123的bug，暂时无解决方案。 使用 musicbox enjoy it 更新日志 2018 06 21 版本 0 2 5 3 修复多处播放错误 2018 06 07 版本 0 2 5 1 修复配置文件错误 2018 06 05 版本 0 2 5 0 全部迁移到新版api，大量错误修复 2018 05 21 版本 0 2 4 3 更新依赖，错误修复 2017 11 28 版本 0 2 4 2 更新获取歌曲列表的api 2017 06 03 版本 0 2 4 1 修正mpg123状态异常导致的cpu占用，增加歌词双行显示功能 2017 03 17 版本 0 2 4 0 修复通知可能造成的崩溃 2017 03 03 版本 0 2 3 9 邮箱用户登录修复 2017 03 02 版本 0 2 3 8 登录接口修复 2016 11 24 版本 0 2 3 7 新增背景色设置 2016 11 07 版本 0 2 3 6 已知错误修复 2016 10 16 版本 0 2 3 5 新增进入歌曲专辑功能 2016 10 13 版本 0 2 3 4 新增查看歌曲评论 2016 09 26 版本 0 2 3 3 keybinder 错误修复 2016 09 15 版本 0 2 3 2 已知错误修复 2016 09 12 版本 0 2 3 1 已知错误修复 2016 09 11 版本 0 2 3 0 python 2 和 3 支持 2016 05 09 版本 0 2 2 10 修复最后一行歌名过长的问题 2016 05 08 版本 0 2 2 9 缓存问题修复 2016 05 07 版本 0 2 2 8 解决通知在gnome桌面持续驻留（ 303）的问题 更多 the mit license mit copyright c 2015 omi 4399 omi gmail com permission is hereby granted free of charge to any person obtaining a copy of this software and associated documentation files the software to deal in the software without restriction including without limitation the rights to use copy modify merge publish distribute sublicense and or sell copies of the software and to permit persons to whom the software is furnished to do so subject to the following conditions the above copyright notice and this permission notice shall be included in all copies or substantial portions of the software the software is provided as is without warranty of any kind express or implied including but not limited to the warranties of merchantability fitness for a particular purpose and noninfringement in no event shall the authors or copyright holders be liable for any claim damages or other liability whether in an action of contract tort or otherwise arising from out of or in connection with the software or the use or other dealings in the software