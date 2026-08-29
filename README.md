# inspy @ EvolvedGhost

本仓库（https://github.com/EvolvedGhost/inspy）**仅用于母仓库的自动发版**（是一个 CI / release mirror）。

- **真正的源码在母仓库**：https://gitee.com/yiwowang/inspy.git
- `inspy/` 是一个指向母仓库的 **git 子模块**链接（`git submodule update --init` 即可拉取）。
- `.github/workflows/auto-release.yml` 每天定时拉取母仓库最新代码：
  - 若母仓库有新 commit，则同时构建 **Windows x64** 和 **Linux x64** 的一键运行包；
  - 并发布 release，命名格式：`年月日-commit前7位`；
  - 包内包含：可执行程序、`inspy.cfg*` 全套配置模板、`VERSION`、`README.md`、启动脚本。

> 请勿在此仓库提交业务代码，源码修改请直接到母仓库进行。
