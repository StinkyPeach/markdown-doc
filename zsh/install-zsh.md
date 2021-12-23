<h1 align="center">
	Zsh 美化
</h1>

## 安装zsh

```shell
sudo apt-get install -y zsh
```

## 安装 oh-my-zsh

```shell
sh -c "$(curl -fsSL https://raw.github.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"

## 切换shell 为zsh
chsh -s /bin/zsh
```

## 安装字体

为了防止终端可能会出现乱码，也是因为你的电脑不支持那么多字体，所以我们需要先安装扩展字体。

Powerlevel10k 作者推荐使用 [Meslo Nerd Font](https://link.zhihu.com/?target=https%3A//github.com/romkatv/powerlevel10k%23meslo-nerd-font-patched-for-powerlevel10k) 字体，Download these four ttf files:

- [MesloLGS NF Regular.ttf](https://link.zhihu.com/?target=https%3A//github.com/romkatv/powerlevel10k-media/raw/master/MesloLGS%20NF%20Regular.ttf)
- [MesloLGS NF Bold.ttf](https://link.zhihu.com/?target=https%3A//github.com/romkatv/powerlevel10k-media/raw/master/MesloLGS%20NF%20Bold.ttf)
- [MesloLGS NF Italic.ttf](https://link.zhihu.com/?target=https%3A//github.com/romkatv/powerlevel10k-media/raw/master/MesloLGS%20NF%20Italic.ttf)
- [MesloLGS NF Bold Italic.ttf](https://link.zhihu.com/?target=https%3A//github.com/romkatv/powerlevel10k-media/raw/master/MesloLGS%20NF%20Bold%20Italic.ttf)

## 安装 Powerlevel10k主题

```shell
git clone --depth=1 https://github.com/romkatv/powerlevel10k.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/themes/powerlevel10k

## 打开zsh的配置文件
cd ~
vim .zshrc
ZSH_THEME=powerlevel10k/powerlevel10k

## 更改成功后
source .zshrc

## 后续回自动弹出配置Powerlevel10k的配置界面，若没有，请手动配置
```

![image-20211223114529721](https://github.com/StinkyPeach/markdown-doc/raw/main/images/install-zsh/image-20211223114529721.png)

## 配置Powerlevel10k

Powerlevel10k 提供了一个配置脚本，运行脚本后只需回答几个简单的问题即可完成配置。

直接输入 `p10k configure` 即可进入配置问答界面

```bash
p10k configure
```

![image-20211223145027277](https://github.com/StinkyPeach/markdown-doc/raw/main/images/install-zsh/image-20211223145027277.png)

## 安装插件

Oh My Zsh 有非常丰富的插件，使用插件可以使得在终端的效率翻倍，下面介绍 5 个我常用的插件。 插件均需在配置文件 `~/.zshrc` 中写出，如下：

```text
plugins=(
  git
  github
  autojump
  zsh-syntax-highlighting
  zsh-autosuggestions
)
```

- zsh-syntax-highlighting

  ```shell
  git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
  ```
	- 在~/.zshrc 中配置
	plugins=(zsh-syntax-highlighting)

- zsh-autosuggestions

  ```shell
  git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
  ```
	- 在~/.zshrc 中配置
	plugins=(zsh-autosuggestions)
