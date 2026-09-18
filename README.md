# Shadowrocket 功能模块

仅存放功能模块，不含节点、订阅凭据、个人内网配置、证书或私钥。

## 导入及更新地址

- [番茄小说定向去广告](https://raw.githubusercontent.com/q85985477/shadowrocket-modules/main/modules/Fanqie-AdBlock.module)
- [TikTok US 追加名单兼容版](https://raw.githubusercontent.com/q85985477/shadowrocket-modules/main/modules/TikTok-US-Append.module)

## 番茄小说

候选版 2026-09-18.2。上一版已被用户报告未能屏蔽广告，本版尚未经过iPhone实机验收。综合 zqzess 与 honue 的已知广告路径，并按用户要求拒绝 fqnovelvod.com 视频CDN和 novelapp.ixigua.com 视频请求。番茄域名下 audio/tts/video 路径为候选规则，缺少当前iPhone请求日志，不能保证听书全覆盖。已缓存媒体和离线朗读不受网络规则控制。

没有加入全局 ttplayer 拦截、历史IP及整个 bytedance.com 封锁。共享广告接口仍可能影响其他App，snssdk 的 toutiao 视频路径也会被拒绝。无需会员脚本，不提供会员解锁。

启用前停用旧番茄模块；更新模块后重新应用配置，测试文字阅读、章末/底部广告及听书视频。若听书仍可加载，请提供对应时段Shadowrocket请求记录（隐藏订阅与凭据）以确认真实地址，避免盲目扩大封锁。

来源：https://github.com/zqzess/rule_for_quantumultX/blob/master/Surge/Module/FanQieNovel.sgmodule 、https://github.com/honue/rules/blob/master/Loon/plugin/FanQieNovel.plugin 。

## TikTok US

保留用户既有Semporia美国区模块的4条改写，仅将MITM hostname改为%APPEND%，并使用本仓库更新地址，避免更新回退修复。原作者及来源保留在模块内。它是旧式兼容版本，不保证当前App可解锁。上游当前说明推荐使用支持TikTok的节点而不再依赖旧式HTTPS改写：https://github.com/Semporia/TikTok-Unlock 。模块不会自动切换美国节点。

## HTTPS解密与分流

两份模块都追加解密名单，不覆盖其他模块名单。其他仍使用覆盖写法的模块也需单独检查。

HTTPS解密本身不把DIRECT改为PROXY或改变内网VPN策略，但名单内的HTTPS连接会被解密，证书锁定可能导致失败。共享广告域名的其他App也可能受影响。本仓库不添加内网、RustDesk、Codex、PayPal域名，也不包含DNS/TUN或节点设置。

使用自己生成并在iPhone中信任的CA证书；不要上传证书或私钥。导入后在方便中断连接时重新应用配置，确认有效名单，再测试阅读、翻章、底部广告及原有服务。

若出现问题，停用新模块并恢复原模块；不要同时启用多个TikTok地区模块。旧sing-box地址仍可能是旧版，请使用本仓库上方更新地址。
