# GitSubmodule

git practice

## 使用 submodule

### 添加 Webgl-basic 子模块

> 若想自定义文件夹 可在后面加 path;
> 例 git submodule add git@github.com:11zouzouzou/Webgl-basic.git basic

```bash
git submodule add git@github.com:11zouzouzou/Webgl-basic.git
```

> 运行后，git status，可以看到目录有增加 1 个文件.gitmodules, 这个文件用来保存子模块的信息。

### 查看子模块

```bash
git submodule
```

### 更新子模块

- 更新项目内子模块到最新版本

```bash
 git submodule update
```

- 更新子模块为远程项目的最新版本

```bash
 git submodule update --remote
```

### 修改子模块

- 在子模块中(命令行文件根目录需要更换到对应子模块)修改文件后，直接提交到远程项目分支。
