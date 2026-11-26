# PON 固件自定义配置

此仓库仅提供配置模板和构建申请入口，不含固件源码。Fork 后在自己的分支上编辑下面的文件，向本仓库的 `main` 提交 PR。

| 文件 | 可改内容 |
| --- | --- |
| `profile.conf` | 单行 `tcboot` 或 `native-ubi`，应与设备现有的引导和分区布局一致。 |
| `kernel.config` | 可选 `CONFIG_KERNEL_PRINTK_TIME=y/n`、`CONFIG_KERNEL_MAGIC_SYSRQ=y/n`（每行填一个值）。 |
| `kmods.config` | 可选 `CONFIG_PACKAGE_kmod-dummy=y`、`CONFIG_PACKAGE_kmod-ifb=y`、`CONFIG_PACKAGE_kmod-netem=y`、`CONFIG_PACKAGE_kmod-vxlan=y`。不支持删除基础模块。 |

以 `#` 开头的行为注释。只接受表内列出的项目，其他文件不会进入构建；不要提交脚本、补丁、光猫身份或密钥。需要新增选项时，请先开 Issue 说明用途。

提交 PR 代表申请，审核后由维护者触发受控构建；Fork 自己运行 Actions 不会触发私有构建。固件不会自动公开，能否交付取决于构建验证结果、原厂组件分发许可及对应源码义务。
