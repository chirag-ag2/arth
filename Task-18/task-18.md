## ARTH — Task 18 👨🏻‍💻

Task Description📄

🔅 Create an AWS EC2 instance

🔅 Configure the instance with Apache Webserver.

🔅 Download php application name “WordPress”.

🔅 As wordpress stores data at the backend in MySQL Database server. Therefore, you need to setup a MySQL server using AWS RDS service using Free Tier.

🔅 Provide the endpoint/connection string to the WordPress application to make it work.

## Introduction

WordPress is a popular PHP application. It is used over many sites available on the Internet. Our task is to deploy a WordPress website on Amazon EC2 Instance. WordPress needs MySQL Database so we will use Amazon RDS for it.

![](https://cdn-images-1.medium.com/max/2048/0*WroJOxiyUjcH5_8G.jpeg)

## Creating an EC2 instance

 1. Choose Machine Image (Prefer Amazon Linux 2 AMI (HVM)).

 2. Choose the desired instance type.

 3. Now, Configure a Security Group allowing SSH from Your IP and HTTP from anywhere.

 4. Get a key pair used for SSH and Launch.

We have successfully launched our EC2 instance. In the next module, we will configure our RDS database to work with our EC2 instance.

![](https://cdn-images-1.medium.com/max/3840/1*n9OmWf-BwnJFAfyANz_dwQ.png)

In the above image instance is launched named Task 18

## Creating RDS on AWS

![](https://cdn-images-1.medium.com/max/3840/1*Np16e-5vcBCj4s874qUD3w.png)

![](https://cdn-images-1.medium.com/max/3840/1*vdu2fMVriRWV8yUv4olUqw.png)

![](https://cdn-images-1.medium.com/max/3840/1*E3zdGFOKdutu-hmWHnvq4w.png)

![](https://cdn-images-1.medium.com/max/3840/1*gBdg9P8yEnz2MoniC_axPA.png)

![](https://cdn-images-1.medium.com/max/3840/1*T8mpPE7N9hrz6JtEuh280w.png)

## Configuring RDS Database

 1. Allow EC2 to access RDS by Changing Security Group of RDS.

 2. SSH your EC2 Instance using command “ssh -i <path/to/pem/file> ec2-user@<publicIpAddress>”.

 3. Install MySQL on your EC2 Instance by using the command “sudo yum install -y mysql”.

 4. Set Environment variable for MySQL host using export “MYSQL_HOST=<rds-endpoint>”.

 5. Connect to Database by “mysql — user=<user> — password=<password> <database-name>”.

 6. Finally, create a database user for your WordPress application and give it permission to access the database. Run these commands in the terminal, *“CREATE USER ‘<user-name>’ IDENTIFIED BY ‘<password>’;
GRANT ALL PRIVILEGES ON <database-name>.* TO <user-name>;
FLUSH PRIVILEGES;
Exit”.
*Note — This user is different from the user we gave during MySQL Engine Creation.

We learned how to configure network and password security for our RDS database. Our EC2 instance now has network access to our RDS database. Further, we created a database user to be used by your WordPress application.
Now, we will configure our EC2 instance to run the WordPress application.

![](https://cdn-images-1.medium.com/max/3840/1*YMk-Ci0of2Pna32XYHM9aQ.png)

## Setting up Wordpress

![](https://cdn-images-1.medium.com/max/3840/1*bslOgzXBC4UkbKm0fAoXTg.png)

![](https://cdn-images-1.medium.com/max/3840/1*uyEA8pazmHen_-6UjEI6NQ.png)

![](https://cdn-images-1.medium.com/max/3840/1*EQUJvlbvIbMkrINLEJxj5A.png)

![](https://cdn-images-1.medium.com/max/3840/1*RMPI_oAma8_9H5cCxBwZWQ.png)

![](https://cdn-images-1.medium.com/max/3840/1*Dbsx2D9WVksb5K-3eYPJMg.png)

## To check it is successfully connected

![](https://cdn-images-1.medium.com/max/3840/1*NCb4A_vDz2glhz6a2JMo2Q.png)

## Thankyou!!!!!!!!