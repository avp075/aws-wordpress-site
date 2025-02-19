# demo-wordpress-site
Sample IAC implementation using CloudFormation  to deploy WordPress site on AWS

* I have used the https://www.draw.io/ online resource for desiging the architecture diagrams. 

## Part 1 - Transformation and Migration to the Public Cloud

* I have used below mentioned AWS services for transforming and migrating to public cloud

  * EC2 as a compute resource and host the wordpress site.
  * MySQL RDS as a relational database for store/retrive data.
  * Application LoadBalancer to balance/route the incomming web traffic.
  * S3 Bucket to store the cloudformation templates and WordPress Site content.
  * Route53 to host a public domain name. 
    http://demo.aviralpandey.nl

* As part of infra provisioning at first I deployed the AWS elastic cloud compute instance and then deployed the WordPress Application on Apache Web Server using cloudFormation. (used the prebuilt image with application code instead to application deployment with each new server)

* Once elastic cloud compute instance is deployed then next deployed the Application LoadBalancer and autoscaling/launch configuration setup using cloudFormation to handle/balance the load and application request routing.

* WordPress uses PHP to store and retrieve data from MySQL databases thus next using cloudFormation deployed AWS MySql RDS also allowed the security group of DB to allow inbound requestś from elastic cloud compute.

* Lastly, to access our WordPress Site, we need to have a user-friendly domain name. To create a domain name for our WordPress Site created a record set in Route53 using cloudFormation by referring to the application load balancer DNS.

* Now to make our WordPress Site live, I used the link http://demo.aviralpandey.nl and once updated the wp-config.php file on EC2 instance, the WordPress Site is live.

![architecture diagram](https://github.com/aviral-tzu/demo-wordpress-site/blob/master/demo-diagram.jpg)


