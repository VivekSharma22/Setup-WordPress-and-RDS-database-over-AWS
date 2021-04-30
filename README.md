# Setup-WordPress-and-RDS-database-over-AWS
![image](https://user-images.githubusercontent.com/72133094/116683908-df057a00-a9cd-11eb-988b-785a8425ac85.png)

ARTH Task 18

Task Description📄

🔅 Create an AWS EC2 instance 

🔅 Configure the instance with Apache Webserver. 

🔅 Download php application name "WordPress".

🔅 As wordpress stores data at the backend in MySQL Database server. Therefore, you need to setup a MySQL server using AWS RDS service using Free Tier.

🔅 Provide the endpoint/connection string to the WordPress application to make it work. 

STEP 1: Creating AWS EC2 Instance
To launch ec2 instance we have to navigate to EC2 dashboard and click on launch instance . Then we have to give information about the instance like image , type of instance, security group, volumes etc. After that an instance will be launched, visible on dashboard.

![image](https://user-images.githubusercontent.com/72133094/116684278-681cb100-a9ce-11eb-9867-4796cf4572b9.png)

STEP 2: Configure the instance with Apache Webserver. 
We can directly login to the instance using web browser or use putty. After login use the following commands to configure apache webserver.

#yum install httpd -y => To install apache webserver
![image](https://user-images.githubusercontent.com/72133094/116684341-7c60ae00-a9ce-11eb-89d0-81c77ce71238.png)

#systemctl start httpd => To start apache webserver

#systemctl status httpd => To view status of httpd

![image](https://user-images.githubusercontent.com/72133094/116684399-8c788d80-a9ce-11eb-99ff-e9b5b2d239f4.png)

Create a webpage - index.html
![image](https://user-images.githubusercontent.com/72133094/116684580-bd58c280-a9ce-11eb-866c-19bc9ef17457.png)

View webpage from browser -

![image](https://user-images.githubusercontent.com/72133094/116684613-c8abee00-a9ce-11eb-92c0-ea3a5e82855e.png)

STEP 3: Download php application name "WordPress"
For installing WordPress we should have php installed in our system with version 7 or above.

#amazon-linux-extras install php7.3 => install php7.3
![image](https://user-images.githubusercontent.com/72133094/116684658-d3ff1980-a9ce-11eb-947a-6c0bce905132.png)

# php -v => To see php version installed
![image](https://user-images.githubusercontent.com/72133094/116684735-ef6a2480-a9ce-11eb-96f0-bbb5f1e6f3ed.png)

Now to install WordPress on our instance

#wget https://wordpress.org/latest.tar.gz => download the WordPress software
![image](https://user-images.githubusercontent.com/72133094/116684777-014bc780-a9cf-11eb-8014-9e461375aa79.png)

#tar -xzf latest.tar.gz => unzip installation file
![image](https://user-images.githubusercontent.com/72133094/116684813-10cb1080-a9cf-11eb-87f2-9c96899e87ad.png)

Now restart the httpd service so that server can pick up the changes

#systemctl restart httpd

Now we can see the welcome page WordPress when we visit to this url http://65.1.3134.132/wordpress then we shall be redirected to http://65.1.134.132/wordpress/wp-admin/setup-config.php
![image](https://user-images.githubusercontent.com/72133094/116684939-3a843780-a9cf-11eb-8c78-8d8306b4ef0a.png)
STEP 4: setup a MySQL server using AWS RDS service using Free Tier
To setup a MySQL server navigate to AWS RDS service and click on create database option then fill all the required fields like user, password, name of database, choose and free tier in templates .

When database is created you can see details of the database

![image](https://user-images.githubusercontent.com/72133094/116684852-204a5980-a9cf-11eb-8e22-e3a2278b2a71.png)
![image](https://user-images.githubusercontent.com/72133094/116684953-407a1880-a9cf-11eb-992e-ca06b436b172.png)

STEP 5: Provide the endpoint/connection string to the WordPress application to make it work. 
In the image above we can see the endpoint URL. We have to put this URL ,user name, password and our database name in the page we obtain after step 3.

After that we can see a page like given below
![image](https://user-images.githubusercontent.com/72133094/116685008-54be1580-a9cf-11eb-9b2a-f016491dfa2a.png)

Copy the content from above page , create a file "wp-config.php" in the /var/www/html/wordpress folder then copy the content to that file. At last click on Begin Installation to start installing WordPress . When the process of installation ends you will see the famous 5 minute WordPress installation process

![image](https://user-images.githubusercontent.com/72133094/116685036-60a9d780-a9cf-11eb-8012-ee5e30af0b65.png)

Fill in the details and proceed. You Will see a success page like this one-

![image](https://user-images.githubusercontent.com/72133094/116685091-6f908a00-a9cf-11eb-8425-78cbc1be0cbd.png)

Finally WordPress is installed you can login with the given email and password and you can see the dashboard of dashboard of WordPress.

![image](https://user-images.githubusercontent.com/72133094/116685164-8b942b80-a9cf-11eb-97e1-456bad57ec53.png)

THANK YOU FOR READING..............



