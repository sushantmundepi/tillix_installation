# tillix_installation
cmd to install tillix later on choose "2" to make tillix as default terminal  and then "Y" to make zsh as default shell

install tillix-emulator 

    sudo apt update
    sudo apt install tilix -y
configure the ~/.bashrc file to include settings related to Tilix and VTE, creating a symbolic link for VTE, and then reloading the bash configuration to apply the changes immediately.

    sed -i '$a\# Tilix\nif [ $TILIX_ID ] || [ $VTE_VERSION ]; then\n    source /etc/profile.d/vte.sh\nfi' ~/.bashrc
    sudo ln -s /etc/profile.d/vte-2.91.sh /etc/profile.d/vte.sh
    source ~/.bashrc

to make tilix as default terminal 

    sudo update-alternatives --config x-terminal-emulator

install zsh

    sudo apt install -y zsh
    sudo apt install -y curl wget git
    sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"

set up and configure your Zsh shell with Oh My Zsh

    echo '' > ~/.zshrc
    sed -i '$a\export ZSH="$HOME/.oh-my-zsh"\nZSH_THEME="avit"\nDEFAULT_USER=$USER\nplugins=(git zsh-autosuggestions zsh-syntax-highlighting)\nsource $ZSH/oh-my-zsh.sh\nsource /etc/zsh_command_not_found' ~/.zshrc
    sudo apt install command-not-found -y
    cd ~/.oh-my-zsh/plugins/
    git clone https://github.com/zsh-users/zsh-autosuggestions.git $ZSH_CUSTOM/plugins/zsh-autosuggestions
    git clone https://github.com/zsh-users/zsh-syntax-highlighting.git $ZSH_CUSTOM/plugins/zsh-syntax-highlighting
    source ~/.zshrc
    exec zsh
    cd
