
- I use Linux & Mac for development, will only cover instructions for those
- I keep them all in a folder named dotfiles in home dir
- Use sym links
- Show tree output
- TODO
	- iTerm
	- Ubersicht
	- Homebrew

- git
	- version control system
	- Configured to hold my name and email
	- Git installation
		- Mac
			- run xcode-select --install
			- git config --global user.email "you@example.com"
			- git config --global user.name "Your Name"
		- Linux
			- sudo apt install git -y
			- git config --global user.email "you@example.com"
			- git config --global user.name "Your Name"

	- Use my git dotfile
		- Mac
			- mkdir -p ~/dotfiles/git
			- wget https://raw.githubusercontent.com/omolazabal/dotfiles-mac/master/git/.gitconfig -P ~/dotfiles/git
			- rm ~/.gitconfig
			- ln -s ~/dotfiles/git/.gitconfig ~/.gitconfig
		- Linux
			- mkdir -p ~/dotfiles/git
			- wget https://raw.githubusercontent.com/omolazabal/dotfiles-linux/master/git/.gitconfig -P ~/dotfiles/git
			- rm ~/.gitconfig
			- ln -s ~/dotfiles/git/.gitconfig ~/.gitconfig

- tmux
	- Terminal multiplexer
	- Configured to use ZSH and ressurect sessions after closing your terminal.
	- Will not work if you do not have ZSH
	- Tmux Installatinon
		- Mac
			- brew install tmux
		- Linux
			- sudo apt install tmux -y

	- Use my tmux dotfile
		- Mac
			- mkdir -p ~/dotfiles/tmux
			- wget https://raw.githubusercontent.com/omolazabal/dotfiles-mac/master/tmux/.tmux.conf -P ~/dotfiles/tmux
			- rm ~/.tmux.conf
			- ln -s ~/dotfiles/tmux/.tmux.conf ~/.tmux.conf

			- mkdir -p ~/dotfiles/tmux/.tmux/plugins
			- rm -rf ~/.tmux
			- ln -s ~/dotfiles/tmux/.tmux ~/.tmux
			- git clone https://github.com/tmux-plugins/tpm ~/dotfiles/tmux/.tmux/plugins/tpm
			- tmux new-session
			- <C-b`> + :` source ~/.tmux.conf
			- <C-b`> + I` source ~/.tmux.conf
		- Linux
			- mkdir -p ~/dotfiles/tmux
			- wget https://raw.githubusercontent.com/omolazabal/dotfiles-linux/master/tmux/.tmux.conf -P ~/dotfiles/tmux
			- rm ~/.tmux.conf
			- ln -s ~/dotfiles/tmux/.tmux.conf ~/.tmux.conf

			- mkdir -p ~/dotfiles/tmux/.tmux/plugins
			- rm -rf ~/.tmux
			- ln -s ~/dotfiles/tmux/.tmux ~/.tmux
			- git clone https://github.com/tmux-plugins/tpm ~/dotfiles/tmux/.tmux/plugins/tpm
			- tmux new-session
			- <C-b`> + :` source ~/.tmux.conf
			- <C-b`> + I` source ~/.tmux.conf

- vim
	- Terminal-based editor
	- Many configurations that suite my workflow
	- Installation
		- Mac
			- brew install vim
		- Linux
			- sudo apt install vim -y
	- Use my dotfile
		- Mac
			- mkdir -p ~/dotfiles/vim
			- wget https://raw.githubusercontent.com/omolazabal/dotfiles-mac/master/vim/.vimrc -P ~/dotfiles/vim
			- rm ~/.vimrc
			- ln -s ~/dotfiles/vim/.vimrc ~/.vimrc
		- Linux
			- mkdir -p ~/dotfiles/vim
			- wget https://raw.githubusercontent.com/omolazabal/dotfiles-linux/master/vim/.vimrc -P ~/dotfiles/vim
			- rm ~/.vimrc
			- ln -s ~/dotfiles/vim/.vimrc ~/.vimrc
		
VSCode
	- Editor
	- Installation
		- Mac
			- visit https://code.visualstudio.com/download
			- Double click zip file to unzip
			- Drag the .app file into you Appliations folder
		- Linux
			- visit https://code.visualstudio.com/download
			- run sudo dpkg -i <filename> on your installation
	- Use my dotfile
		- Mac
			- mkdir -p ~/dotfiles/vscode
			- wget https://raw.githubusercontent.com/omolazabal/dotfiles-mac/master/vscode/settings.json -P ~/dotfiles/vscode
			- rm ~/Library/Application Support/Code/User/settings.json
			- ln -s ~/dotfiles/vscode/settings.json ~/Library/Application Support/Code/User/settings.json

			- wget https://raw.githubusercontent.com/omolazabal/dotfiles-mac/master/vscode/keybindings.json -P ~/dotfiles/vscode
			- rm ~/Library/Application Support/Code/User/keybindings.json
			- ln -s ~/dotfiles/vscode/keybindings.json ~/Library/Application Support/Code/User/keybindings.json

		- Linux
			- mkdir -p ~/dotfiles/vscode
			- wget https://raw.githubusercontent.com/omolazabal/dotfiles-linux/master/vscode/settings.json -P ~/dotfiles/vscode
			- rm ~/.config/Code/User/settings.json
			- ln -s ~/dotfiles/vscode/settings.json ~/.config/Code/User/settings.json

			- wget https://raw.githubusercontent.com/omolazabal/dotfiles-linux/master/vscode/keybindings.json -P ~/dotfiles/vscode
			- rm ~/.config/Code/User/keybindings.json
			- ln -s ~/dotfiles/vscode/keybindings.json ~/.config/Code/User/keybindings.json
			

- ZSH
	- fancy shell
	- Installation
		- Mac
			- brew install zsh
			- sh -c "$(wget -O- https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
			- Make it the default shell
		- Linux
			- sudo apt install zsh -y
			- sh -c "$(wget -O- https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
			- Make it the default shell
	- Use my dotfile
	    - Mac
            - mkdir -p ~/dotfiles/zsh
            - wget https://raw.githubusercontent.com/omolazabal/dotfiles-mac/master/zsh/.zshrc -P ~/dotfiles/zsh
            - rm ~/.zshrc
            - ln -s ~/dotfiles/zsh/.zshrc ~/.zshrc
            - mkdir -p "$HOME/.zsh"
            - git clone https://github.com/sindresorhus/pure.git "$HOME/.zsh/pure"
            - brew install autojump
            - git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
            - git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
            - source ~/.zshrc
	    - Linux
            - mkdir -p ~/dotfiles/zsh
            - wget https://raw.githubusercontent.com/omolazabal/dotfiles-linux/master/zsh/.zshrc -P ~/dotfiles/zsh
            - rm ~/.zshrc
            - ln -s ~/dotfiles/zsh/.zshrc ~/.zshrc
            - mkdir -p "$HOME/.zsh"
            - git clone https://github.com/sindresorhus/pure.git "$HOME/.zsh/pure"
            - sudo apt install autojump -y
            - git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
            - git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
            - source ~/.zshrc

