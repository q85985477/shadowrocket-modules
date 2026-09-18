# Shadowrocket 功能模块

仅存放功能模块，不含节点、订阅凭据、个人内网配置、证书或私钥。

## 导入及更新地址

- [番茄小说定向去广告](https://raw.githubusercontent.com/q85985477/shadowrocket-modules/main/modules/Fanqie-AdBlock.module)
- [TikTok US 追加名单兼容版](https://raw.githubusercontent.com/q85985477/shadowrocket-modules/main/modules/TikTok-US-Append.module)

## 番茄小说

候选版 2026-09-18.1：2条广告域名拒绝、6条广告URL匹配。通过15个模拟URL检查，未完成iPhone实机验收，不能保证最新版全部广告消失。启用前停用原来两份番茄模块，避免叠加。参考 zqzess/rule_for_quantumultX 和 deezertidal/shadowrocket-rules 的公开广告接口线索重新编写；不封锁整个字节域名或历史IP。

## TikTok US

保留用户既有Semporia美国区模块的4条改写，仅将MITM hostname改为%APPEND%，并使用本仓库更新地址，避免更新回退修复。原作者及来源保留在模块内。它是旧式兼容版本，不保证当前App可解锁。上游当前说明推荐使用支持TikTok的节点而不再依赖旧式HTTPS改写：https://github.com/Semporia/TikTok-Unlock 。模块不会自动切换美国节点。

## HTTPS解密与分流

两份模块都追加解密名单，不覆盖其他模块名单。其他仍使用覆盖写法的模块也需单独检查。

HTTPS解密本身不把DIRECT改为PROXY或改变内网VPN策略，但名单内的HTTPS连接会被解密，证书锁定可能导致失败。共享广告域名的其他App也可能受影响。本仓库不添加内网、RustDesk、Codex、PayPal域名，也不包含DNS/TUN或节点设置。

使用自己生成并在iPhone中信任的CA证书；不要上传证书或私钥。导入后在方便中断连接时重新应用配置，确认有效名单，再测试阅读、翻章、底部广告及原有服务。

若出现问题，停用新模块并恢复原模块；不要同时启用多个TikTok地区模块。旧sing-box位置仅作为迁移入口，后续维护以本仓库为准。
