## Arch Linux LiveDVD (with xfce4 preinstalled)

本 Profile 基于 archiso 52 (releng)，**本配置档未经充分测试，谨慎使用**。

> 本仓库也有适用于早期版本 archiso 的配置档（切换分支即可）。

不对上游配置作任何删减，额外提供了一个最小化的 xfce4 桌面环境和一些必须的图形化应用以协助安装或修复 Arch Linux。

关于本配置档和 Arch Linux 官方 releng 配置档有何差异，[请看这里](https://github.com/bobby285271/Archiso/commit/ee37de3cda4952f72837247d0c9f845a4dde9265)。

### 获取镜像

> 最后构建时间为 2021.04.08，**请注意这些镜像没有经过充分测试，谨慎使用**。

**用户名 `live` 密码 `live`，用户名 `root` 密码 `root`**

百度网盘：https://pan.baidu.com/s/1Hnxy805j-BFbxMv-WeNcdQ 

提取码：`hu6p`

### 自行构建

请确保你在使用 Arch Linux（若使用 Docker 需要 `--privileged` 选项）且安装了 `archiso` 和 `git` 软件包。

在 root 权限下拉取仓库并开始构建：

```plain
# git clone https://github.com/bobby285271/Archiso.git
# mkarchiso -v -w work -o out Archiso
```

其中 `work` 是工作目录，`out` 是制品目录（可按需修改）。在构建完成后可在 `out` 获取需要的 ISO 文件并可以直接删除 `work`。

如果需要进一步定制请参考 [ArchWiki](https://wiki.archlinux.org/index.php/Archiso)，需要特别注意的是 `customize_airootfs.sh` 已经被弃用。
