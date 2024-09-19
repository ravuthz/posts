# Show the listening PORTs in any OS via CLI

This post will show you how to list the listening **ports** in **Linux**, **MacOS** and **Windows** using the command line interface with existing packages or third-party packages.

![](https://miro.medium.com/v2/resize:fit:1400/format:webp/1*AbELvvb4TSnzHn024Im8VA.png)

### Linux

In Linux, the **netstat**, **lsof** or **ss** command can be used to find open or listening ports.


1. Using lsof:

```bash
sudo lsof -i -P -n | grep LISTEN
```

Options:

-i: Display network files (Internet connections) only.
-P: Show only listening ports.
-n: Show numerical addresses instead of resolving hostnames.
| grep LISTEN: Pipes (|) the output to grep to filter and display only lines containing the word "LISTEN", which indicates listening network ports.

2. Using netstat:

```bash
sudo netstat -tuln | grep LISTEN
```

Options:

-t : Show TCP ports.
-u : Show UDP ports.
-l : Show only listening ports.
-n : Show numerical addresses instead of resolving hostnames.

3. Using ss:
Is a modern alternative to netstat and is generally faster.

```bash
sudo ss -tuln | grep LISTEN
```

Options:

-t : Show TCP ports.
-u : Show UDP ports.
-l : Show only listening ports.
-n : Show numerical addresses instead of resolving hostnames.


### MacOS
In macOS, the **netstat** or **lsof** command can be used to find open or listening ports.

1. Using netstat:
```bash
sudo netstat -tuln
```

2. Using lsof:

```bash
sudo lsof -i -P -n | grep LISTEN
```

3. Using nmap (optional):
```bash
brew install nmap

nmap -p- localhost
```


### Windows

1. Use the built-in **netstat** command:
```bash
netstat -an | find "LISTEN"
```
Alternatively, to get a more detailed view with process IDs:
```bash
netstat -ano | find "LISTEN"
```

2. Using **tasklist**
```bash
tasklist | findstr [PID]
```

Support me if you like this posts :)

https://ko-fi.com/ravuthz

https://www.buymeacoffee.com/ravuthz
