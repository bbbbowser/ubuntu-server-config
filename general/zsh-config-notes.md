## install and configure zsh and oh-my-zsh

    sudo apt update && sudo apt upgrade -y
    sudo apt install zsh

the following script should ask if you want to set zsh as your default shell. make sure to say yes to this prompt.

    sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"

## set theme for zsh

theme screenshots can be seen at https://github.com/ohmyzsh/ohmyzsh/wiki/Themes

edit the theme line of `~/.zshrc` to use, for example, the agnoster theme

    ZSH_THEME="agnoster"

logout and login to see changes applied

## configure zsh syntax highlighting and autosuggestion

    git clone https://github.com/zsh-users/zsh-autosuggestions.git $ZSH_CUSTOM/plugins/zsh-autosuggestions
    git clone https://github.com/zsh-users/zsh-syntax-highlighting.git $ZSH_CUSTOM/plugins/zsh-syntax-highlighting

modify `~/.zshrc` to include plugins

    plugins=(git zsh-autosuggestions zsh-syntax-highlighting)
