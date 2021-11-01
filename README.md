# SEI Installfest - Mac OSX

## Unit 1

For the first portion of this class, we'll be working exclusively inside of the browser. 

We'll be installing the following tools:

* Slack
* Homebrew
* Xcode
* Zsh
* Git
* VS Code
* iTerm2

**TIP**: Use CTRL+SHIFT+V to paste commands into the terminal

### Slack

We will be using Slack to communicate throughout the course. You should've received an invite to our channels via e-mail. You can login via the web browser, but downloading / installing the app is highly recommended.

[Download Slack](https://slack.com/downloads)

### Homebrew

Homebrew is a package manager that we will use to install various command line tools in our class.

Visit the [homebrew website](https://brew.sh/) for install instructions.

You may be prompted to installed XCode command line tools. When prompted, click and install through that, and you're homebrew installation will continue.

After the installation process, run the command `brew doctor`. If any warnings or errors are displayed, we will need to resolve them before proceeding with the rest of the install fest.

### Xcode (if prompted)

We do not use Xcode in class but some other applications that we do use require some Xcode libraries. Normally, all you need is the Xcode CLI which should have already been installed when you installed Homebrew. If it didn't get installed, you can use this command:

```text
xcode-select --install
```

If you need to, you can install Xcode through the App Store. [Link here](https://itunes.apple.com/us/app/xcode/id497799835?mt=12)

### Zsh

Open the Terminal app on your mac (it's built-in). This is a **command line interface (CLI)** for a program called a **shell**. CLIs allow us to interact directly with our computer via text-based commands. 

Zsh is a shell that lets us interact with the operating system.
There are different types of shells you can use, but BASH and ZSH are currently the most popular for Unix systems. (Linux and Mac)

We will use Zsh in this class. If your Terminal is running Zsh, you'll see Zsh at the top of the shell window.

If your mac is running any of the following operating systems, your default shell is [ZSH](https://zsh.sourceforge.io/). 

* macOS Catalina – 10.15
* macOS Big Sur – 11
* macOS Monterey – 12

Here is how you change the default shell to Zsh if it isn't already:

* Run `brew install zsh`
* Run `chsh -s /bin/zsh` to change the default shell to Bash.
* Quit the Terminal app and re-open it (the whole app, not just the window).
* Verify that the window says Zsh at the top now, instead of Bash

[More on available shells for Unix systems (Linux & Mac)](https://bigstep.com/blog/top-5-linux-shells-and-how-to-install-them)



### GIT

Before we do this process, please make sure you have signed up for an account on [Github](http://www.github.com). We will be installing a version of GIT from home brew and also configuring it.

To install GIT

```text
brew install git
```

**Configuring GIT**

Using your email credentials for GIT, run these commands with your user and email configured.

```text
git config --global user.name "YOUR-GITHUB-USERNAME"
git config --global user.email "YOUR-EMAIL-ADDRESS"
git config --global credential.helper cache
git config --global init.defaultBranch main
```

**Setting up SSH Key** 

Follow the GitHub documentation for setting up an SSH Key to push code to GitHub securely.

* [Github Generating SSH Keys](https://help.github.com/articles/generating-ssh-keys/)

### VS Code

Currently the most popular editor according to developer polls. This is Microsoft's free version of Visual Studio.

Download and install VS Code from [here](https://code.visualstudio.com/download)

You're all good to go now, but for ease of use, let's make it so we can automatically open up any file or project in VS Code, from our command line. The following instructions are taken from [these docs](https://code.visualstudio.com/docs/setup/mac). If you're on Windows or Linux, see the left-side menu to switch to the instructions for your machine.

To be able to open VS Code from any directory, open the Command Palette \(Shift+⌘+P\) and type 'shell command' to find the Shell Command: Install 'code' command in PATH command \(it will be the first one that comes up\).

Restart the terminal for the new $PATH value to take effect. You'll be able to type 'code .' in any folder to start editing files in that folder.

### M1 Chip Users
If you are using a Mac with an M1 chip you may need to run this additional command in your terminal.

Please check with your instructors if the above instructions still don't allow you to run the `code` command in your terminal!

```
# Check with your instructors first!
# https://code.visualstudio.com/docs/setup/mac#_alternative-manual-instructions
cat << EOF >> ~/.zprofile
# Add Visual Studio Code (code)
export PATH="\$PATH:/Applications/Visual Studio Code.app/Contents/Resources/app/bin"
EOF
```

### iTerm2
Although not strictly required, iTerm2 is a tricked out version of the Terminal app that is the default command line interface. It will help with the visuals of the command line navigation, especially with ohMyZSH.

Install iTerm2 by copying the following homebrew command into your terminal:

```
brew install --cask iterm2
```
When it has completed, you will be able to find iTerm2 in your applications folder.

If you need to, you can also [download iTerm2 here](https://www.iterm2.com/) manually. Check out the features tab for all of the cool tricks iTerm2 does.

While using iTerm2 in the beginning it may ask your admin password or for permissions in the mac OS. Click 'yes' all the prompts.

### OhMyZsh

We will be tricking out command line even further with [Oh-My-Zsh](https://github.com/robbyrussell/oh-my-zsh). OhMyZsh provides very handy tools for easy configuration and customization of the look and feel of the command line.

Copy and past the following command into your terminal to install oh-my-zsh:

```text
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

Restart your terminal, and you should see a brand new and colorful command prompt.

### Setting the default shell editor To VS Code
Open up the Zsh configuration file by running the command `code ~/.zshrc` 

Next, add the follow lines towards the bottom to set your default shell editor to VS Code.


```
export EDITOR="code -w"
```
Save your .zshrc file and restart the terminal to enjoy!


---

## Unit 2

### Node
We'll be installing `node` via the Node Version Manager! (nvm)

The instructions can also be found on their site here: https://github.com/nvm-sh/nvm

```
# Install
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.0/install.sh | zsh

# Verify installation
command -v nvm

# Install the latest version of node
nvm install node

# Verify node and npm are installed
node --version
npm --version
```


### Postgres

**Postgres.app**

We will be using a relational database called Postgres during our class.

Download and install from [http://postgresapp.com/](http://postgresapp.com/)

Open up your `.zshrc` file in your Code editor \(`code ~/.zshrc` for VS code\) Your editor will popup with configuration settings, at the bottom of the file append

```text
export PATH=$PATH:/Applications/Postgres.app/Contents/Versions/latest/bin
```

Save the file and either restart your terminal or write `source ~/.zshrc` to apply your changes. To check if it worked, type `which psql` in your terminal at which point should display:

```text
/Applications/Postgres.app/Contents/Versions/9.5/bin/psql
```

---

## Part 3

### Installing MongoDB \(Updated 2/2021\)

**Notes:** The name of the free version of MongoDB has changed to `mongodb-community` as of November 2019. Also, the Catalina version of MacOS \(version 10.15\) disallows folders being created at the root of the file system so you must create your MongoDB data folder inside your home folder

```bash
# Download the official Homebrew formula for MongoDB and the Database Tools
brew tap mongodb/brew

#Install MongoDB
brew install mongodb-community@4.4
```

There are two ways to start your server: 1. As a macOS service 2. Manually as a background process

**As a Service**

```text
# Start
brew services start mongodb-community@4.4

# Stop
brew services stop mongodb-community@4.4
```

**As a Background Process**

```text
# For Mac running Intel processors
mongod --config /usr/local/etc/mongod.conf --fork

# For Apple M1 processors
mongod --config /opt/homebrew/etc/mongod.conf --fork
```

To stop the background process, you'll need to connect to your `admin` database in your mongo shell and run `db.shutdownServer()`.

```text
> use admin
> db.shutdownServer()
> exit
```

---

## Part 4

### Installing Python 3

Brew is also used to install Python 3. \(Python 2 is already installed on your Mac.\) To install Python 3 without errors, we first need to create a couple directories and change them to be owned by us:

```text
mkdir /usr/local/lib
mkdir /usr/local/Frameworks
whoami
```

Make a note of the username returned from `whoami`. Enter that username in place of USERNAME below:

```text
sudo chown -R USERNAME:wheel /usr/local/lib
sudo chown -R USERNAME:wheel /usr/local/Frameworks
```

If you received no errors from those commands, then use this command to install version 3:

```text
brew install python3
```

You can test the installation by running `python3 --version`.

This should also install `pip3`, a package installer for Python 3. You can verify that it is installed and working by updating it with the following command:

```text
pip3 install --upgrade pip setuptools wheel
```

This should return some normal messages - no errors. Now that `pip3` is working, we can use it to install a useful Python shell:

```text
pip3 install ipython
```

iPython makes it easy to write python code in your terminal. We may not use it a huge amount but it is handy to have around.

