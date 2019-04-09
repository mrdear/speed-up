## brew加速指南

brew自身是以git项目形式存放在本地，自身更新是通过git pull更新，软件下载则通过额外的下载源，因此brew的加速有两个方面的修改：

**清单1：修改brew仓库的remote地址为国内镜像仓库**

```bash
#!/usr/bin/env bash
# brew替换为清华大学源脚本
# 替换brew.git:
cd "$(brew --repo)"
git remote set-url origin https://mirrors.tuna.tsinghua.edu.cn/git/homebrew/brew.git

# 替换homebrew-core.git:
cd "$(brew --repo)/Library/Taps/homebrew/homebrew-core"
git remote set-url origin https://mirrors.tuna.tsinghua.edu.cn/git/homebrew/homebrew-core.git

```

**清单2: 修改brew的下载源为国内镜像**

```bash
# 替换homebrew-bottles:
export HOMEBREW_BOTTLE_DOMAIN=https://mirrors.tuna.tsinghua.edu.cn/homebrew-bottles
export HOMEBREW_NO_AUTO_UPDATE=true
```
需要把上述变量放到bash或者zsh配置中。


**清单3: 生效，测试**

```bash
# 配置生效
source ~/.bash_profile

# brew更新测试，update虽然还是挺慢的。。。但是下载软件挺快的了
brew update | echo
```


### 附录

中国科大brew源
- [https://mirrors.ustc.edu.cn/brew.git](https://mirrors.ustc.edu.cn/brew.git)
- [https://mirrors.ustc.edu.cn/homebrew-core.git](https://mirrors.ustc.edu.cn/homebrew-core.git)
- [https://mirrors.ustc.edu.cn/homebrew-bottles](https://mirrors.ustc.edu.cn/homebrew-bottles)

brew官方源
- [https://github.com/Homebrew/brew.git](https://github.com/Homebrew/brew.git)
- [https://github.com/Homebrew/homebrew-core](https://github.com/Homebrew/homebrew-core)