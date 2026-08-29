# inspy 自动发版仓库

本仓库**仅用于母仓库的自动发版**（CI / release mirror），不存放业务源码。

## 说明

- **母仓库（真正的源码）**：https://gitee.com/yiwowang/inspy.git
- `inspy/` 是母仓库的 **git 子模块**，由 action 自动更新到母仓库最新 commit。
- `.github/workflows/auto-release.yml` 每天定时检测母仓库更新，有更新则自动构建并发布 release。

## 自动发版

- 在有新 commit 时，于 `windows-latest` 与 `ubuntu-latest` 上构建 **Windows x64** 与 **Linux x64** 一键运行包。
- Linux 包在 **Debian 11（glibc 2.31）** 容器中构建，兼容 Ubuntu 20.04+ / Debian 11+ / RHEL 9+ 等主流发行版，避免 GLIBC 版本过高的问题。
- 发布 release，命名格式：`年月日-commit前7位`。
- 包内含：可执行程序、`inspy.cfg*` 全套配置模板、`VERSION`、`README.md`、启动脚本。

> 请勿在此仓库提交业务代码，源码修改请直接在母仓库进行。
