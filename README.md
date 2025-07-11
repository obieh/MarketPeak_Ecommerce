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

* Copy the public key and head over to your github account. Click your profile settings and click 'ssh and GPG keys' on the left. Then click 'New SSH key' towards the top right.

![](./img/Pasted%20image%20(11).png)

* Add a title, 'Key type' should be 'Authrntication Key' then paste the key generated and copied from the EC2 instance.

![](./img/Pasted%20image%20(12).png)

* Click 'Add SSH key' to add and save the key on yor github account.

![](./img/Pasted%20image%20(13).png)

* On the EC2 terminal, run `sudo yum install git -y` to install git if you have not already.

![](./img/Pasted%20image%20(14).png)

* Verify git installation, run `git --version`

![](./img/Pasted%20image%20(15).png)


* clone the MarketPeak_Ecommerce repo via ssh using the ssh url copied earlier.`git clone git@github.com:yourusername/MarketPeak_Ecommerce.git`

![](./img/Pasted%20image%20(16).png)


### Install Apache HTTP Server on the EC2 instance.

* Run `sudo yum update -y` to update the server.

* Run `sudo yum install httpd -y` to install apache webserver.

![](./img/Pasted%20image%20(17).png)

* Run `sudo systemctl start httpd` to start the server

* Run `sudo systemctl enable httpd` to httpd start on server boot.

![](./img/Pasted%20image%20(18).png)

### Configure httpd for MarketPeak_Ecommerce

#### Setup httpd to point to the directory cloned from your git repo earlier.
* Clear the default httpd web directory. Run `sudo rm -rf /var/www/html/*`

* Copy MarketPeak_Ecommerce directory to httpd web directory '/var/www/html'. Run `sudo cp -r ~/MarketPeak_Ecommerce/* /var/www/html/`

![](./img/Pasted%20image%20(19).png)

* Reload httpd, to apply the changes. Run `sudo systemctl reload httpd`

![](./img/Pasted%20image%20(20).png)

