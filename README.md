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

### 修改子模块版本

- 在子模块中(命令行文件根目录需要更换到对应子模块)
1. git checkout 自定版本
2. 在主项目目录中 git add . ; git commit -m 'xx'; git push

### 删除子模块

#### 方法一
1. 删除子模块文件夹
```bash
 git rm --cached 子模块文件夹名
 rm -rf 子模块文件夹名
```
2. 删除.gitmodules文件中相关子模块信息
```text
[submodule "Webgl-basic"]
	path = Webgl-basic
	url = git@github.com:11zouzouzou/Webgl-basic.git
```
3. 删除.git/config中的相关子模块信息
```text
[submodule "Webgl-basic"]
	url = git@github.com:11zouzouzou/Webgl-basic.git
	active = true
```
4. 删除.git文件夹中的相关子模块文件
```bash
rm -rf .git/modules/assets
```

#### 方法二

1. 自动在 .git/config 中删除
```bash
git submodule deinit project-sub-1
```
2. 移除了project-sub-1 文件夹，并自动在 .gitmodules 中删除
```bash
git rm project-sub-1
```
3. 方法一中的第四步可能还需要走动删一下