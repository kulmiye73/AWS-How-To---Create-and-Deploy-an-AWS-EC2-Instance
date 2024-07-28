# AWS-How-To---Create-and-Deploy-an-AWS-EC2-Instance
AWS How To - Create and Deploy an AWS EC2 Instance



Creating and Deploying an AWS EC2 Instance – Manual Method

Note:  This is general outline of the steps to create and deploy an EC2 Instance on AWS.

AWS Instance Creation and Connection

Login into your AWS Console account.
On the Amazon Web Services page, select VPC.
Create a Virtual Private Cloud (VPC)

On the VPC Dashboard, select Your VPCs.
Click the Create VPC button.
In the Name tag box, enter “VPC-One”; In the CIDR block box, enter “172.16.0.0/16”
Click the Yes, Create button. Click the Close button.
Create Subnets

On the VPC Dashboard select Subnets
Click the Create Subnet button
In the Name tag box, enter “SB-One”
In the VPC drop-down item, select the “VPC-One” item
In the Availability Zone drop-down item, select “us-west-2b”
In the CIDR block box, enter “172.16.1.0/24; click the Yes Create button
You will be returned to the Create Subnet page. Your “First-Subnet” item is selected.
Click the Close button
Create Internet Gateway (IWG)

On the VPC Dashboard, select Internet Gateways.
Click the Create internet gateway button.
In the Name tag box, enter, “IG-One”; Click the Yes, Create button.
Click the Close button.
Locate and click the Actions button, select Attach to VPC.
In the VPC drop-down item, select the “VPC-One” item. Click the Yes, Attach to VPC  
Create Route Tables

On the VPC Dashboard, select Route Tables
Locate the click the Create Route Table button
In the Name tag box, enter “RT-One”.
In the VPC drop-down item, select the “VPC-One” item.
Click the Yes, Create button. Click the Close button.
 

Modify Route Tables

Select the radio-button for the “RT-One” route table you created above.
Locate and select the Routes tab.
Click the Edit routes button; click the Add route button.
In the Destination column box, enter “0.0.0.0/0”; In the Target column –item; Select t Internet Gateway option; Select the “IG-One” item. Click the Save routes button.
Click the Close button.
You will be returned to the Create Route Table page. In the Name Column, Select,  “RT-One” and select the check-mark object.
Associate Subnets

On the Create Route Table page, locate and select the Subnet Associations tab.
Click the Edit subnet associations button.
Under the Associate column, place a select and place a check-mark in the check-box that matches the “SB-One” item.
Click the Save button.
 

Create Security Groups

At the top of the AWS console page, click on Services, select EC2.
On the EC2 Dashboard, select Security Groups.
Locate and select the Create Security Group button.
In the Security group name box, enter “SG-One”.
In the Description box, enter “SG One”.
In the VPC drop-down item, select the “VPC-One” item.
Click the Yes, Create button; Click the Close button.
Add Rules to Security Group

Locate the select the radio-button for the “SG-One” security group.
Select the Inbound Rules tab.
Click the Edit button. Click Add Rules button.
In the Type column, change the Custom TCP Rule item to ALL Traffic.
In the Source column, enter “0.0.0.0/0” .
Click the Add Rule button. Select RDP from the drop-down item list.
In the Source Column, select “My IP” from the drop-down item list. Note your IP Address.
Click the Save button
 

 

Create an Instance

Select the EC2 Service
Click Launch Instance button. Select the Microsoft Windows Server 2012 R2 Base.
Review the Instance types page.
Click, Next, Configure Instance Details button.
In the Network box, select “VPC-One”.
In the Subnet box, select “SN-One”.
In the Auto-assign Public IP box, select “Enable”
Click the Next: Add Storage button.
Click the Next: Add Tags button
Click the Add tag button; Enter “Name” in the Key box; Enter “EC2-Two” in Value box
Click Next: Configure Security Group
Choose Select an existing Security group; Select the Security Group, “SG-Two”.
Click the Review and Launch button. Click the Launch button.
Use or create a key pair

In the drop-down, select and choose Create a new key pair.
Enter “First-KP” in the Key pair name box
Click the Download Key pair button
(NOTE: a copy of the key pair file will be downloaded to your computer.)
Click the Launch Instances button.
Click the View Instances button.
Wait for the Instance Status to turn Green and Status Checks to show “2/2 Checks”.
 

Return to EC2 services  - Connect to Your Instance

Select Instances
Note the Instance status – it should be “running” and have “2/2 checks” checked green.
NOTE: It can take 4 minutes or so for the Instance to become available.
Select the EC2-One Instance radio button. Below in the Description tab, note the Public DNS and IPv4 Public IP.   You can use the Public DNS URL in your browser in future sessions.
Click the Connect button. Click the Get Password button.  Click the Choose File button and locate the Key pair you created and downloaded earlier.
Click the Decrypt password button. Note, copy and paste the decrypted password.
Click the Close button.
 

 On the EC2w Dashboard, select the EC2 instance radio button.  Click the Connect button
Click the Download Remote Desktop file. Note where the file downloads to on your computer.  Open the file.  You will see a prompt on-screen, click the Connect button.
enter the user name (if not already entered) “administrator”. On the EC2 Instance dashboard, click the Get Password button.  Select Choose file and browse to the downloaded KP-Pair-A.pem file you made earlier. Click Decrypt password.  Note the decrypted password on the screen.  Copy and paste the password into the RDP prompt for the administrator user.
You should be logged into the EC2 Instance.[AWS How To - Create and Deploy an A.txt](https://github.com/user-attachments/files/16402627/AWS.How.To.-.Create.and.Deploy.an.A.txt)
