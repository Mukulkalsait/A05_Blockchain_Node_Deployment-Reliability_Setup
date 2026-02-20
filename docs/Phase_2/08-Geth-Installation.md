
## 2.1 Install Geth (Ubuntu 24.04)

- Validated Ethereum execution client availability and version compatibility on Ubuntu 24.04.
- The installation is quiet simple, all we have to do is add ppa with software-properties-common and update and run ""**apt install geth**" , and done.

```bash
sudo apt update
sudo apt install -y software-properties-common # to get add-apt-repository command


sudo add-apt-repository -y ppa:ethereum/ethereum # official ethereum ppa

sudo apt update
sudo apt install -y geth
```


> Post Installation Orignal OP
```bash

mukul in  Ubuntu-24 in ~ took 15m44s
❯ geth version
Geth
Version: 1.17.0-stable
Git Commit: 0cf3d3ba4f7062fd2bbf2bda10972d528974e876
Architecture: amd64
Go Version: go1.25.1
Operating System: linux
GOPATH=
GOROOT=

mukul in  Ubuntu-24 in ~
❯





```
