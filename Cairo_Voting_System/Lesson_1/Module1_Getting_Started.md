# Getting Started

Hello everyone! We have set up our project. This series will walk you though all the steps necessary to deploy your very own voting system which include being able to create proposals, vote for proposals and also be able to request tokens to be used for staking. There are a lot of prerequisites needed to be able to set up Starknet in your local machine for both developments and deployments. 

Now there are many resources to be able to setup starkup in your local environment.
There are [Starknet Docs](https://docs.starknet.io/guides/quickstart/environment-setup/) and [Cairo Book](https://book.cairo-lang.org/ch01-01-installation.html)



Also you must have experience with Rust syntax and concepts like borrowing and ownerships.

![Side eye](../assets/side-eye.gif)



# Installation Process

To make this easy for us, I have placed the command below to run to setup starkup on Linux or MacOs:

```
curl --proto '=https' --tlsv1.2 -sSf https://sh.starkup.sh | sh
```
You can verify that Scarb and Starknet Foundry are installed correctly by running:

```
scarb --version
snforge --version && sncast --version
```

The installation is deemed successful when you get a result like this:

```
scarb 2.11.4 (c0ef5ec6a 2025-04-09)
cairo: 2.11.4 (https://crates.io/crates/cairo-lang-compiler/2.11.4)
sierra: 1.7.0

snforge 0.42.0
sncast 0.42.0
```

For Windows:

It will be mostly advicable to download WSL in your system to make use of this command easily but this restricts your project to only making use of the WSL. So the use of homebrew is advised to be familar with. 

You can run this command this command to install WSL:

```
wsl --install
```

Open up the Ubuntu terminal and run these commands to update your wsl system:

```
sudo apt update
sudo apt install -y curl git build-essential
```

Install Homebrew and verify the installation:

```
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
echo 'eval "$(/home/linuxbrew/.linuxbrew/bin/brew shellenv)"' >> ~/.profile
source ~/.profile
brew --version
```

ASDF is another way to install starkup with Windows and we have installed homebrew to be able to install asdf. Run these commands to make install asdf and verify the installation:

```
brew install asdf
echo '. "$(brew --prefix asdf)/libexec/asdf.sh"' >> ~/.bashrc
source ~/.bashrc
asdf --version
```
After confirming asdf has been installed correctly, Run these commands to setup starkup and other packages to have starknet setup in your local environment: 

```
asdf plugin add scarb
asdf install scarb latest
asdf set -u scarb latest

asdf plugin add starknet-foundry
asdf install starknet-foundry latest
asdf set -u starknet-foundry latest

asdf plugin add starknet-devnet
asdf install starknet-devnet latest
asdf set -u starknet-devnet latest

scarb --version
snforge --version && sncast --version
starknet-devnet --version
```

Not Bad Aye?

![thumbs-up](../assets/thumbs-up-elon.gif)

Congratulations you have passed the stage of installing and setting up starknet on your local machine. Next?
You should go tp the next module of this chapter.

