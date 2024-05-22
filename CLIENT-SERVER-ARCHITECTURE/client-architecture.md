<h2><b>Implement a Client Server Architecture using MySQLDatabase Management System (DBMS)</b></h2>

<h3><b>Introduction</b></h3>
Implementing a Client-Server Architecture using a MySQL Database Management System (DBMS) involves setting up a server to host the MySQL database and clients to interact with the server. The server manages the database, handles queries, and ensures data integrity, while clients connect to the server over a network to request data, submit updates, and execute transactions. This architecture allows for centralized data management, improved data security, and scalable access for multiple clients.

<h3><b>Prerequisites</b></h3>
<ol><li> An AWS account with appropriate permissions to create and manage EC2 instances, Security Groups, and Key Pairs. </li>

<li>Basic familiarity with AWS services and the Linux command line interface.</ol></li>

<h3><b>Step 0 : Set up EC2 Instance</b></h3>

#### 1. Create and configure 2 EC2 instance type of t3.micro and Ubuntu 24.04 LTS (HVM) AMI type in eu-north-1 region. name one server "mysql-server" and the one "mysql-client"

<img src="images/mysql-server-details.JPG" alt="server">

<img src="images/mysql-client-details.JPG" alt="client">

#### 2. Create ssh key to access the 2 EC2 instances for secure access to the instances.
#### 3. Configure network security group to allow traffic on port 80 for HTTP connection, port 443 for HTTPS connection port 22 for SSH connection and port 3306 to the EC2 servers.For extra security, do not allow all IPaddresses to reach your 'mysql server' - allow access only to thespecific local IP address of your 'mysql client

#### 4. Connect to Instances via SSH
Before connecting to the instance, change the permission for the downloaded ssh key  to ensure your key is not publicly viewable with the command below:

```bash
sudo chmod 400 <private-key-name>.pem
```

After changing the permission, connect to the instance with the command below:

```bash
ssh -i "<private-key-name>.pem" ubuntu@<ip-address or dns-name>
```
<img src="images/server-connect.JPG" alt="server">

<img src="images/client-connect.JPG" alt="client">

#### 5. Update and Upgrade the packages on the 2 EC2 instances

```bash
sudo apt update
sudo apt upgrade -y
```

<img src="images/server-update.JPG" alt="server">
<img src="images/server-upgrade.JPG" alt="server">

<img src="images/client-update.JPG" alt="client">
<img src="images/client-upgrade.JPG" alt="client">

<h3><b>Step 1 : Set MySQL Server</b></h3>

#### 1. Install MySQL Server
To install MySQL server, run the following command from a terminal prompt:

```bash
sudo apt install mysql-server -y
```
<img src="images/mysql-server-install.JPG" alt="server">

#### 2. Start and enable mysql server service. Then check the status

```bash
sudo systemctl start mysql

sudo systemctl enable mysql

sudo systemctl status mysql
```
<img src="images/mysql-server-status.JPG" alt="mysql-server-status">

#### 3. Configure the MySQL server to allow connections from remote hosts. Navigate to the mysqld.cnf file 

```bash
sudo vi /etc/mysql/mysql.conf.d/mysqld.cnf
```
Then replace the bind address from '127.0.0.1' to '0.0.0.0'

<img src="images/mysql-server-conf.JPG" alt="mysql-server">

<h3><b>Step 2 : Set MySQL Client</b></h3>

#### 1. Install MySQL client
To install MySQL client, run the following command from a terminal prompt:

```bash
sudo apt install mysql-client -y
```
<img src="images/mysql-client-install.JPG" alt="client">

<h3><b>Step 3: Configure MySQL Server - Client Connetcion</b></h3>

#### 1. Set up secure installtion for MySQL Server
Run the folloeing command on mysql serve

```bash
sudo mysql_secure_installation
```
<img src="images/mysql-secure.JPG" alt="secure">

#### 2. Access Mysql server

```bash
sudo mysql
```

<img src="images/sudo-mysql.JPG" alt="sudo-mysql">

#### 3. Create an admin user for the database and grant all priveileges

```sql

CREATE USER 'admin'@'%' IDENTIFIED WITH mysql_native_password BY 'Admin.12345';

CREATE DATABASE demo_db;

GRANT ALL ON demo_db.* TO 'admin'@'%' WITH GRANT OPTION;

FLUSH PRIVILEGES;

```
<img src="images/mysql-user.JPG" alt="mysql-user">

#### 4. Connect remoetely to MySQL server from MySQL client without SSH

```bash
sudo mysql -u admin -h <ip-address-myswl-server> -p
```
<img src="images/mysql-user-connect.JPG" alt="mysql-user-connect">

#### 4. View all datbase to confirm the demo_db dsatbase created. Create a table and insert sample data

```sql
SHOW DATABASE;
```
<img src="images/mysql-db.JPG" alt="mysql-db">

#### 5. Create a table in the demo_db database and insert sample data

```sql
USE demo_db;
CREATE TABLE demo_table (
  ID INT AUTO_INCREMENT,
  name VARCHAR(50),
  PRIMARY KEY(ID)
);

INSERT INTO demo_table (name) VALUES ("Taofeek");

INSERT INTO demo_table (name) VALUES ("Alee");

SELECT * FROM demo_table;

```

<img src="images/mysql-table.JPG" alt="mysql-table">

The MySQL Client - Server Architecture is fully setup