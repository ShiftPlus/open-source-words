git + hub = github hub is a command line tool that wraps git in order to extend it with extra features and commands that make working with GitHub easier. ``` sh $ hub clone rtomayko/tilt expands to: $ git clone git://github.com/rtomayko/tilt.git ``` hub is best aliased as git, so you can type $ git <command> in the shell and get all the usual hub features. See "Aliasing" below. See Usage documentation for the list of all commands and their arguments. Installation Dependencies: git 1.7.3 or newer Homebrew hub can be installed through Homebrew on macOS: sh $ brew install hub $ hub version git version 1.7.6 hub version 2.2.3 Windows hub can be installed through Scoop on Windows: ``` sh scoop install hub ``` Fedora Linux On Fedora you can install hub through DNF: sh $ sudo dnf install hub $ hub version git version 2.9.3 hub version 2.2.9 Arch Linux On Arch Linux you can install hub from official repository: sh $ sudo pacman -S hub Standalone hub can be easily installed as an executable. Download the latest compiled binaries and put it anywhere in your executable path. Source With your GOPATH already set up: sh $ go get github.com/github/hub $ cd "$GOPATH"/src/github.com/github/hub $ make install prefix=/usr/local Prerequisites for compilation are: make Go 1.8+ Ruby 1.9+ with Bundler - for generating man pages Aliasing Using hub feels best when its aliased as git. This is not dangerous; your normal git commands will all work. hub merely adds some sugar. hub alias displays instructions for the current shell. With the -s flag, it outputs a script suitable for eval. You should place this command in your .bash_profile or other startup script: sh eval "$(hub alias -s)" PowerShell If youre using PowerShell, you can set an alias for hub by placing the following in your PowerShell profile (usually ~/Documents/WindowsPowerShell/Microsoft.PowerShell_profile.ps1): sh Set-Alias git hub A simple way to do this is to run the following from the PowerShell prompt: sh Add-Content $PROFILE "`nSet-Alias git hub" Note: Youll need to restart your PowerShell console in order for the changes to be picked up. If your PowerShell profile doesnt exist, you can create it by running the following: sh New-Item -Type file -Force $PROFILE Shell tab-completion hub repository contains tab-completion scripts for bash, zsh and fish. These scripts complement existing completion scripts that ship with git. Installation instructions hub bash completion hub zsh completion hub fish completion Meta Home: https://github.com/github/hub Bugs: https://github.com/github/hub/issues Authors: https://github.com/github/hub/contributors