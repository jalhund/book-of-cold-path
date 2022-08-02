# Create server

#### Rent server

First you need to rent a server (well, or use your computer if the provider allows it)

In this topic, I will try to write specific OS, in fact, this is not so important. I will disassemble the launch and configuration of the server on a specific Linux Debian so that there is no confusion. On all other systems, you can do by analogy

First you need to rent a suitable server. A VPS with 512 MB of RAM fits without problems. The game server is well optimized, you can keep one or more game servers, then this should be enough for you.

After you have bought it, you will receive an email with:

1. ip address of the server (which you will use to connect)
2. login and password OS: debian9 (you can use another, but in this topic it will be used)

#### Programs

In order to interact with the server on a PC, you need to download:

1. Putty - SSH client to connect to and manage server
2. Any FTP client (for example, FileZilla, if it is available on a rented server tariff. If FTP connection is not available, then download WinSCP)

You can also manage the server using your phone. For example, on Android, you can use the following programs:

1. Termius for connecting via ssh
2. CX explorer for working with server files via ftp or sftp

#### Initial server setup

So, you should write the this commands only once. This is the initial setting, you write these commands first, then you can forget about it

So, connect to the server via IP, enter the username and password.

Next, write commands (if it requires input and the inscription "Do you want to continue? \[Y / n]" appears, then press y on the keyboard)

Updating data about repositories

```
apt update 
```

Install LuaJIT

```
apt-get install luajit
```

Install LuaSocket:

```
apt-get install lua-socket
```

Install LuaSec

```
apt-get install lua-sec
```

Install Screen

```
apt-get install screen
```

Install the nano editor (to quickly edit the code in the console)

```
apt-get install nano
```

Installing Git to download the latest version of the server for Cold Path

```
apt-get install git
```

#### Server downloading and starting

We have not downloaded the server yet, and it is better to prepare for this. So, type the command

```
screen -S server1
```

(this is necessary so that when you exit the console, the server remains running in the background. It also helps a lot in that it helps to switch between open programs in the console. Read more about Screen utility in Internet)

Next, create a folder in which our server will be

```
mkdir server1
```

See elements in directory

```
ls
```

Okay, the folder has been created. Now let's move into it.

```
cd server1
```

We will drop our server into this folder. Write command to download the latest version of the server:

```
git clone https://github.com/JAlHund/cold-path-server
```

Or just upload the downloaded sources to the server in another way

We have downloaded a copy of game server to the server. Now let's go to game server folder

```
cd cold-path-server
```

See elements in directory

```
ls
```

Give permission to the script to run

```
chmod +x start.sh
```

Start server

```
./start.sh
```

As you can see, server has started, and now you can connect to it in the game

Select Direct Connection from the Join menu and write ip:port (example: 127.0.0.1:5555). Default port is 5555
