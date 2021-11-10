# AJ's docker-demo
some examples of building redis and nginx containers using both ansible and docker-compose

**install docker:**

    sudo apt install docker.io

**install docker-compose and ansible:**

    sudo apt install python3-pip
    pip3 install -r requirments.txt

**Build and run with docker-compose:**

    docker-compose up -d
**Build and run with an ansible playbook:**

    ansible-playbook ansible-build.yaml -v

**is nginx working?**

`docker ps` should show 2 running containers.
in a browser visit `http://localhost:80` and you should be greeted with the nginx default welcome page

**is redis working?**

    # download redis-tools
    apt install redis-tools
    # run redis-cli then ping your local host on port 6379.
    # if you get a PONG back its working
    redis-cli
    127.0.0.1:6379> ping
    PONG

**Whats next?**
Next we customize and secure our apps by adding config files into each containers build context.
