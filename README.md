# cloud-init 配置

本仓库是一些常用的 cloud-init 配置文件，目前主要是树莓派上的镜像对应的配置文件。

使用时直接复制到烧录后的 TF 卡中的 boot 分区根目录即可，该目录下已经有相关文件，已有的文件是默认配置，我们需要覆盖它。boot 分区是 FAT 分区，将 TF 卡通过读卡器插上后电脑可以看到此分区，所以可以很方便地复制文件。

需要注意的是，应该在刚烧录完成后首次启动前执行上述步骤才会生效，如果已经启动过，则需要执行 `cloud-init clean --logs --reboot` 后才会生效，日志可在 `/var/log/cloud-init*` 找到。可通过 `cloud-init status --long` 查看当前状态

温馨提示：对于树莓派 4B，ubuntu 20.04 的镜像因为已经过时无法在 Raspberry Pi Imager 中找到，需要从 [Ubuntu 官网](https://canonical-ubuntu-hardware-support.readthedocs-hosted.com/boards/how-to/ubuntu_supported/raspberry-pi/) 下载 pre-installed image。由于树莓派性能有限，建议下载 server 版。