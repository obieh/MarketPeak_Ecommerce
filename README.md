# This project demonstration deployment of E-commerce website on AWS webserver.

## Initialize Git Repository
* Create a directory for the project, runm `mkdir MarketPeak_Ecommerce`
* Change to the direcotory `cd MarketPeak_Ecommerce`
* Initialse git `git init`

![](./img/Pasted%20image.png)

## Obtain and Prepare the E-Commerce Website Template.
* You can download a free E-commerce website [here](https://www.tooplate.com/view/2130-waso-strategy)

* Customize (make changes if you desire) the template.

## Stage and Commit to the template to Git

* Run `git add .` to add all files
* Run `git config --global user.name "your git username"`
* Run `git config --global user.email "email registered on github"`
* Run `git commit -m"Initial commit with basic e-commerce site structure"`

![](./img/Pasted%20image%20(2).png)

## Push to Remote git Repo
* Head over to your github account and create a remote repo 'MarketPeak_Ecommerce'. Make it an empty repo.

![](./img/Pasted%20image%20(3).png)

* Link your local repo to github. In your local terminal add remote repository url. Be sure to add your git details.

![](./img/Pasted%20image%20(4).png) 

* Push to remote github

![](./img/Pasted%20image%20(5).png)

## AWS Deployment
* Head over to your aws account and create an ec2 instance

![](./img/Pasted%20image%20(6).png)

* Connect to the EC2 instance using ssh.

![](./img/Pasted%20image%20(8).png)

### Clone the repo on the EC2 Instance.

* Head over to your github account, click the repo and copy url to clone via ssh

![](./img/Pasted%20image%20(9).png)

* On the EC2 terminal run `ssh-keygen` to generate SSH keypair 

![](./img/Pasted%20image%20(10).png)

* Run `cat /home/ec2-user/.ssh/id_rsa.pub` to view the public key.

![](./img/Pasted%20image%20(38).png)

^ Copy the public key and head over to your github account.