# cheatshh ![Static Badge](https://img.shields.io/badge/version-1.0.6-blue)

Cheatshh is an interactive CLI meant for managing command line cheatsheets, written in shell script. Now you don't have to remember CLI commands and just refer your cheatsheet. You can group commands and view their TLDR and MAN pages along with a custom description for the command.

# Preview/Screenshots 

https://github.com/AnirudhG07/cheatshh/assets/146579014/831405bb-aba4-461f-9ca9-e0f75d74155d

# Features

- Comprehensive cheatsheets for various command-line utilities and tools.
- Easy-to-use interface for quickly accessing and executing commands, powered by fuzzy finder(fzf) and whiptail.
- Customizable cheatsheets and groups to suit your needs.
- TLDR and MAN pages visible in the preview.
- Easy to add, edit, delete commands & groups and play around.
- Bookmark commands to access them outside of group as well.

# Installation

The following installation guidelines hold for Linux and MacOS.<br>
You can download cheatshh through following ways- (more will be added soon)

## Pip Installation

Before running the below commands, make sure your dependencies are satisfied. See the DEPENDENCIES section for more info.
From your command line, run-

```bash
pip install cheatshh
```

This will create ~/.config/cheatshh in your home directory. Now simply run-

```bash
cheatshh
```

and you are done. Use various options to add, edit and delete commands and groups.

## Homebrew Installation

This tool can also be installed using Homebrew(for MacOS only). You can install it by tapping my homebrew-tap repo and installing the tool.

```bash
brew tap AnirudhG07/AnirudhG07
brew install cheatshh
```

You can now run the tool by running `cheatshh -h` in your terminal. If you are facing issues, try running-

```bash
brew install AnirudhG07/AnirudhG07/cheatshh # After tapping the repo
```

Make sure you have Homebrew installed in your MacOS and it is updated which can be done by running `brew update`.

## Manual Installation through git clone

You can setup manual installation with the following guidelines-

### For MacOS and Linux

1. Clone the repository

```bash
git clone https://github.com/AnirudhG07/cheatshh
```

2. Navigate to the project directory run below if downloaded in home directory

```bash
cd ~/cheatshh
```

3. Install the requirements through

```
pip install -r requirements.txt
```

4. (optional) Make sure you have `poetry` installed which will be required to build the project. If not you can run either of the below commands-
```bash
pip install poetry
# OR
curl -sSL https://install.python-poetry.org | python -
```
This will download `peotry`. Now you can proceed to the next step.

5. Run the below code to set cheatshh

```bash
pip install .
```

Now you should be able to use the tool by running `cheatshh` in your terminal. Feel free to raise an issue if any error comes up.

## For Windows

For Windows, you can use Virtual Machines of Linux, or change configurations manually.<br>

- Change the path to directory `~/.config/cheatshh` to `/path/to/your/directory/cheatshh`, by using grep command
  in the cheatshh directory, in `setup.py`,`cheats.sh` and manually setting up `./src/run_cheatshh.py`.

- This should run cheatshh appropriately. Make sure the dependencies are installed, since they are easily available for Unix applications.

# Libraries and Groups

You can create custom groups using-

```bash
cheatshh -g
```

We also have premade libraries of groups <a href="https://github.com/AnirudhG07/cheatshh/tree/main/library"> here </a> which you can download with the instructions given there itself. <br>
We welcome you to publish your own libraries for everyone to see.

# Bookmarking
Bookmarking let's you save your command in the main preview despite them being present in a group.<br>
You can bookmark a command by pressing Enter and selecting `Bookmark`. Now you don't need to find it in a group and access it in the main preview.<br>You can always remove Bookmark of a command by pressing Enter and selecting `Remove Bookmark`.

# Dependencies

Cheatshh uses the following as its main tools. Ensure that these are pre-installed in your computer.

- fuzzy finder
- whiptail
- jq

In MacOS, you can use HomeBrew to install the above packages with-

```bash
brew install <package>
```

For MacOS & Linux both, you can run the following command to download the packages.

```bash
sudo apt install <package>
```

For Windows, you can use your favourite package manager or download from their website itself.

# Trouble-shooting

1. If permission denial error shows up, run the same command using sudo. You will have to provide password in this case.

```bash
sudo <command-name>
```

This might be needed in the case for man page display or maybe for installation of dependency.

2. If `WARNING: The script cheatshh is installed in '/home/admin/.local/bin' which is not on PATH.` error comes, then cheatshh script has to be included in the system PATH, you can add the following lines to the appropriate shell configuration.

- BASH: Add the following at the end of ~/.bashrc

```bash
export PATH="$HOME/.local/bin:$PATH"
```

- ZSH: Add the following at the end of ~/.zshrc

```bash
export PATH="$HOME/.local/bin:$PATH"
```

After adding these lines, either restart your terminal or run source on the respective configuration file to apply the changes. For example:

```bash
source ~/.bashrc  # For Bash
source ~/.zshrc   # For Zsh
```

This should add the path in your `shell-rc` file and you should be able to run.<br>
Note: If you are using some other shell like fish or any similar other, configure the settings accordingly. Using Fish is not recommended for this tool.

# Documentation

Cheatshh is an interactive, easy CLI tool to maintain your custom cheatsheets. You can check our the <a href="https://github.com/AnirudhG07/cheatshh/tree/1.0.6/docs"> docs </a> to see how to use cheatshh.

# Contributing

I would love to take contributions from the community! If you have suggestions for new cheatsheets, improvements to existing ones, or bug fixes, please feel free to submit a pull request. 
### Contribution Guidelines
1) For contribution of a library, it should have a suitable folder name(max 3 words) with commands.json and groups.json, similar to the format in other libraries. The `group` field should be "yes", `bookmark` field should be "no".
2) For bug fixes, it will be great if you could discuss first in Issues before directly putting a PR. 
3) It would be great to publish this in other package managers. So I would request help for publishing to different package managers.
