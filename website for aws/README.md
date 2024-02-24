# Deployment Steps

## EC2 Instance Setup
1. Launch an EC2 Instance with Ubuntu 22.04 AMI.
2. Choose t2.micro as Instance Type.
3. Configure security group to allow SSH & HTTP Inbound Traffic from Source 0.0.0.0/0.
4. Launch the instance.

## Apache Configuration
1. Connect to the EC2 instance.
2. Update the machine and install Apache web server:

sudo apt update
sudo apt install apache2 -y

3. Access the Apache default page using the Public IP.

## Website Deployment
1. Clone the website repository:

git clone https://github.com/Raghavarora09/Multi-Tier-Website-using-EC2.git

2. Copy the website content to Apache's directory:

sudo cp -R website\ for\aws/* /var/www/html

3. Remove the default index.html page:

sudo rm /var/www/html/index.html


## RDS MySQL Database Setup
1. Create an RDS MySQL database with Free Tier settings.
2. Configure security group to allow necessary inbound traffic through port 3306.
3. Note down the RDS Endpoint and port.

## PHP Application Integration
1. Install PHP and MySQL packages:

sudo add-apt-repository -y ppa:ondrej/php
sudo apt install php5.6 mysql-client php5.6-mysqli

2. Connect to the RDS Instance and create a table to store user data.

## Integration with Website
1. Update database credentials in index.php file.
2. Test the website and verify data storage in the MySQL database.

## Autoscaling Setup
1. Create an AMI from the EC2 Instance.
2. Create a Launch Template from the AMI.
3. Create an Autoscaling Group using the Launch Template.
4. Configure desired capacity and availability zones.
5. Review and create Autoscaling Group.

## Accessing Autoscaled Instances
1. Check the newly created instances in the EC2 console.
2. Access any of the instances using its Public IP to verify the application.

