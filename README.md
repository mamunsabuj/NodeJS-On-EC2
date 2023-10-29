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

refferences

https://www.youtube.com/watch?v=T-Pum2TraX4&t=17s
https://www.youtube.com/watch?v=-Iw0aQtERmE
https://www.youtube.com/watch?v=S45jZCvd2M8

The Best Way to Install Node.js
https://yoember.com/nodejs/the-best-way-to-install-node-js-with-yarn/
