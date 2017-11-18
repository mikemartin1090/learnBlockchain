# Learn How to Build a Blockchain

Following the 
[Hackernoon Blockchain Guide](https://hackernoon.com/learn-blockchains-by-building-one-117428612f46 "Build a Blockchain") using my Windows 10, 1703 machine [with Bash on Ubuntu on Windows.](https://evdokimovm.github.io/windows/zsh/shell/syntax/highlighting/ohmyzsh/hyper/terminal/2017/02/24/how-to-install-zsh-and-oh-my-zsh-on-windows-10.html "Win 10 Runs Ubuntu"), I realized I knew nothing about setting up Python/PIP in a newly installed environment.

## Setting up the Environment

This project requires Python 3.6+

```
➜  python3 --version
Python 3.5.2
```

My Win 10 Ubuntu is running 3.5.2. How do I update? [Found this](
http://ubuntuhandbook.org/index.php/2017/07/install-python-3-6-1-in-ubuntu-16-04-lts/ "Install Python 3.6")

```
# add the python 3.6 repository
sudo add-apt-repository ppa:jonathonf/python-3.6

# update local repositories
sudo apt-get update

# install 3.6
sudo apt-get install python3.6
```

To keep everything neat, let's put this new python in a [virtual environment](http://docs.python-guide.org/en/latest/dev/virtualenvs/ "Virtual Environments")
```
# install virtual environment
sudo apt-get install python3.6-venv

# create the virtual environment file
python3.6 -m venv .venv

# source the venv file
source .venv/bin/activate
```

Now that we are in the environment, lets get some more pre-reqs installed. Perks of being in an environment mean we don't mess up our 'prod' version of Ubuntu.
```
# get latest pip
pip install --upgrade pip

# if pip isn't installed, we should install
sudo apt install python3-pip

# called for in article
pip install Flask==0.12.2 requests==2.18.4

# article asks for a http client - piper recommends httpie, but postman is also a good option.
pip install httpie
```

The rest of the article was pretty staight forward - I'm about half way through. Will update here with any issues that I found...

Oh! And if you want to get out of your virtual python environment, just execute the `deactivate` command.


## Gotchas

1. Don't move your project directory around. There are hard coded paths in your .venv files. For instance, I moved my directory down one level, but 12 files, including the activate file referenced the original path. This will lead you to believe the venv isn't working when it shows you an older version of python. `VIRTUAL_ENV="/mnt/c/Users/mmartin/github/public/learnBlockChain/.venv"`

## Definitions

Immutable - unchanging over time or unable to be changed

Sequential - forming or following in a logical order or sequence. One after the other

## References

Made With Help from [Markdown Cheatsheets](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet "Markdown Cheatsheets")