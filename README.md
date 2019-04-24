# WordpressRahul
AWS cloud formation for highly available wordpress site 

Getting Started
These are instructions to set up a highly available wordpress site with a webserver and RDS database.
The Wordpress file in the repository is a cloud formation template to set up a wordpress site for both dev and prod.
The stack can run as a single instance as well as in multi AZ behind a load balancer. Security groups are set up and the resources are created in a specified VPC.

Prerequisites
AWS login

To get the Dev env running:
Login to AWS and go to the cloudformation service
Click Create stack , upload a template and next.
In the 'specify details' page, Give a name to the stack . For eg; Devwordpress
For Dev, we can give allocated storage, DBclass and Instance Type of low or medium capability.
The MultiAZDatabase can be set to False. 
The webserver capacity may be 1.

To get the Prod env running:

In the 'specify details' page, Give a name to the stack . For eg; Prodwordpress
We can give allocated storage, DBclass and Instance Type of high capacity.
The MultiAZDatabase should be set to True. 
The webserver capacity may be more than 1.

The subnets to be mentioned should be atleast two subnets in different availability zones.

Constraints

There should be an existing EC2 keypair to enable SSH access.
All the parameters like instance type, CIDR range should be valid.
The usernames and passwords should be alphanumeric
Maximum number of webserver instances which can be created is 5.
This Cloudformation script can not be used to deploy on ECS.

Test result:
The wordpress site created out of the testing is http://ac5-applica-fj0vxpy2uxh2-542650238.ap-southeast-2.elb.amazonaws.com/wordpress.
