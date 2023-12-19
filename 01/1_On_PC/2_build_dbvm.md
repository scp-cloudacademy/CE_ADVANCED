# Building Database VM

  **Scenario :** Cosmetic Evolution Server

  **Hands-on Location :** Your Labtop

  **Prerequisition :** Windows 10 above, VM Workstation Pro, [CentOS 7.9 VM Image](https://github.com/scp-cloudacademy/ce-advanced/blob/main/01/02_build_vm_image.md))


### Step 1 – Prerequsitis
### Install and enable Remi 

    yum -y install epel-release      # Remi 저장소를 설치하고 활성화한다.
    yum -y install https://dev.mysql.com/get/mysql80-community-release-el7-11.noarch.rpm

### Install MySQL 8.0.35

    yum -y install mysql-server
    
### Check Version

    mysqld -V

### Start and Enable MySQL 

    systemctl start mysqld
    systemctl enable mysqld

    
### Check initial password
    
    grep 'temporary password' /var/log/mysqld.log

### Change password

    mysql -u root -p

example) ALTER USER 'root'@'localhost' IDENTIFIED BY 'abcd1234';

```mysql
ALTER USER 'root'@'localhost' IDENTIFIED BY 'VMuser1@';
```

### Allow access from external

```mysql
use mysql;
select host, user from user;
```

```mysql
CREATE USER 'vmuser'@'%' IDENTIFIED BY 'VMuser1@';
GRANT ALL PRIVILEGES ON *.* TO 'vmuser'@'%';
```

```mysql
FLUSH PRIVILEGES;
```

```mysql
select host, user from user;
```

```bash
systemctl restart mysqld
```
Open Firewall port

```
firewall-cmd --zone=public --permanent --add-port=3306/tcp    # 3306 for MySQL
firewall-cmd --zone=public --permanent --add-port=22/tcp      # 22 for SSH
firewall-cmd --reload                                         
firewall-cmd --zone=public --list-all                         
```

Download and Install MySQL Workbench

[https://www.mysql.com/products/workbench/](https://www.mysql.com/products/workbench/)

In Bation Host, Install and launch Workbench and upload schema

[cosmetic data](https://github.com/scp-cloudacademy/ce-advanced/raw/main/09/cosmetic_COSMETIC.sql)

[Movie data](https://github.com/scp-cloudacademy/ce-advanced/raw/main/09/cosmetic_MOVIES.sql)
