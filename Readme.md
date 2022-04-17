# origin-tools

This is an aggregation of my own CLI.
These tools consist of the following CLI.

- conn

Note: Please note that we basically only check them on Linux and mac.

## conn
conn CLI is made for connect to some servers through SSH (password auth).

### initial setup
Follow the steps below to perform the initial setup.

1. rename `servers.csv.sample` file to `servers.csv`, and modify your server information.
   ```bash
   $ cd origin_tools/
   $ mv servers.csv.sample servers.csv
   $ vi servers.csv
   NAME, IP_ADDR, USER, PASSWORD
   server1, <your-ipaddr>, <your-username>, <your-password>
   server2, <your-ipaddr>, <your-username>, <your-password>
   server3, <your-ipaddr>, <your-username>, <your-password>
   ...
   ```
2. "orign_tools" directory at your preferred location.
   ```bash
   $ sudo mv origin_tools/ /opt/
   ```
3. If necessary, create a symbolic link to the location where `PATH` is set so that CLI under bin directory can be executed without specifying the path.
   ```bash
   $ cd /usr/local/bin/
   $ sudo ln -s /opt/origin_tools/bin/conn conn
   ```

## How to use

1. Just type command `conn`, and press Enter key. So you can see server select menu.
   ```bash
   $ conn
   ```
   <img width="400" src="https://user-images.githubusercontent.com/6835793/163697301-e2c2c7f2-390b-4350-9773-626550e142b8.png">
   
2. select any server and press Enter key. So you can connect to the server.
   ```bash
   ...
   spawn env LANG=C /usr/bin/ssh root@master
   root@master's password: 
   Activate the web console with: systemctl enable --now cockpit.socket
   
   Last login: Sat Apr 16 05:25:21 2022 from 192.168.56.1
   [root@master ~]# 
   ```