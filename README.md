# demo-wordpress-site
Sample IAC implementation using CloudFormation  to deploy WordPress site on AWS

* To host the WordPress Site, I first deployed the AWS elastic cloud compute instance and then deployed the WordPress Application on Apache Web Server.

* Once elastic cloud compute instance is deployed then next deployed the Application LoadBalancer to handle/Balance the load and application request routing.

* WordPress uses PHP to store and retrieve data from MySQL databases thus next using cloud formation deployed AWS MySql RDS also allowed the security group of DB to allow inbound requestś from elastic cloud compute.

* Lastly, to access our WordPress Site, we need to have a user-friendly domain name. To create a domain name for our WordPress Site created a record set in Route53 by referring to the application load balancer DNS.

* Now to make our WordPress Site live, I used the link http://demo.aviralpandey.nl./ and once updated the wp-config.php file on EC2 instance, the WordPress Site is live.

![architecture diagram](https://github.com/aviral-tzu/demo-wordpress-site/blob/master/demo-diagram.jpg)
