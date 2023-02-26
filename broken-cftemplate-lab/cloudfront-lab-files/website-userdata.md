#!/bin/bash
yum update -y
yum install -y httpd
systemctl start httpd
systemctl enable httpd
cd /var/www/html
aws s3 cp s3://dct-cf-website/index.html ./
aws s3 cp s3://dct-cf-website/website.css ./
cp index.html index.txt
rm -rf index.html
EC2AZ=$(curl -s http://169.254.169.254/latest/meta-data/placement/availability-zone) 
sed "s/AZID/$EC2AZ/" /var/www/html/index.txt > /var/www/html/index.html
