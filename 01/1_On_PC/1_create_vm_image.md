# Creating VM Image

  **Scenario :** Cosmetic Evolution Shoppingmall severs

  **Hands-on Location :** Your Labtop

  **Prerequisition :** Windows 10 above 

---


## VM Environment

### 1. Download and Install VMware Workstation pro 

    https://www.vmware.com/products/workstation-pro/workstation-pro-evaluation.html

### 2. Download CentOS 7.8

[CentOS 7.8.2003 Download Link](https://ftp.iij.ad.jp/pub/linux/centos-vault/7.8.2003/isos/x86_64/CentOS-7-x86_64-DVD-2003.iso)

### 3. Install CentOS 7.8 

- In Workstation Pro menu, [Edit] > [Preference]:    Select Default Hardware compatibility : *** Workstation 16.2x ***
![image](https://github.com/scp-cloudacademy/ce-advanced/assets/147478897/d4c977e8-95e6-4fad-b094-dfd1c963d55c)

- After Completing CentOS installation,
  log in as root account,

 ```
sudo SYSTEMCTL set-default multiuser.target ## CLI 모드로 부팅
shutdown now
```

### 4. Clone VM Image for Wen/App/DB VM
- In Workstation Pro left Library pane, select Vm Image just created and right mouse click
![image](https://github.com/scp-cloudacademy/ce-advanced/assets/147478897/450c23a0-8c25-454e-9519-2e3e34e3e6a8)

- Clone 3 VMs and rename webvm, appvm dbvm
![image](https://github.com/scp-cloudacademy/ce-advanced/assets/147478897/0812f214-a99c-4ab0-bdda-916f839213a1)
---






