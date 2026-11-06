# dsh-fairy-zzz-patched4c

中文 | [English](#english)

> dsh-fairy-zzz-patched4c是四夕4c使用Deepseek Harness对dsh-fairy-zzz进行了客制化改造的补丁包，一切解释权归四夕4c所有

**作者**：四夕4c（4Dusk-4c） · **仓库**：[4Dusk-4c/dsh-fairy-zzz-patched4c](https://github.com/4Dusk-4c/dsh-fairy-zzz-patched4c)

`dsh-fairy-zzz` 的**纯显示补丁**——不是皮肤本体，不含皮肤本体的一行代码或一个媒体资源。

它不插入预设、不注册 slot、不带视频/语音素材，只加载一个 Client 半身，把几处显示修复叠在已安装的 `dsh-fairy-zzz` 上：

| 修复 | 效果 |
|---|---|
| 眼徽波纹 | 扩散波纹/光晕恢复正圆（覆盖 DSH 全局 `corner-shape: superellipse(1.5)`） |
| 窗口按钮 | Windows 标题栏最小化/全屏/关闭按钮背景透明，聊天界面也保持沉浸 |
| 开机动画 | 右下角 `1× / 1.5× / 2× / 3×` 倍速 + `SKIP ▸`，选择记在 `localStorage` |
| 字标 | 侧栏 “Fairy” 字标改用 HarmonyOS Sans SC / 鸿蒙黑体 |
| 用量标签 | 消息尾部原生「用量」改为「电费」，眼徽气泡标题同步 |

## 前置条件

必须先装并启用 `dsh-fairy-zzz`（皮肤本体，不在本仓库分发）。本补丁只改显示，皮肤本体没装时它什么也不会画。

## 安装

只从 **GitHub Release** 下载安装。

**DSH Desktop / Web 的插件页**

1. 左侧栏 → **Plugins**
2. **Add plugin** → 填入下面的 Release 下载地址 → **Install**

```
https://github.com/4Dusk-4c/dsh-fairy-zzz-patched4c/releases/download/v1.0.0/dsh-fairy-zzz-patched4c-1.0.0.tgz
```

安装前 Host 会先读一遍 spec，显示 name / version / description 供确认。

**命令行**

```
dsh plugin --profile <profile> add https://github.com/4Dusk-4c/dsh-fairy-zzz-patched4c/releases/download/v1.0.0/dsh-fairy-zzz-patched4c-1.0.0.tgz
```

装好后刷新页面即可看到上述效果；无需重启 Host。

## 卸载

Plugins 页 → 该插件 → Remove，或：

```
dsh plugin --profile <profile> remove dsh-fairy-zzz-patched4c
```

## 兼容性

本补丁通过 `dsh-fairy-zzz` 渲染出的 DOM class 叠加样式（`.fz3-eye-halo`、`.fz3-boot`、`.fz3-skip`、`.fz3-bubble-head` 等），并监听 `.fz3-boot` 的出现来注入控制条。**皮肤本体若改动这些 class 或结构，补丁需要跟着适配**；此时表现为某一项修复不生效或控制条不出现，不会影响皮肤本体运行。

开发验证于 DSH `0.2.1-rc.3`。未声明 `engines.dsh`，因此安装时不会被版本要求阻断；升级 DSH 大版本后建议实测一次。

## 许可

MIT，见 [LICENSE](./LICENSE)。

---

## English

A **display-only companion patch** for `dsh-fairy-zzz`. It is not the skin and ships none of the skin's code or media assets.

It inserts no preset, registers no slot and carries no video/voice resources: one Client half layers a few display fixes over an installed `dsh-fairy-zzz`:

- circular eye ripple and halo (overrides DSH's global `corner-shape: superellipse(1.5)`)
- transparent Windows title-bar min/max/close buttons, immersive in chat too
- boot-animation speed `1× / 1.5× / 2× / 3×` and `SKIP ▸` in the bottom-right corner, remembered in `localStorage`
- sidebar “Fairy” wordmark in HarmonyOS Sans SC
- the native `用量` message tail relabelled `电费`

**Requires** `dsh-fairy-zzz` to be installed and enabled first.

**Install (GitHub Release only):** download the tarball from
`https://github.com/4Dusk-4c/dsh-fairy-zzz-patched4c/releases/download/v1.0.0/dsh-fairy-zzz-patched4c-1.0.0.tgz`,
then in DSH open **Plugins** → **Add plugin**, paste that URL and press **Install**.
CLI: `dsh plugin --profile <profile> add <same URL>`.

**Caveat:** the patch targets class names produced by `dsh-fairy-zzz` (`.fz3-eye-halo`, `.fz3-boot`, `.fz3-skip`, `.fz3-bubble-head`, …). If the skin changes that DOM, the patch needs a matching update; a mismatch only makes a fix stop applying.

MIT licensed.

**Author:** 四夕4c (4Dusk-4c) · [github.com/4Dusk-4c](https://github.com/4Dusk-4c)
