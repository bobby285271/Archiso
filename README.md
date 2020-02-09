# Dasyatis 的 Arch Linux 安装镜像

中文：https://www.bobby285271.top/index.php/archiso-chinese/

English：https://www.bobby285271.top/index.php/archiso/

### 准备

请确保你在使用 Arch Linux 且安装了 `archiso` 和 `git` 软件包。

将本项目仓库克隆到本地：
```plain
# git clone https://github.com/bobby285271/Archiso.git
# cd ./Archiso/
```

### 配置
配置过程请参考：[ArchWiki](https://wiki.archlinux.org/index.php/Archiso)。

* `packages.x86_64` 用于修改软件包信息。
* `airootfs/root/customize_airootfs.sh` 可用于进行额外的配置。
* `build.sh` 用于最终的镜像生成。

例如你希望 NetworkManager 开机启动，你就把 `systemctl enable NetworkManager` 加入 `airootfs/root/customize_airootfs.sh`，如果你发现加进去的命令没起作用，看看 `build.sh` 是否执行了覆盖有关配置的命令。

`airootfs/etc/` 中的内容将会被拷贝到最终镜像启动后的 `/etc/` 目录中（如果由同名文件，就会被覆盖掉）。`airootfs/usr/` 等等同理（当然默认是没这个目录的，你可以自己建一个），可用于放置自己修改过的各类应用程序的配置文件。例如你希望 Live 系统中的 `/etc/sddm.conf` 是怎么样的，你就新建一个 `airootfs/etc/sddm.conf` 文件，填入你的内容，设置正确的文件权限即可。

### 构建
接下来运行构建脚本：
```plain
# ./build.sh -v
```

如果一切顺利，构建完成后可以在 `out/` 目录找到生成的镜像文件。如需再次构建，需要先删除 `work/` 目录。

### 意外排除
如果你没有见到 `out/` 目录，意味着构建失败了，看看网络是否有问题。如果没有，重启系统，删除 `work/` 目录，再次尝试。

确保你的系统所有软件包都是最新的，如果确认是 Arch Linux 的问题，就向 Arch Linux 反馈问题，如果确认是我的配置档出现了问题，可以在评论区反馈。

祝一切顺利！
