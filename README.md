# Deploying a Node Js Application on AWS EC2

### Testing the project locally

``
In order to check this application we are deploying the server on locally installed Ubuntu VM. To lauch Ubuntu VM on local system install VM follow the below link.
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

``
2. After patching let us install git using command " apt install git". Do check the git version installed using "git --version" command.

![image](https://github.com/vikasgokavi/Node.js-on-AWS-/assets/105034318/a6f5ca78-aaff-4d0e-a37f-6c7e00777c0e)



3. Clone this project to locally installed VM using below command.
```
git clone https://github.com/vikasgokavi/Node.js-on-AWS-.git
```
![image](https://github.com/vikasgokavi/Node.js-on-AWS-/assets/105034318/b6385a25-f72a-4f5f-a6b1-ab01966d8fdb)


4. Now change the directory "Node.js-on-AWS-" using "cd" command.

   ![image](https://github.com/vikasgokavi/Node.js-on-AWS-/assets/105034318/d9b6aaf1-8b28-4ab5-b610-9c2eeac89eec)
``

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

```
Initialise and start the project
npm run start

![image](https://github.com/vikasgokavi/Node.js-on-AWS/assets/105034318/83e00e14-a2c6-4fc4-bcaa-9388c5e8d9b9)

After this step we can access the server at http//:localhost:3001 and copy this address and paste in the firefox browser which is available on Ubuntu VM as it is the local host.

![image](https://github.com/vikasgokavi/Node.js-on-AWS/assets/105034318/60761ee4-0e93-468e-8fca-fac77a3d12c7)










