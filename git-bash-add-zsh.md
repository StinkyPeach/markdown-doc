## git-bash 添加zsh

`zsh 可应用到 windows Terminal， vscode， goland`

## 准备

1. [git for winsows](https://git-scm.com/)  (`git version 2.30.1.windows.1`)
2. [zsh](https://packages.msys2.org/package/zsh?repo=msys&variant=x86_64) (`zsh-5.8-5-x86_64.pkg.tar.zst`)
3. [oh-my-zsh](https://ohmyz.sh/#install)

## 安装

1. 安装git for windows

2. 解压`zsh-5.8-5-x86_64.pkg.tar.zst` 

   ```shell
   > apt-get install -y zstd
   > tar -I zstd -xvf zsh-5.8-5-x86_64.pkg.tar.zst
   ```

3. 将解压内容移动到git安装的根目录，例如：(`C:\Program Files\Git`)， 将`zsh.exe`或者`zsh-5.8.exe`改为`zsh`
![](https://github.com/StinkyPeach/markdown-doc/raw/main/image/git-bash-add-zsh/image-20210308140626782.png)

4. 安装 oh-my-zsh

   ```shell
   > sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
   ```


5. 使用

   - 打开一个 git-bash， 输入zsh ，即可启动zsh
![](https://github.com/StinkyPeach/markdown-doc/raw/main/image/git-bash-add-zsh/image-20210308141013279.png)

## 安装插件

```shell
> cd ~/.oh-my-zsh/custom/plugins
> git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions

> # 添加 zsh-autosuggestions
> vim ~/.zshrc
```

默认插件已经有了git，所以这里新增插件，空格隔开
![](https://github.com/StinkyPeach/markdown-doc/raw/main/image/git-bash-add-zsh/image-20210308141439420.png)

```shell
source ~/.zshrc
```

## 配置默认启动zsh

```shell
vim ~/.bashrc
## 追加内容
## Launch Zsh
if [ -t 1 ]; then
exec zsh
fi
```

## 加入windwos Terminal

在 `windows treminal` 的`settings.json`的 lists 字段中加入

```json
{
	"guid": "{b453ae62-4e3d-5e58-b989-0a998ec441b7}",
	"hidden": false,
	"name": "Git Bash",
	"commandline" : "C:/Program Files/Git/bin/bash.exe -li",
	"icon" : "C:/Program Files/Git/mingw64/share/git/git-for-windows.ico",
	"startingDirectory" : "%USERPROFILE%"
}
```

## 结束