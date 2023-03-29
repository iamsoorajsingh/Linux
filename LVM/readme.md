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

pvcreate /dev/sde
vgcreate suraj_vg /dev/sde
lvcreate -n suraj_lv -L 200m suraj_vg
mkdir -p /mnt/suraj
mkfs.xfs /dev/mapper/suraj_vg-suraj-lv
vi /etc/fstab/ --->allows you to specify how and what options need to be used for mounting a particular device or partition, so that it will be using that options every time you mount it
/dev/mapper/suraj_vg-suraj_lv   /mnt/suraj      xfs     defaults        0       0

xfs_growfs /dev/mapper/suraj_vg-suraj-lv
mount -a   -->it will mount the dir


