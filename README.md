# PON 固件自定义配置

此仓库仅提供配置模板和构建申请入口，不含固件源码。Fork 后在自己的分支上编辑下面的文件，向本仓库的 `main` 提交 PR。

| 文件 | 可改内容 |
| --- | --- |
| `profile.conf` | 单行 `tcboot` 或 `native-ubi`，应与设备现有的引导和分区布局一致。 |
| `kernel.config` | 可选 `CONFIG_KERNEL_PRINTK_TIME=y/n`、`CONFIG_KERNEL_MAGIC_SYSRQ=y/n`（每行填一个值）。 |
| `kmods.config` | 可选 `CONFIG_PACKAGE_kmod-dummy=y`、`CONFIG_PACKAGE_kmod-ifb=y`、`CONFIG_PACKAGE_kmod-netem=y`、`CONFIG_PACKAGE_kmod-vxlan=y`。不支持删除基础模块。 |

以 `#` 开头的行为注释。只接受表内列出的项目；PR 只能修改这三份文件，不要提交脚本、补丁、光猫身份或密钥。需要新增选项时，请先开 Issue 说明用途。

提交非草稿 PR 即可申请：私有构建服务每两小时自动检查，不需要维护者手动触发，也不需要在 Fork 启用 Actions。每个北京时间自然日，全库最多接收 2 单、每个 GitHub 账号最多接收 1 单，超额的有效申请等待后续扫描；同一源码和配置不会重复构建。GitHub 定时任务可能延迟，请保持 PR 打开。当前结果仅保存在私有构建库；含受限原厂组件的固件不对外下载。
