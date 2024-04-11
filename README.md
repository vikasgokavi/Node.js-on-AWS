# Deploying a Node Js Application on AWS EC2

### Testing the project locally


In order to test this application we are deploying the server on locally installed Ubuntu VM. To lauch Ubuntu VM on local system install VM follow the below link.
https://www.vmware.com/content/vmware/vmware-published-sites/us/products/workstation-pro/workstation-pro-evaluation.


After installing the VMware workstation it's time to install Ubuntu ISO Image from the browser. Download the ISO image from the below link.
https://ubuntu.com/download. After this step start the VMware application and create VM by browsing the downloaded ISO from local window OS and set up required configuration like user, dish and etc.

Once done with deploying of Ubuntu VM on local VMware Station, login to the VM using user ID and Passwd that you created while deploying Ubuntu VM. Now you can see the Home Page.

``
Home Page of Ubuntu VMware Workstation
![image](https://github.com/vikasgokavi/Node.js-on-AWS-/assets/105034318/2c00af1f-8df8-4118-9898-8976e3535ced)

``
Now Click on Terminal Application from the application list.


![image](https://github.com/vikasgokavi/Node.js-on-AWS-/assets/105034318/5b812166-166e-498c-84ef-16b338c736d3)
``
1. In order to do all the task, we need to switch as root user using "sudo su -"
command. Once logging in as root user do patching using "sudo apt update" command.

   ![image](https://github.com/vikasgokavi/Node.js-on-AWS-/assets/105034318/8ad63633-a5ec-4101-87a9-c0fe8607c073)


2. After patching let us install git using command " apt install git". Do check the git version installed using "git --version" command.

   ![image](https://github.com/vikasgokavi/Node.js-on-AWS-/assets/105034318/a6f5ca78-aaff-4d0e-a37f-6c7e00777c0e)



3. Clone this project to locally installed VM using below command.
   
```
git clone https://github.com/vikasgokavi/Node.js-on-AWS-.git

```
   ![image](https://github.com/vikasgokavi/Node.js-on-AWS-/assets/105034318/b6385a25-f72a-4f5f-a6b1-ab01966d8fdb)


4. Now change the directory "Node.js-on-AWS-" using "cd" command.

   ![image](https://github.com/vikasgokavi/Node.js-on-AWS-/assets/105034318/d9b6aaf1-8b28-4ab5-b610-9c2eeac89eec)


5. Under this directory create a hidden file ".env". This file will not be visible with simple "ls" command. To view this file use "ls -a"command and now setup the environment variables inside ".env" file using vi editor.
```
DOMAIN= "http//:localhost:3000"
PORT=3000
STATIC_DIR="./client"

PUBLISHABLE_KEY="vikasgokavi"
SECRET_KEY="vishwanath"
```
6. Install npm packege on ubuntu.
apt npm install

  ![image](https://github.com/vikasgokavi/Node.js-on-AWS-/assets/105034318/105e0750-c13a-4db4-81ec-1ee370055f5c)


7. Initialise and start the project
  npm run start

 ![image](https://github.com/vikasgokavi/Node.js-on-AWS/assets/105034318/83e00e14-a2c6-4fc4-bcaa-9388c5e8d9b9)

8. After this step we can access the server at http//:localhost:3001 and copy this address and paste in the firefox browser which is available on Ubuntu VM as it is the local host.

 ![image](https://github.com/vikasgokavi/Node.js-on-AWS/assets/105034318/60761ee4-0e93-468e-8fca-fac77a3d12c7)


### Now we will deploy a server on AWS and follow the same steps to lauch this application.

1. Here we are launching a instance named Nodejs-app-server, with Amazon machine image "Ubuntu 22.04 LTS" and type of instance is t2-micro which consist of 1 VCPU and 1 GiB of Memory.

 ![image](https://github.com/vikasgokavi/Node.js-on-AWS/assets/105034318/5e2ae0a6-e49c-4bca-a47e-8a380f5f6c16)


2. Let us select Key Pair, we can use a key pair to securely connect to our instance. Ensure that you have access to the selected key pair before you launch the instance.

 ![image](https://github.com/vikasgokavi/Node.js-on-AWS/assets/105034318/8d295b01-9881-4c7f-98ce-a3719c701229)

3. Under network setting, Firewall > create a new security group and keeping default rules where Allow SSH traffic from helps us connect to our instance, keeping the staorage configuration default which is eligible under free tier 1X8GiB for root volume.    

![image](https://github.com/vikasgokavi/Node.js-on-AWS/assets/105034318/0b7a2b2a-340f-4b08-8002-27c31fb75896)

4. On clicking Launch instance our VM will take some time and will be ready to connect.

 ![image](https://github.com/vikasgokavi/Node.js-on-AWS/assets/105034318/ddce65ca-6793-4ae4-a8de-2eab2e56f874)

5. Next select the ckeckbox of the instance, go tho action and click on connect.

 ![image](https://github.com/vikasgokavi/Node.js-on-AWS/assets/105034318/3e2b8ad3-2254-46e0-9856-a6c39e30157f)

6. Here there are four option we have in order to connect to the server, let us connect the instance using SSH Client i.e. Putty, here we use a .ppk we downloaded during instance creation.

  <img width="959" alt="image" src="https://github.com/vikasgokavi/Node.js-on-AWS/assets/105034318/32bf74a6-6402-4aea-a955-fd06d964e430">

7. Now we are on putty agent,here we will first switch as root user using "sudo su -" command. Once switching as root user let us see is there any updates pending using command "sudo apt update". Then we will check either git is installed or not using git --vesrion command. Then we will install node.js using "sudo apt install nodejs" command.

 <img width="960" alt="image" src="https://github.com/vikasgokavi/Node.js-on-AWS/assets/105034318/3dce18dc-cde1-4f34-830e-eb5d59041ee5">

8. Moving ahead with installation of npm, package manager using "sudp apt install npm" command.

 ![image](https://github.com/vikasgokavi/Node.js-on-AWS/assets/105034318/8877010e-705d-40b1-93b6-58e3f2199356)

  Now we can see the latest version of node.js and npm.

 ![image](https://github.com/vikasgokavi/Node.js-on-AWS/assets/105034318/cba82cb6-7353-45f7-97e6-2ca56de6a0d0)

9. Let us clone the git repository to aws instance using command "git clone https://github.com/verma-kunal/AWS-Session.git"

 ![image](https://github.com/vikasgokavi/Node.js-on-AWS/assets/105034318/11266096-12b3-43df-a693-b668a4ebf338)

10. In this step we will change the directory to AWS-Session. Under this directory we have created a hidden file named ".env" in order to keep environmental variables.

  <img width="536" alt="image" src="https://github.com/vikasgokavi/Node.js-on-AWS/assets/105034318/afaf9e34-7b53-44c5-b08d-547e3be5b418">

11. Next step is to we will add the environmental variables .env file using vi editor.

  <img width="960" alt="image" src="https://github.com/vikasgokavi/Node.js-on-AWS/assets/105034318/2f51ae1e-35e8-434c-bef0-8b1cab04eb23">

  ![image](https://github.com/vikasgokavi/Node.js-on-AWS/assets/105034318/874c5670-bb9b-4362-9671-683483e8d0c5)

12. To run the application here we will install npm node modules here for the packages that need to runthe application.

  ![image](https://github.com/vikasgokavi/Node.js-on-AWS/assets/105034318/345aafbc-6209-46a9-8fca-386957163f8f)
    
13. Now we will run the command "npm run start"

  ![image](https://github.com/vikasgokavi/Node.js-on-AWS/assets/105034318/a65fca36-dad8-4fb6-9808-2ef9c4877b74)


The command npm run start is commonly used in Node.js projects to start the application. Here's why it's used:

Defined in package.json: In most Node.js projects, the package.json file includes scripts that define various tasks. One of these scripts is often named start, and it typically runs the command needed to start the application.

Consistency: Using npm run start ensures consistency across different development environments and for different developers working on the project. Since it's a standard script name, everyone knows that running npm run start will start the application.

Customizable: The start script can be customized to include any necessary startup commands or configurations specific to your project. For example, it might start a server, compile assets, or perform other initialization tasks.

npm Scripts: npm provides a way to run custom scripts defined in package.json using the npm run command. This allows developers to define and execute project-specific commands easily.

14. Now we will go to browser and paste the public IP and port number 54.164.38.62:3000.

 ![image](https://github.com/vikasgokavi/Node.js-on-AWS/assets/105034318/f1088515-b64f-4e9d-8eb9-aa42b01d8d62)


This site can’t be reached 54.164.38.62 refused to connect. The reason being it can't be reached as while launching ec2-instance under security group we have only enabled the SSH connection. To make site reachable we need to expose port number 3000 to the internet.

  <img width="959" alt="image" src="https://github.com/vikasgokavi/Node.js-on-AWS/assets/105034318/1ca47336-3eb5-455d-9e17-fd55d7b3e328">

Now under inbound rules we will add port number 3000 and we will save the rules.

  ![image](https://github.com/vikasgokavi/Node.js-on-AWS/assets/105034318/ff27ce26-0b89-4c4e-9862-3bd11aec75ce)


  ![image](https://github.com/vikasgokavi/Node.js-on-AWS/assets/105034318/a0fe51f4-6b11-4301-9631-3b993b78fc15)


Again go to the same browser page and refresh.


  ![image](https://github.com/vikasgokavi/Node.js-on-AWS/assets/105034318/be8d0e77-825f-4385-b1e5-da61cfbb61b7)


Now the application is running successfully.








  

    


      
     




  




   














