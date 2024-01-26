Edit by Jan 26, 2024

- [01 First Step: Connect VPN](#01-first-step-connect-vpn)
- [02 Via SSH connect Hipergator](#02-via-ssh-connect-hipergator)
    - [0201 Through Terminal](#0201-through-terminal)
    - [0202 Through VScode](#0202-through-vscode)
    - [0203 Connect](#0203-connect)

# Hipergator

HiPerGator is the University of Florida's supercomputer.

## 01 First Step: Connect VPN
Before connecting Hipergator, you need use the [Gatorlink VPN](https://it.ufl.edu/ict/documentation/network-infrastructure/vpn/). 
>  The Gatorlink VPN service provides secure remote access to the University of Florida network and makes it appear as if your computer were physically attached to the campus network. By using the Gatorlink VPN client, you may access resources on the UF network that are not typically available over an Internet path. 


## 02 Via SSH connect Hipergator

### 0201 Through Terminal

Use `terminal.app` in mac to connect 
```
ssh uf_username@hpg.rc.ufl.edu
```
Please change `uf_username` to your uf username.

<!-- ![img001](./img/001.png) -->
<p align="center">
  <img src="./img/001.png" width="500">
</p>

After typing password and select option, you are in the Hipergator.

*You can use terminal to access the config, but I strongly recommand to use VScode. The guide is in 0202.*

<!-- ![img004](./img/004.png) -->
<p align="center">
  <img src="./img/004.png" width="500">
</p>

*Using nano could edit config file.*

### 0202 Through VScode

[Offical Documents](https://help.rc.ufl.edu/doc/SSH_Using_VSCode)

**Step1:** Install the Extension of SSH from extensions store.

<!-- ![img002](./img/002.png) -->
<p align="center">
  <img src="./img/002.png" width="500">
</p>


**Step2:** Setup SSH config

After installing, you can see the `Remote Explorer` in left bar. 
Click it, and `move your mouse on the SSH`, you will find the gear.

Click to `Open SSH Config File`.

<!-- ![img003](./img/003.png) -->
<p align="center">
  <img src="./img/003.png" width="500">
</p>


**Step3:** Copy&Paste and edit config
[Offical Documents](https://help.rc.ufl.edu/doc/SSH_Multiplexing)

```
Host hpg
    User uf_username
    HostName hpg.rc.ufl.edu
    ControlPath ~/.ssh/cm-%r@%l-%h:%p
    ControlMaster auto
    ControlPersist 8h
```
Please change `uf_username` to your uf username.

The last three line help for SSH Multiplexing to avoid having to go through MFA for every connection.

<!-- ![img005](./img/005.png) -->
<p align="center">
  <img src="./img/005.png" width="500">
</p>


### 0203 Connect

There are two ways in VScode. You can see two arrows in the image006.
<!-- ![img006](./img/006.png) -->
<p align="center">
  <img src="./img/006.png" width="500">
</p>


Now you can type `ssh hpg` in the terminal to connect.
<p align="center">
  <img src="./img/008.png" width="500">
</p>

## 03 