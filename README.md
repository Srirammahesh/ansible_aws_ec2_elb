# ansible_aws_ec2_elb
![alt text](https://i.postimg.cc/SKPnQnbK/img-logo.png)

Three plays has been designed in our Ansible Playbook to reach our desired goal.
## Play 1:
- Create a vault (to store AWS Access Key and Secret Key).
- Install the localhost/host machine dependencies.
- Create the Security Groups for the EC2 instances.
- Provision EC2 instances on AWS.
- Add the public IP of the EC2 instances in a dynamic in-memory inventory of Ansible using the ec2 plugin in the hostgroup “webserver” 
## Play 2:
- This play works on the “webserver” hostgroup which I just created.
- This will configure the ec2 instances in AWS.
- In this example , I created a simple role of installing the “httpd” software(since I am using Amazon Linux 2 ami which is based on the Redhat family. For other linux flavours like the debian family, you can go forward and install “apache2” instead of httpd).
- Replace the default page with a simple php code to see the changes.(later can be used to see the Load balancer usage)
- Now, start the service httpd.
## Play 3:
- Load balancer is created.
- Add the created EC2 instances to the ELB , so that they can distribute the traffic among the servers.

## Let’s start building the code:
### Step-1: Configure the Ansible file:
![alt text](https://i.postimg.cc/8kvmdFgg/img1.png)
### Step-2: Create an Ansible vault file:
You should be provided with the AWS Access Key and Secret Key after creating the account. If you have lost it, you could create it by logging into your AWS account.Then go to your profile and click Your Profile →  My Security Credentials →  Access keys (access key ID and secret access key) → Create New Access Key → then download the file.

#### Ansible Vaults will store the keys as a secret, very securely and in an encrypted format.
![alt text](https://i.postimg.cc/MGtFSnKF/img2.png)
![alt text](https://i.postimg.cc/q7MdyVNW/img3.png)

### Step-3:PlayBook Creation:
Refer code from repository

