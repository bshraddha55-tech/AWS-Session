# Deploying a Node Js Application on AWS EC2

### Testing the project locally

1. Clone this project
```
git clone https://github.com/verma-kunal/AWS-Session.git
```
2. Setup the following environment variables - `(.env)` file
```
DOMAIN= ""
PORT=3000
STATIC_DIR="./client"

PUBLISHABLE_KEY=""
SECRET_KEY=""
```
3. Initialise and start the project
```
npm install
npm run start
```
*******************************************************************************************************************************************
Hosting App on EC2 instance starts here

### Set up an AWS EC2 instance

1. Create an IAM user & login to your AWS Console
    - Access Type - Password
    - Permissions - Admin
2. Create an EC2 instance
    - Select an OS image - Ubuntu
    - Create a new key pair & download `.pem` file
    - Instance type - t2.micro
3. Connecting to the instance using ssh
```
ssh -i instance.pem ubunutu@<IP_ADDRESS>
```

### Configuring Ubuntu on remote VM

1. Updating the outdated packages and dependencies
```
sudo apt update
```
3. Install Git - [Guide by DigitalOcean](https://www.digitalocean.com/community/tutorials/how-to-install-git-on-ubuntu-22-04) 
4. Configure Node.js and `npm` - [Guide by DigitalOcean](https://www.digitalocean.com/community/tutorials/how-to-install-node-js-on-ubuntu-22-04)

### Deploying the project on AWS

1. Clone this project in the remote VM
```
git clone https://github.com/verma-kunal/AWS-Session.git
```
2. Setup the following environment variables - `(.env)` file
```
DOMAIN= ""
PORT=3000
STATIC_DIR="./client"

PUBLISHABLE_KEY=""
SECRET_KEY=""
```
> For this project, we'll have to set up an [Elastic IP Address](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/elastic-ip-addresses-eip.html) for our EC2 & that would be our `DOMAIN`

git clone https://github.com/verma-kunal/AWS-Session.git  -- forked it to my account
```

****Install nodejs and npm and check the version preferrably to be latest-- important for hosting the app on EC2 instance
sudo apt update
sudo apt install nodejs
sudo apt install npm  -- only after this 'npm install' will work

*node -v
npm -v


3. Initialise and start the project
```
npm install
 Got Vulnerabilities here, due to this npm run gave error
npm run 
```
For trouble shooting done
npm audit -- gave the package details which was causing issue
npm audit fix - to fix the vulneranilities 
npm fund -- had to try this too for cehcking the package details which was causing issue
cat package.json -- to check the nodemon details
nodemon version -- didn't work

which worked ?

npm install nodemon@latest --save-dev  --- 

npm install

npm start --- generated the local host link

npm list nodemon -- informational (to list the nodemon version)

> NOTE - We will have to edit the **inbound rules** in the security group of our EC2, in order to allow traffic from our particular port

### Project is deployed on AWS 🎉
