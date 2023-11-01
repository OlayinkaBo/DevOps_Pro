# Understanding Client Server architechture with MYSQL as RDBMS

Client-Server refers to an architechture in which two or more computers are connected together over a network to send and receive requests between one another.

This can be illustrated with the diagram below :

![Alt text](<Images/Client server.PNG>)


In the above example, a machine that is trying to access a Web site using Web browser or simply `curl` command is a client and it sends HTTP requests to a Web server (Apache, Nginx, IIS or any other) over the internet.

If we extend this concept further with the addition of a Database Server, we get the below architecture : 

![Alt text](<Client server database.PNG>)

In this case, our webserver has the role of a "Client" that connects and reads/writes to/from a Database (DB) server (MYSQL, MongoDB, Oracle, SQL server or any other) and the communication between them happens over a local Network (since it is a common practice the place the Web server and the DB server close to each other in a local Network) or through internet connection.

An example of the set up in the above diagram is the LAMP or LEMP stack previously implemented.

With reference to the LAMP stack project where we implemented a LAMP STACK website, we will use a commercially deployed LAMP website `www.propitixhomes.com` as an example.

This LAMP website server(s) can be located anywhere in the world and you can reach it also from any part of the globe over the internet.

By typing `www.propitixhomes.com` on your browser, your browser becomes the "Client" by sending request to the remote server and in turn wait for response from the remote server.

Let's do a quick demo of a client - server communication.

On windows or Ubuntu terminal run the `curl` command.

`curl -Iv www.propitixhomes.com`

In this example, your terminal is the client and `www.propitixhomes.com` is the server.

The response from the remote server as seen in the below output shows that the URL is being served by a computer with an IP address 75.2.115.196 on port 80

![Alt text](<Images/server IP.PNG>)

The IP address of the server can also be gotten by using the `ping` command.


## Implement a Client Server Architecture using MYSQL Database Management System (DBMS).

To demonstrate a basic Client-server using MYSQL RDBMS, follow the below instructions.

1. Create and configure two linux based virtual servers (EC2 instances in AWS).


Server A name - `mysql server`

Server B name - `mysql client`


2. On  `mysql server` Linux Server, install MySQL **server** software.

![Alt text](<Images/Install mysql server.PNG>)

3. On  `mysql client` Linux Server, install MySQL **Client** software.

![Alt text](<Images/Install mysql client.PNG>)

4. By default, both of our EC2 virtual servers are located in the same local virtual network, so they can communicate with each other using local IP addresses. We use `mysql server’s` local IP address to connect from `mysql client`. MySQL server uses TCP port 3306 by default, so we must open it by creating a new entry in ‘Inbound rules’ in ‘mysql server’ Security Groups. For extra security, do not allow all IP addresses to reach the ‘mysql server.’ Only allow access to the specific local IP address of the ‘mysql client.’

![Alt text](<Images/Local IP comm.PNG>)


5. To configure MySQL server to allow connections from remote hosts, use vim to open the mysqld.cnf file with this command:

`sudo vi /etc/mysql/mysql.conf.d/mysqld.cnf`

Search for the bind-address and Replace ‘127.0.0.1’ to ‘0.0.0.0’ like this:

![Alt text](<Images/VI Server.PNG>)

![Alt text](<Images/Bind address change.PNG>)

After configuring mysql server to allow connections from remote hosts, we need to create a remote user that can access our database from remote hosts. To do this, we first connect to our mysql database on the mysql server EC2 instance:

`sudo mysql`

![Alt text](<Images/sql login.PNG>)

We can list all users in our database with the command:

`select user,plugin,host from mysql.user;`

![Alt text](<Images/mysql user list.PNG>)

This displays the list of all users that can access our database. To create a new remote user:

`CREATE USER 'olayinka'@'172.31.20.12' IDENTIFIED WITH mysql_native_password BY 'olayinka123';`

If we use the % sign, it will allow all connections from remote hosts but in this case it is specific to the ip address indicated. olayinka is the username, and the password is olayinka123, as shown in the command.

![Alt text](<Images/mysql user created.PNG>)

To verify our new user has been created, we run the command:

`select user,plugin,host from mysql.user;`

![Alt text](<Images/mysql user created verify.PNG>)

And we can see that user olayinka is now created.

Connecting to database from MySQL Client EC2 instance.

After creating the remote user, we can now head to the mysql client EC2 instance shell and connect to the database by using the command:

`mysql --host=172.31.42.132 --user=olayinka --password=olayinka123`

    NB: The IP address in the command is the private IP address of the MySQL Server EC2 instance.

![Alt text](<Images/connection established.PNG>)

The connection was successful. We can now start running queries on the database:

`show databases;`

![Alt text](<Images/show databases.PNG>)


With this, we have successfully implemented a client-server architecture using MySQL DBMS on AWS.

## Thank you!