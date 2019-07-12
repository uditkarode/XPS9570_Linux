# XPS9570_Linux
A config file to make the Linux kernel work with the Dell XPS 15 9570 (2018)

## How to compile
Assuming you already emerged `sys-kernel/gentoo-sources`  
```bash
cd /usr/src/linux
git clone https://github.com/uditkarode/XPS9570_Linux.git
mv XPS*/4.19* . && rm -rf XPS*
mv 4.19* .config
make -j$(nproc --all)
make -j$(nproc --all) modules_install
make install
genkernel --install initramfs
```

the kernel should be compiled and present in /boot after these commands
