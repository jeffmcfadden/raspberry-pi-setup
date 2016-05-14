    sudo apt-get update
    mkdir installs
    cd installs
    sudo apt-get install git wget vim

    wget https://cache.ruby-lang.org/pub/ruby/2.3/ruby-2.3.1.tar.gz
    tar -zxvf ruby-2.3.1.tar.gz
    cd ruby-2.3.1
    sudo apt-get install autoconf gcc g++ make bison libyaml-dev libssl-dev libffi-dev zlib1g-dev libxslt-dev libxml2-dev libpq-dev zip libreadline-dev

     # RPi B+ ONLY:
    ./configure --disable-install-doc && make clean && make && sudo make install

    # RPi 2+ ONLY:
    ./configure --disable-install-doc && make clean && make -j4 && sudo make install

    sudo gem install bundler



    sudo apt-get install postgresql postgresql-contrib libpq-dev

    sudo -i -u postgres
    createuser -s -P rails #set password
    exit

    sudo vim /etc/postgresql/9.4/main/pg_hba.conf

    # change this: # "local" is for Unix domain socket connections only

    sudo service postgresql restart

    sudo apt-get install nginx

    sudo apt-get install upstart

    # Restart
    sudo shutdown -r now

    # Set motd
    sudo vim /etc/motd

    # Set hostname
    sudo vim /etc/hostname # Reboot afterward to take effect




    cd installs
    mkdir node
    cd node
    wget https://nodejs.org/dist/v4.2.4/node-v4.2.4-linux-armv7l.tar.gz
    tar -zxvf node-v4.2.4-linux-armv7l.tar.gz
    cd node-v4.2.4-linux-armv7l
    sudo cp -R * /usr/local/
    sudo apt-get install libavahi-compat-libdnssd-dev


    #REDIS

    sudo apt-get install redis-server
    # Do this: #See: https://gist.github.com/bdotdub/714533
    sudo start redis-server

    # uPNP manager
    sudo apt-get install miniupnpc


