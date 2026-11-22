# AC极光 · vivo X Flip 模块与移植

三个面向 vivo X Flip（PD2256 / V2256A）的项目源码，整理为可开源发布的形态。

- 作者：**AC极光**（酷安：**AC极光_Official**）
- 机型：vivo X Flip，PD2256 / V2256A，SM8475，Android 14 / 15
- 每个子目录都有自己的 README、LICENSE 和构建说明

## 目录

### 1. [magic-mirror-manager](magic-mirror-manager/) —— 魔镜应用管理

KernelSU 模块，WebUI 管理外屏（魔镜）应用白名单：列出已安装应用，一键加入/移出
`fold_adaptive_screen_app_list`，可重启魔镜桌面立即生效。

- 许可：MIT
- 许可、目录结构、打包方式见子目录 README
- 模块 zip：`magic_mirror_manager-v1.0.3.zip`（根目录 `module.prop` + `webroot/`）

### 2. [cammirror-a14](cammirror-a14/) —— 相机增强（Android 14 适配）

外屏相机增强模块的 A14 移植：取景镜像修正、内屏 UI、4K/60 帧、默认超广角、
「颠倒世间之物」、「虚假之天」电源键改音量键。

- 原作：Cisheng & Minis；A14 适配与维护：AC极光
- 许可：适配改动 MIT，原作部分权利归原作者；**三个二进制不随源码分发**，见 `bin/BINARIES.md`
- 模块 zip：`cammirror-v5preview01-a14.zip`

### 3. [skyward-pd2256](skyward-pd2256/) —— Skyward recovery 外屏移植

把 Rust 写的 Skyward recovery 移植到 X Flip，默认在外屏 422×682 上显示；
含 180° 旋转、外屏背光、双触摸屏选择、可滑动页面、精简打包工具等改动。

- 上游：Kirk Lin（Skyward）、Qingizi7（PD2301 适配）
- 许可：GPL-3.0-or-later（继承上游）
- 源码含完整 Rust 工作区（不含 `target/`、原厂镜像、vivo 专有 `.so`）
- 构建见 `skyward-pd2256/BUILD.md`，改动清单见其 README

## 免责

所有项目都只修改可回退的用户态内容（设置、模块、恢复分区），不写死系统分区；
刷写 recovery 前请确认 bootloader 已解锁并备份原厂镜像。因使用本仓库内容造成的
设备损坏、数据丢失，作者不承担责任。
