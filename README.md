# Linux-Server-Configuration

## About
  This project is submitted under Udacity Full Stack web Development Nanodegree Final Project

## Server Details
Server Static IP Address 13.126.215.145

Hosted site Url [http://13.126.215.145.xip.io]

## Grader Password

graders

## Grader Key
Download Key from above or

-----BEGIN RSA PRIVATE KEY-----
MIIEowIBAAKCAQEA7U8H7BQ3mqe+F2crD0/ZKYVsniXaK4up1SpWmJnGNm91Hbgz
7X0YFb/0LQRPURL+uPgOgzoywApVpCWXcxU4/lYziFnfsIg3Psr4+kYQ5vAV3Y0G
Gh9vl3RSQ+cgjR+iKmAwFNWqA9m4z/7YI6HvCJP/1MhGM73tMFxVS5++pMFlf8df
25mtfUyuPrwnsk8y7/SLH8NX6loS+zVmqRGnxKCBm3tv2sN8efQBbp8pcYS0ZlmN
WhbwHY9Lq/190GsK9Q9dxQtnZu2lyT1/zTFS2p3avd13bBOXH+NSP+kS6tbGZFMG
07uC6hsBf076xm5yeXhA4V/CH5Df+JC+OhX/xQIDAQABAoIBAQCQxymPJxpxWStI
/eEwW0ei5ErLBU7gSDnZ2hWwzgg2h7NM6WeM2UfLZSukF0AIt2z+DiBUgTobHXL4
TRLj3CvER3TzF9m3yrLhtVVG415GdmzwmKwDXfBn10ilMqoSTx1RexN6coxiAv+U
rebRfmbltd1bxL/Hq3S8j2heVdwqiMID6OMvztGjHTiFdUPTEE+GCWK3Zc/AO52c
Ipj1cAwhEI338//UiaU/hRP1qZ2xEgss2//p8yD/lLxyi44eckxY6FyDUqEP2xu+
bGNK9al8ZrKCv0bQLwO9qV6FeKCMnNhicEpZmrB6HGqMKfhg8bcgjKzkwmj5lvbG
58Vum0JhAoGBAPt2HZvFzKPidY9LmvOIYZp9T56U5VoE5j/3jlGX1dT9PfCwJZMl
24EBai37NQi8gOrIkcDyCDeHq1I8sIMqh5ScPOhZxOPYkzwnbIynO0PofoAsLlgM
jWK/vDOy4vPe5+IHODS0aqM2vA9Hdsu90TWtdZ/kR3pOV6fEtbkMW9Q5AoGBAPGX
hcACMh1LLBMUxV4jToxTQ9w+FRRwo4t1hG/C+sZEaBXEHnKuOZ/xYZncKnGr58lx
rw2rc8gr7VxNxQae/xxN3nEeUfqMKzOW+Bqwc8rLeXdb+RbwFF8AJlMAw9POhAfY
g00/UQOgq1HsHBmuXgQ9b4yS8TM0+M5KIi2LnL/tAoGAB+1XTZvUsa3n6taFUfwQ
p6AfrG4hNM9GuumA8Q2KTiaVl0rWRGdDHjP/NufeaiIXJk+gWKbIn4eFXRhQsDHd
CFBMkz6ROGWRbqoHf/+dnKxtoHjEFT6ADobg1fhjszBpuvRjTzYIzpBhKVIlapLX
T4viU2IM5swlc0J+QBElq/ECgYAHw3C+3NMzccj2zAITplrN05coqq4OvBflUV9y
H/fjCyu1F1pLISIk66LRSOvsPzPxmz+e1tWfpxm3j6A3OEDGbhIp3GmR/ZMd00oh
wW3XJHbAySnV/N0KuHyCylGAqvA/OEvv3YsC7NTUixvUD3Bh/n9pKwepN5iPOH6k
rAnbeQKBgGW3UmkZxcSHy8d67LEiu3mDFySJUO16Qfb+kCNo90t3oh9H/wU9J++q
BHcce5S88LxirMG8d0Thzjdqrel/PqQkEwcS2UMlvVIDdhnWk/UlGQUiuYjL2EzG
/F1oJCCSGHwXvopOyvihj7hyuEIUCrFh/flLiLQ8HGPWe31IikLI
-----END RSA PRIVATE KEY-----

## How to connect as grader:
  save private key provided in your local machine and run the following command
  ```
  ssh -i path/to/privatekey -p 2200 grader@13.126.215.145
    
  ```
## Configuring Linux Server

### Updating all packages
```
sudo apt-get update
sudo apt-get upgrade
```

### Creating grader User:
  ```
  sudo adduser grader
  ```
  This will add new user
  ```
  sudo nano /etc/sudoers
  ```
  Below the Root user append the following line
  ```
  grader  ALL=(ALL:ALL) ALL
  ```
  This will grant sudo permission to grader
  ### Creating a ssh key pair for grader
   On your local machine in terminal/command prompt
   ```
   ssh-keygen
   ```
   This will generate public and private ssh keys which is saved to .ssh folder
   
   Then in your virtual machine change to newly created user
   ```
   sudo su - grader
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
   sudo service ssh restart
   ```
   
   Now from your log in to grader with private key generated 
   ```
   Use this for connecting from local terminal
   ssh -i .ssh/id_rsa grader@ipaddress 
   ```
   ```
   OR
   Use this for connecting from local terminal
   ssh grader@ip_address 
   ```
  ### Changing the ssh port to 2200
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
   
  ### Disabling ssh login as root
  `sudo nano /etc/ssh/sshd_config`
  
  make change `PermitRootLogin no`
  
  ### Configurating  Uncomplicated Fire Wall
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
  
  ### Changing time Zone
  `sudo dpkg-reconfigure tzdata`
  
  select none from list and then select utc.
  
  ### Installing Apache2 
  In terminal 
  
  ```sudo apt-get install apache2```
  
  Now mod_wsgi
  
  ```sudo apt-get install python-setuptools libapache2-mod-wsgi```
  
  Enable mod_wsgi
  
  ```sudo a2enmod wsgi ```
  #### Setting up your flask application to work with apache2
   Creating a flask app
   
   In /var/www directory create a new folder
   `sudo mkdir FlaskApp`
   
   Install git 
   
   `sudo apt-get install git`
   
   move to the FlaskApp `cd FlaskApp`
   
   In that direcory clone your github repository
   
   `sudo git clone https://github.com/username/repo_name.git`
   
   Rename your repository to FlaskApp
   
   Then rename your project file to `__init__.py`
   
   >Error : While accesssing the client_secrets.json file 
   ```
   PROJECT_ROOT = os.path.realpath(os.path.dirname(__file__))
   json_url = os.path.join(PROJECT_ROOT, 'client_secrets.json')
   CLIENT_ID = json.load(open(json_url))['web']['client_id']
   ```
   Use json_url instead client_secrets.json in script
   
  #### Install and configuring postgresql for project
   Install Postgres `sudo apt-get install postgresql`
   
   login to postgres `sudo su - postgres`
   
   postgres shell `psql`
   
   create user `CREATE USER catalog WITH PASSWORD 'password';`
   
   permit user to createdb `ALTER USER catalog CREATEDB;`
   
   Create a db name  catalog with user catalog `CREATE DATABASE catalog WITH OWNER catalog;`
   
   connect to db `\c catalog`
   
   revoke all permission to public `REVOKE ALL ON SCHEMA public FROM public;`
   
   Give schema permission to user catalog `GRANT ALL ON SCHEMA public TO catalog;`
   
   exit from db  `\q`
   exit from postgres `exit`
   
   Change the database connection in both db_setup.py and __init__.py as `engine =       create_engine('postgresql://catalog:password@localhost/catalog')`

   #### Create a Virtuval Flask env for our app to be isolated from server environment for better stability(Extra Credit/Optional)

   In this step, we will create a virtual environment for our flask application.

    We will use pip to install virtualenv and Flask. If pip is not installed, install it on Ubuntu through apt-get.

    sudo apt-get install python-pip 
    If virtualenv is not installed, use pip to install it using following command:

    sudo pip install virtualenv 
    Give the following command (where venv is the name you would like to give your temporary environment):

    sudo virtualenv venv
    Now, install Flask in that environment by activating the virtual environment with the following command:

    source venv/bin/activate 
    Give this command to install Flask inside:

    sudo pip install Flask 
    Next, run the following command to test if the installation is successful and the app is running:

    sudo python __init__.py 
    It should display “Running on http://localhost:5000/” or "Running on http://127.0.0.1:5000/". If you see this message, you have successfully configured the app.

    To deactivate the environment, give the following command:

    deactivate
   
   Now you are ready with your applicatiom
  ### Configure and Enable a New Virtual Host
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
   
  ### Create the .wsgi File
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
  
   ### Installing require modules
   You can either install all modules on your machine or create a virtual environment for the project and install the modules
   To Create virtual environment: sudo virtualenv venv
   To activate virtual environment: source venv/bin/activate
   ` pip install flask sqlalchemy psycopg2 requests oauth2client`

   To deactivate virtual environment: deactivate
   
   ### Setting up your Google Oauth2
   Login to your [developer console](https://console.developers.google.com) and select your project and edit OAuth details as following
   
   Javascript origin
   `http://static_ip_address.xip.io`
   
   redirect URI
   
   `http://static_ip_address.xip.io\callback`
   
   `http://static_ip_address.xip.io\gconnect`
   
   `http://static_ip_address.xip.io\login`
   
   [xip.io](xip.io) is a free DNS which will be the same as using IP address
   
   ### Final Step
   Restart your apache2 server
   
   `sudo service apache2 restart`
   
   ### References used
        https://www.digitalocean.com
        some git hubs to get an idea 
"# Linux-Configuration" 
