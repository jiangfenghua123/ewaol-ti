# ewaol-ti
GOAL:集成K3S 到AM6442 /TDA4 单板

现有的参考：https://ewaol.sites.arm.com/meta-ewaol/overview.html

已经将K3S 集成到n1sdp 单板的sdk ,且是yocto 的编译架构

代码：https://git.gitlab.arm.com/ewaol/meta-ewaol.git

      meta-ewaol
          ├── meta-ewaol-config   配置整个代码
          ├── meta-ewaol-distro    编译目标
          ├── meta-ewaol-tests     测试目标
          

编译工具：kas

编译命令：kas build meta-ewaol-config/kas/n1sdp.yml
支持的yocto branch: hardknott

ewaol 的编译使用kas

编译会根据meta-ewaol-config/kas/n1sdp.yml去创建build \layers,且控制整个编译过程

          ├──build 
                    ├── conf
                    │   ├── bblayers.conf
                    │   ├── local.conf
                        └── templateconf.cfg
          ├─-─ layers
                   ├── meta-arm
                   ├── meta-openembedded
                   ├── meta-security
                   ├── meta-virtualization​
                   └── poky
                   
 如果采用ewaol,会改变现有的AM6442/TDA4 的编译架构，所以不采用。
 AM6442的代码架构：

 
       ├── build    
       ├── configs
       ├── downloads
       ├── oe-layertool-setup.sh​
       ├── sample-files
       └── sources
           ├── bitbake
           ├── meta-arago
           ├── meta-arm
           ├── meta-openembedded
           ├── meta-processor-sdk
           ├── meta-qt5
           ├── meta-ti
           ├── meta-virtualization
            └── oe-core
    
  ti 支持的layers yocto branch:dunfell
  
目前 meta-virtualization branch:dunfell 没有支持k3s
 
 
 
 
 
                   
