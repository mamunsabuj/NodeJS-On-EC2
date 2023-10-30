# Node Hello World

Simple node.js app that servers "Welcome to Node JS"

Great for testing simple deployments on Cloud

## Step 1: Install NodeJS and NPM using nvm

Install node version manager (nvm) by typing the following at the command line.

```bash
sudo su -
curl -o- https://raw.githubusercontent.com/creationix/nvm/v0.35.3/install.sh | bash
```

Activate nvm by typing the following at the command line.

```bash
. ~/.nvm/nvm.sh
```

Use nvm to install the latest version of Node.js by typing the following at the command line.

```bash
nvm install node
```

If you want to install a specific node js version. Run command one by one and check.

```bash
nvm list
nvm ls-remote
nvm install 20.9.0
nvm use 20.9.0
nvm alias default 20.9.0
node -v
npm install -g npm
npm -v
```

20.9.0 is the latest Node js stable version. You can install other node js verion.

Test that node and npm are installed and running correctly by typing the following at the terminal:

```bash
node -v
npm -v
```

## Step 2: Install Git and clone repository from GitHub

To install git, run below commands in the terminal window:

```bash
sudo apt-get update -y
sudo apt-get install git -y
```

Just to verify if system has git installed or not, please run below command in terminal:

```bash
git — version
```

This command will print the git version in the terminal.

Run below command to clone the code repository from Github:

```bash
git clone https://github.com/mamunsabuj/NodeJS-On-EC2
```

Get inside the directory and Install Packages

```bash
cd nodejs-on-ec2
npm install
```

Start the application
To start the application, run the below command in the terminal:

```bash
npm start
```

## Step 3: Deploy Node JS project using PM2

Access in your EC2 Instance/ server
Git clone or upload your project in your server
Goto your project directory and install npm packages

```bash
npm install
```

Install PM2 package globally

```bash
sudo npm install pm2 -g
```

To Install latest pm2 package

```bash
sudo npm install@latest pm2 -g
```

Now start the pm2 for the project index page

```bash
sudo pm2 start index.js
```

starting page will be index.js or app.js. Set as your project requirement.

Application will be started. You will see a list of application with ID
Or run the following command for show the list

```bash
sudo pm2 ls
```

Check your application in browser, is it working or not
To stop or restart application

```bash
sudo pm2 ls
```

To stop or restart application

```bash
sudo pm2 stop 0
sudo pm2 restart 0
```

0 is the ID for the running application.

Check application logs

```bash
sudo pm2 logs 0
```

To start an application in Cluster mode

```bash
sudo pm2 start app.js -i max
```

## Refferences

1. https://www.youtube.com/watch?v=T-Pum2TraX4&t=17s
2. https://www.youtube.com/watch?v=-Iw0aQtERmE
3. https://www.youtube.com/watch?v=S45jZCvd2M8

The Best Way to Install Node.js
https://yoember.com/nodejs/the-best-way-to-install-node-js-with-yarn/

# Install MongoDB in EC2

login as root user

```
sudo su - root
```

For MongoDB 3.0, create below file using vi or any other editor

```bash
sudo vi /etc/yum.repos.d/mongodb-org-4.0.repo
```

Copy/paste the following to repo file

```bash
[mongodb-org-4.0]
name=MongoDB Repository
baseurl=https://repo.mongodb.org/yum/amazon/2013.03/mongodb-org/4.0/x86_64/
gpgcheck=1
enabled=1
gpgkey=https://www.mongodb.org/static/pgp/server-4.0.asc
```

Install MongoDB packages

```
sudo yum -y install mongodb-org
```

Check you have MongoDB installed properly

```
which mongo  # should print /usr/bin/mongo
```

Start MongoDB server

```
sudo service mongod start
```

Check MongoDB status

```
sudo service mongod status
```

#### MongoDB Configuration

Update MongoDB config

```
sudo vi /etc/mongod.conf
```

Find the network interface and update the port and bindIp by 27017 port and 0.0.0.0 .
after configuration setup restart MongoDB

```
sudo service mongod restart
```

#### Create MongoDB User

Connect to MongoDB

```
mongo
```

Create a root user

```
use admin
db.createUser({ user: "admin", pwd: "password", roles: ["root"] })
```

MongoDB Setup process done.

Please don't forget to add 27017 port from 0.0.0.0/0 in instance's Inbound Rule.

Now can can connect to the mongoDB by using MongoDB Compass from your local pc. Download MongoDB Compass from https://www.mongodb.com/products/tools/compass

MongoDB connection string will be similar as

```
mongodb://Your-EC2-Hostname:27017
```

## MongoDB Referrence

https://medium.com/@calvin.hsieh/steps-to-install-mongodb-on-aws-ec2-instance-62db66981218
https://www.youtube.com/watch?v=Gz_7WMjv6sE&t=1s

### Deploy Vue.js + Vuex Front-end app

Follow these steps to setup the Vue.js application on the server.

Clone or upload the Vue + Vuex project into the your EC2

Install NPM packagers

```
sudo npm install
```

Update the app to use real backend API:

Open the index file of your vue js application in editor,
Delete or replace or comment any delopment code lines in that file

Configure the path to API:
Configure your application live node js API in .env file

Build the front end app with the command

```
sudo npm run build
```

The Vue.js app is now built and ready to be served from the project directory,


### Vue js referrences

https://jasonwatmore.com/post/2019/12/14/vuejs-nodejs-on-aws-how-to-deploy-a-mevn-stack-app-to-amazon-ec2
