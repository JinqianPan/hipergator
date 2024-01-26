Edit by `Jan 26, 2024`

## Content Table
- [01 First Step: Connect VPN](#01-first-step-connect-vpn)
- [02 Via SSH connect Hipergator](#02-via-ssh-connect-hipergator)
    - [0201 Through Terminal](#0201-through-terminal)
    - [0202 Through VScode](#0202-through-vscode)
    - [0203 Connect SSH](#0203-connect-ssh)
- [03 03 Introduce to hipergator](#03-introduce-to-hipergator)
    - [0301 Storage](#0301-storage)
        - [030101 Intro for storage](#030101-intro-for-storage)
        - [030102 Code for accessing different storage](#030102-code-for-accessing-different-storage)
        - [030103 Groups](#030103-groups)
    - [0302 Recourses](#0302-recourses)
    - [0303 Coding](#0303-coding)
        - [030301 VScode & Terminal](#030301-vscode--terminal)
        - [030302 Jupyter Notebook (Website, OOD)](#030302-jupyter-notebook-website-ood)

***

# Hipergator

HiPerGator is the University of Florida's supercomputer. [Official Documents for Hipergator](https://help.rc.ufl.edu/doc/Getting_Started)

## 01 First Step: Connect VPN
Before connecting Hipergator, you need use the [Gatorlink VPN](https://it.ufl.edu/ict/documentation/network-infrastructure/vpn/). 
>  The Gatorlink VPN service provides secure remote access to the University of Florida network and makes it appear as if your computer were physically attached to the campus network. By using the Gatorlink VPN client, you may access resources on the UF network that are not typically available over an Internet path. 

***

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

[Official Documents for VScode](https://help.rc.ufl.edu/doc/SSH_Using_VSCode)

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

[Official Documents for SSH Multiplexing](https://help.rc.ufl.edu/doc/SSH_Multiplexing)

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


### 0203 Connect SSH

There are two ways in VScode. You can see two arrows in the image006.
<!-- ![img006](./img/006.png) -->
<p align="center">
  <img src="./img/006.png" width="500">
</p>


Now you can type `ssh hpg` in the terminal to connect.
<p align="center">
  <img src="./img/008.png" width="500">
</p>

***

## 03 Introduce to hipergator
### 0301 Storage 

[Official Documents for Storage](https://help.rc.ufl.edu/doc/Storage)

The storage has be divided in 4 part: home storage, blue storage, orange storage, and red storage.

Generally, we use home storage, blue storage, and orange storage.

#### 030101 Intro for storage

**Home Storage:** When you log in, the first thing that appears in front of you is home storage. 
> It is permissible to keep `software builds, conda environments, text documents, and valuable scripts in $HOME` as it is somewhat protected by daily snapshots.

**Blue Storage:** This part is responsible for reading and writing. Under the condition that the data can be placed, we will put the data required for code running in this area.

**Orange Storage:** Data storage area (if our data can't be put in the blue storage, we will also put the data here).

`Run Efficiency:` Home Storage > Blue Storage > Orange Storage

`Storage Space:` Orange Storage >> Blue Storage >> Home Storage

#### 030102 Code for accessing different storage 

**Path**
```
cd /blue
cd /orange
```

**Checking Quotas and Managing Space**
```
home_quota
blue_quota
orange_quota
```

#### 030103 Groups

We cannot store our data directly in storages. We need first check what group we are. `And then store the data in that group.`
```
slurmInfo
```
This code would display resource usage for your group.

### 0302 Recourses

### 0303 Coding

In this part, we only introduce how to write Python code in VScode and Jupyter notebook.

#### 030301 VScode & Terminal

**Python environments:** 


#### 030302 Jupyter Notebook (Website, OOD)
