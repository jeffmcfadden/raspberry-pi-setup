# First Things

    sudo apt update
    sudo apt upgrade
    mkdir installs
    cd installs
    sudo apt install git wget vim

# SSH Setup

## Copy Key
    ssh-copy-id pi@<raspberry_pi_ip>

## Update config
    HOST [raspberry_pi_host_or_ip]
    User pi
    PreferredAuthentications publickey
    IdentityFile ~/.ssh/[key_file]

## Test
    ssh [raspberry_pi_host_or_ip]

# Ruby

## Update and install basic build tools
    sudo apt update
    sudo apt install -y \
    autoconf \
    bison \
    build-essential \
    libssl-dev \
    libyaml-dev \
    libreadline6-dev \
    zlib1g-dev \
    libncurses5-dev \
    libffi-dev \
    libgdbm6 \
    libgdbm-dev \
    libdb-dev \
    libjemalloc-dev \
    git \
    curl

## Install rustup (for YJIT)
    curl https://sh.rustup.rs -sSf | sh -s -- -y
    source $HOME/.cargo/env

## Download source & Install

    wget https://cache.ruby-lang.org/pub/ruby/3.4/ruby-3.4.3.tar.gz
    tar -zxvf ruby-3.4.3.tar.gz
    cd ruby-3.4.3
    ./configure --enable-yjit --with-jemalloc
    make -j$(nproc)
    sudo make install
    sudo chown -R $(whoami):$(whoami) /usr/local/lib/ruby/gems/3.4.0