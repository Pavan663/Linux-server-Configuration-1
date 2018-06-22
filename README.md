# Udacity-Linux-Server-Configuration-428
### About
  This is the Udacity project 6 about the Configuring the Linux the server.Take a baseline installation of a Linux distribution on a virtual machine and prepare it to host your web applications,and installing/configuring web and database servers.
### Server IP details
Server IP Address 13.232.118.69

Hosted site Url [http://13.232.118.69.xip.io/](http://13.232.118.69.xip.io/)

### Procedure
1. Launch Virtual Machine with Udacity account
2. Follow the instructions provided to SSH into your server
3. Create a new user named grader
4. Give the grader the permission to sudo
5. Update all currently installed packages
6. Change the SSH port from 22 to 2200
7. Configure the Uncomplicated Firewall (UFW) to only allow incoming connections for SSH (port 2200), HTTP (port 80), and NTP (port 123)
8. Configure the local timezone to UTC
9. Install and configure Apache to serve a Python mod_wsgi application
10. Install and configure PostgreSQL:
	- Do not allow remote connections
	- Create a new user named catalog that has limited permissions to your catalog application database
11. Install git, clone and setup your Catalog App project (from your GitHub repository from earlier in the Nanodegree program) so that it functions correctly when visiting your server’s IP address in a browser. Remember to set this up appropriately so that your .git directory is not publicly accessible via a browser!

### id_rsa key

  ```
   -----BEGIN RSA PRIVATE KEY-----
MIIEpAIBAAKCAQEA1XoLtowoRNZzvKNeWfSvR1fq7r4/Cpv4uYxV4auZoQKPlpy+
cRGOf+9hXpdhx1DR8pg9Bh2zTIeTPOJeay/VVJn2mBjoHHpTlL8AJ9GKOkr3tQi9
LRwl3ARsTbT3oFxp9Kyx9fiZLW7teNXDJEBRSC69y+nd0gvnbagSzATRGkajEtvr
0C2nQijWo021ASJp9+VA1gti1jcwhZcwBIYu4mVLmGpXxboa+JF/Xv31s8c4S0+a
TK4vot0gbmCnBmTPtgtPGmPA/50txcl+FTMVtYiXR2slVzIXlidP2K8HthLhvO0P
rsDw5rcJCTqyBCN8g8xGuZrD0EA1V0x2hvdIFwIDAQABAoIBAC8yGU7Vc72sT9Af
qidnIi06sbTwmI1m6DlVXlNTFdbz8vzQUIY85G1CZht8imB/bLsejzc/77j2rEWk
ok0+OQLIOy1rLD3HiZz0ETu8Zrv2gQckFHbZp0EaNTuEy85HQCGY4ItJ18ukn5m8
YLUuBwpXUxy26pSajyK+KtGyKuyM0+7JZZj9vk39811r6Rlp4GlRKrcv1xLiEMTi
v5A33THBknvsHqG8oF34t4jR/cUkYD9dLnlq/7iIz+RQ+8FmoQaJ3UmA6mFdKQu2
4JMwCVugigWSnCsNj1RMfHt3Yd5TRTIYWLE9iQ9Lg5iwkt5PcgXoOwnnFb6aucXt
qPiSozkCgYEA8EJgRToogD3EkxljD/Exw74hcs01qJaceuTIgoc2Kf2ZgZ79fqVG
RcAsP/papGfwnWkz3y9dkxYTmpx9Yvoxm1hsrt0wzh8i0v/+zzCw0nXd5L04UEyI
td1/Nk74rDYzIIA/F/Q1QtAgBVmwEVWZKe+gu8UmcmQDay9vWBbs5WMCgYEA43Z5
NKb1UO6DcUs0uEwwt/qpAEKQ4tsRUyT1imZ6K0bOydMAxwBYF2VuZBlTQDVX96pf
wf6iRfJjx4/379CUVr7sJBxeAlT5mK9+zyd/TWoApMGhouv+afCQMrLmcgOyY/DE
Chx/BibDoST7Rcvz9QR3klaHy4krl2rtDsd4ur0CgYAcfvLmIxC8rRbMj51FPck2
Oy3CbP5pQXvLw6jYemr9Lfvv+Mh+JeIg0bst12a6yy0prlmdpgOGN38ZvmfMvnn1
v9YcI1XvjJfXyM8TCeZe/+XShHLSa1FnqJ629UTfQApuV2ekUq2igAbcO5f7Zlil
NautuaNmu9//7X9aRlXQmwKBgQCSuBusc7kvD/pm/Kyv6C1QrvWN/mH4gnflWqSr
Nji9a3n9QwZwVm97/+g51wAVHZN1ZEdKGdZQKe5kjh/OZ4sXfSVSkZ2uAWPSMfko
5ABATgzGOUPqlDDR4uMQYMc2ad4KiwXYw9LHg/+SFQmjVtAwjkYWdYw4JG2iyMzK
SK4+PQKBgQDaDPg8d0nwwh4s5vPWaQ2v+JbJCQkMKJI5Y+1BsXhLLYy6Fd14CVzS
z9GrkeGG3BwWHPg9kkI6i/+cu54T69bkjyAlwtdhrJeQmXFP0l7CzLzdv2IuPrJ/
phi3qsvrR2TNpBU8pT6AqBWVK3kFJr4eVo6ZandMi5Ymvy0mHpfo/Q==
-----END RSA PRIVATE KEY-----

  ```
### id_rsa.pub key

```
ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQDVegu2jChE1nO8o15Z9K9HV+ruvj8Km/i5jFXhq5mhAo+WnL5xEY5/72Fel2HHUNHymD0GHbNMh5M84l5rL9VUmfaYGOgcelOUvwAn0Yo6Sve1CL0tHCXcBGxNtPegXGn0rLH1+Jktbu141cMkQFFILr3L6d3SC+dtqBLMBNEaRqMS2+vQLadCKNajTbUBImn35UDWC2LWNzCFlzAEhi7iZUuYalfFuhr4kX9e/fWzxzhLT5pMri+i3SBuYKcGZM+2C08aY8D/nS3FyX4VMxW1iJdHayVXMheWJ0/Yrwe2EuG87Q+uwPDmtwkJOrIEI3yDzEa5msPQQDVXTHaG90gX sai narasimha@DESKTOP-F8RMTCQ
```
### Password

```
sunil
```

### Passphrase
```
just press enter key for Passphrase
```

### How to connect as grader:
  save private key provided in your local machine and run the following command
  ```
  ssh -i path/to/privatekey -p 2200 grader@13.232.118.69
    
  ```
### Configuring Linux Server

#### Updating all packages
```
sudo apt-get update
sudo apt-get upgrade
```

#### Creating grader User:
  ```
  sudo adduser grader 
  ```
  This will add you to new user
  ```
  sudo nano /etc/sudoers
  ```
  Below the Root user append the following line
  ```
  grader  ALL=(ALL:ALL) ALL
  ```
  This will grant sudo permission to grader
  #### Creating a ssh key pair for grader
   On your local machine in terminal/command prompt
   ```
   ssh-keygen
   ```
   This will generate public and private ssh keys which is saved to .ssh folder
   
   Then in your virtual machine change to newly created user
   ```
   su - grader
   ```
   Create a new directory .ssh and new file authorized_keys in that directory
   ```
   mkdir .ssh
   sudo nano .ssh/authorized_keys
   ```
   Copy the public key with .pub extension to authorized_keys and save the file
   ```
   chmod 700 .ssh
   chmod 644 .ssh/authorized_keys
   ```
   - 700 will give read write and execute permission to user.
   - 644 prevent other user from writting in to file.
   Then restart ssh server
   ```
   service ssh restart
   ```
   
   Now from your log in to grader with private key generated 
   ```
   ssh -i .ssh/id_rsa grader@ipaddress 
   ```
  #### Changing the ssh port to 2200
   ```
   sudo nano /etc/ssh/sshd_config
   ```
   Change port 22 to port 2200
    
   Restart the ssh server
   
   ```
   service ssh restart
   ```
   
   >Note: Before Logging using ssh add custom TCP port 2200 under lightsaail firewall in networking tab in lightsail instance console  
   
   Now Login using command like this
   ```
   ssh -i .ssh/id_rsa -p 2200 grader@ipaddress
   ```
   
  #### Disabling ssh login as root
  `sudo nano /etc/ssh/sshd_config`
  
  make change `PermitRootLogin no`
  
  #### Configurating  Ufw firewall
  ```
  sudo ufw allow 2200/tcp
  sudo ufw allow 80/tcp
  sudo ufw allow 123/udp
  sudo ufw enable
  ```
  This will allow all required ports and enables the ufw
  
  After that 
  ```
  sudo ufw status
  ```
  It will display all allowed ports
  
  #### Changing time Zone
  `sudo dpkg-reconfigure tzdata`
  
  select none from list and then select utc.
  
  #### Installing Apache2 
  In terminal 
  
  ```sudo apt-get install apache2```
  
  Now mod_wsgi
  
  ```sudo apt-get install python-setuptools libapache2-mod-wsgi```
  
  Enable mod_wsgi
  
  ```sudo a2enmod wsgi ```
  ##### Setting up your flask application to work with apache2
   Creating a flask app
   
   In /var/www directory create a new folder
   `sudo mkdir FlaskApp`
   
   Install git 
   
   `sudo apt-get install git`
   
   move to the FlaskApp `cd FlaskApp`
   
   In that direcory clone your github repository
   
   `sudo git clone https://github.com/username/catalog.git`
   
   Rename your repository to FlaskApp
   
   Then rename your project file to `__init__.py`
   
   >Error : While accesssing the client_secrets.json file 
   ```
   PROJECT_ROOT = os.path.realpath(os.path.dirname(__file__))
   json_url = os.path.join(PROJECT_ROOT, 'client_secrets.json')
   CLIENT_ID = json.load(open(json_url))['web']['client_id']
   ```
   Use json_url instead client_secrets.json in script
   
   Reffered from [stack overflow](https://stackoverflow.com/questions/44742566/wsgi-cant-find-file-in-same-directory-in-app)
   
  ##### Install and configuring postgresql for project
   Install Postgres `sudo apt-get install postgresql`
   
   login to postgres `sudo su - postgres`
   
   postgres shell `psql`
   
   create user `CREATE USER catalog WITH PASSWORD 'password';`
   
   permit user to createdb `ALTER USER catalog CREATEDB;`
   
   Create a db name  catalog with user catalog `CREATE DATABASE catalog WITH OWNER catalog;`
   
   connect to db `\c catalog`
   
   revoke all permission to public `REVOKE ALL ON SCHEMA public FROM public;`
   
   Give schema permission to user catalog `GRANT ALL ON SCHEMA public TO catalog;`
   
   exit from db and postgres `\q and exit`
   
   Change the database connection in both db_setup.py and `__init__.py` as `engine = create_engine('postgresql://catalog:password@localhost/catalog')`
   
   Now you are ready with your applicatiom
  #### Configure and Enable a New Virtual Host
   `sudo nano /etc/apache2/sites-available/FlaskApp.conf`
   
   In this add the following code
   ```
   <VirtualHost *:80>
		ServerName mywebsite.com
		ServerAdmin admin@mywebsite.com
		WSGIScriptAlias / /var/www/FlaskApp/flaskapp.wsgi
		<Directory /var/www/FlaskApp/FlaskApp/>
			Order allow,deny
			Allow from all
		</Directory>
		Alias /static /var/www/FlaskApp/FlaskApp/static
		<Directory /var/www/FlaskApp/FlaskApp/static/>
			Order allow,deny
			Allow from all
		</Directory>
		ErrorLog ${APACHE_LOG_DIR}/error.log
		LogLevel warn
		CustomLog ${APACHE_LOG_DIR}/access.log combined
   </VirtualHost>
   ```
   Enable the virtual host 
   `sudo a2ensite FlaskApp`
   
   Disabling the default apache2 page
   `sudo a2dissite 000-default.conf`
   
  #### Create the .wsgi File
    ```
    cd /var/www/FlaskApp
    sudo nano flaskapp.wsgi 
    ```
   Add the following code
   
   ```
   #!/usr/bin/python
    import sys
    import logging
    logging.basicConfig(stream=sys.stderr)
    sys.path.insert(0,"/var/www/FlaskApp/")

    from FlaskApp import app as application
    application.secret_key = 'Add your secret key'
   ```
   save and exit
   
   Deploying flask app with apache2 is referred from [Digital ocean](https://www.digitalocean.com/community/tutorials/how-to-deploy-a-flask-application-on-an-ubuntu-vps)
   
   #### Installing require modules
   You can either install all modules on your machine or create a virtual environment for the project and install the modules
   ` pip install flask sqlalchemy psycopg2 requests oauth2client`
   
   #### Setting up your Google Oauth2
   Login to your [developer console](https://console.developers.google.com) and select your project and edit OAuth details as following
   
   Javascript origin
   `http://ip.xip.io`
   
   redirect URI
   
   `http://ip.xip.io\login`
   
   `http://ip.xip.io\gconnect`
   
   `http://ip.xip.io\callback`
   
   [xip.io](xip.io) is a free DNS which will be the same as using IP address
   
   #### Final Step
   Restart your apache2 server
   
   `sudo service apache2 restart`
   
