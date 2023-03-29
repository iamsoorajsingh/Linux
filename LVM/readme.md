Log in to your AWS Management Console and navigate to the EC2 dashboard.

Launch an EC2 instance or select an existing one.

Select the instance and click on the "Actions" button.

From the dropdown, select "Instance Settings" and then "Add/Modify EBS Volumes".

Click on the "Add New Volume" button.

In the "Add EBS Volume" dialog box, select the desired volume type and size.

Choose the availability zone and click "Add" to create the EBS volume.

Once the volume is created, attach it to the EC2 instance by selecting the instance and clicking on "Actions" > "Instance Settings" > "Attach/Replace IAM Role".

Select the newly created EBS volume and specify the device name (e.g. /dev/sdf).

Click on "Attach" to attach the volume to the EC2 instance.

Once the volume is attached, log in to the EC2 instance and format the volume to use it as a file system.
