---
description: Notes for the training session on Apr 11
---

# Session 1

## Setup

Start with a fresh Ubuntu install. I use vagrant.

```text
vagrant init ubuntu/bionic64
vagrant up
vagrant ssh
```

Update and upgrade.

```text
sudo apt-get update && sudo apt-get upgrade -y
```

Install the build dependencies. We will be working with 32 bit binaries so install support for that.

```text
sudo dpkg --add-architecture i386 
sudo apt-get update
sudo apt-get install -y build-essential libc6-dev-i386 vim make build-essential \
libssl-dev zlib1g-dev libbz2-dev libreadline-dev libsqlite3-dev wget curl llvm \
libncurses5-dev libncursesw5-dev xz-utils tk-dev libffi-dev liblzma-dev \
python-openssl git
```

Install Pyenv and Python 2.7

```text
curl https://pyenv.run | bash
# Add the pyenv autoload to your .bashrc after it prompts you to
pyenv install 2.7.16
pyenv global 2.7.16
```

Install the hackery dependencies.

```text
sudo apt-get install -y gdb libssl-dev libffi-dev
pip install -U pip 
pip install -U pwntools requests ipython
wget -q -O- https://github.com/hugsy/gef/raw/master/scripts/gef.sh | sh
```

Clone the session's material.

```text
git clone https://github.com/NUSGreyhats/ctf101-systems-security-2017.git
```

## Exercises

Maneuver into the newly cloned repository's `Challenge` directory.

### Fate

Build the challenge binary.

```text
cd fate
make
```

Solve the challenge.

### Impossible

Solve the challenge.

### Seashells

Solve the challenge.

### Impossible-Net

`nc training.pwn.sg 31337`

### Goldrush

`nc training.pwn.sg 31338`

