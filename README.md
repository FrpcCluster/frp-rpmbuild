
## 说明

* 如环境再Centos6 下则打包出来的文件是Centos6的同时要使用Centos6 的配置文件
* 如环境再Centos7 下则打包出来的文件是Centos7的同时要使用Centos7 的配置文件

## 安装打包工具
```
yum install rpmdevtools
rpmdev-setuptree
```
## 克隆打包库
```
git clone https://github.com/TelDragon/Frp-rpmbuild.git

```

## 文件架构说明

```
 tree rpmbuild
rpmbuild
├── BUILD        编译之前，如解压包后存放的路径
├── BUILDROOT    编译后存放的路径
├── RPMS         打包完成后rpm包存放的路径
├── SOURCES      源包所放置的路径
├── SPECS        spec文档放置的路径
└── SRPMS        源码rpm包放置的路径


rpmbuild/
├── BUILD
├── BUILDROOT
│   ├── frpc
│   │   └── usr
│   │       └── local
│   │           └── frpc
│   │               ├── bin
│   │               │   └── frpc
│   │               ├── config
│   │               │   ├── frpc
│   │               │   └── frpc.service
│   │               ├── etc
│   │               │   ├── frpc_full.ini
│   │               │   └── frpc.ini
│   │               └── log
│   ├── frpc-0.20.0-1.el7.centos.x86_64
│   │   └── usr
│   │       └── local
│   │           └── frpc
│   │               ├── bin
│   │               │   └── frpc
│   │               ├── config
│   │               │   ├── frpc
│   │               │   └── frpc.service
│   │               ├── etc
│   │               │   ├── frpc_full.ini
│   │               │   └── frpc.ini
│   │               └── log
│   ├── frps
│   │   └── usr
│   │       └── local
│   │           └── frps
│   │               ├── bin
│   │               │   └── frps
│   │               ├── config
│   │               │   ├── frps
│   │               │   └── frps.service
│   │               ├── etc
│   │               │   ├── frps_full.ini
│   │               │   └── frps.ini
│   │               └── log
│   └── frps-0.20.0-1.el7.centos.x86_64
│       └── usr
│           └── local
│               └── frps
│                   ├── bin
│                   │   └── frps
│                   ├── config
│                   │   ├── frps
│                   │   └── frps.service
│                   ├── etc
│                   │   ├── frps_full.ini
│                   │   └── frps.ini
│                   └── log
├── RPMS
│   └── x86_64
│       ├── frpc-0.20.0-1.el7.centos.x86_64.rpm
│       └── frps-0.20.0-1.el7.centos.x86_64.rpm
├── SOURCES
│   ├── etc
│   │   └── init.d
│   │       └── frps
│   └── usr
│       ├── lib
│       │   └── systemd
│       │       └── system
│       │           └── frps.service
│       └── local
│           └── frps
│               ├── bin
│               │   └── frps
│               ├── etc
│               │   ├── frps_full.ini
│               │   └── frps.ini
│               └── log
├── SPECS
│   ├── frpc.spec
│   └── frps.spec
└── SRPMS

```

## 打包命令
```
rpmbuild -bb xxxx.spec
rpmbuild -bb --target=i386 xxxx.spec

```

## 测试安装与卸载命令

```
rpm -ivh xxx.rpm     #安装
rpm -ivh --force xxx.rpm  #强制安装
rpm -e xxx.rpm       #查询
rpm -qa |grep xxx    #查询
```

