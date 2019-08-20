# SSH Colorize

Add a file: /etc/profile.d/colorenv.sh

For staging (default text will be green):
```
export LS_COLORS="$LS_COLORS:no=32:ex=32;1:"
export PS1='\[\e[0;32m\][\u@\h \W]\$ '
```

For production (default text will be red):
```
export LS_COLORS="$LS_COLORS:no=31:ex=32;1:"
export PS1='\[\e[0;31m\][\u@\h \W]\$ '
```

# MySQL
Each application and administrator should have different username for database access. Therefore it's easy to spot which one made a query when things go wrong.

# Bash Profile
File `~/.bash_profile` is a nice place to customize your terminals. Here are some useful things to put there.

`whoseport`, coz it's hard to remember lsof parameters (or I'm too lazy to remember it :p)
```
function whoseport() {
    [ -z "$1" ] && echo "Usage: whoseport [port]" || lsof -i ":$1" | grep LISTEN
}
```

# Install Docker on CentOS

Download rpm from this path: https://download.docker.com/linux/centos/7/x86_64/stable/Packages/
3 files needed (download the latest version):
- docker-ce
- docker-ce-cli
- containerd.io

After downloaded:
```sh
sudo yum install containerd.io-xx.rpm docker-ce-cli-xx.rpm
sudo yum install docker-ce-xx.rpm
sudo systemctl start docker
sudo docker run --rm hello-world
```

Docker-compose:
```sh
sudo curl -L "https://github.com/docker/compose/releases/download/1.24.1/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
sudo chmod +x /usr/local/bin/docker-compose
```

Reference:
- https://docs.docker.com/install/linux/docker-ce/centos/
- https://docs.docker.com/compose/install/
