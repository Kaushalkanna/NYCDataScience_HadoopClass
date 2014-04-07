Hadoop Workshop I and II Tutorial:

Goal: 
— configure a Hadoop Cluster on Amazon EC2
— run two sample map reduce jobs on the cluster

Preparation:
1. apply for a AWS acct from http://aws.amazon.com/account/
	put name, email, click on "sign in";
	put full name, email, billing info, credit bard;
	pass the phone number authorization;
	select AWS support plan, use Basic (Free);
	You should see message "Thank you for updating your Amazon Web Services Account!”.

2. log in your acct
	choose "Launch the AWS Management Console";
	click on button "sign in to the AWS console";
	choose "I am a returning user and my password is";
	click "sign in using our secure server";
	On the top left corner, you should see "EC2 Dashboard".

3. create your key pair
   * you are authorizate yourself and communicate with Amazon cloud using public and private key pair.
	on your left panel of EC2 dashboard, click on 
	"network & security" category's "Key Pairs";
	click on button "create key pair";
	type your key pair name, for me, I put "vivian_zhang_supstat";
	you will see a download file window, choose a secure folder to save your .pem file which will be your private key. For me, I get the file called "vivian_zhang_supstat.pem";

4. create EC2 instances
   * Each instance is like a seperate machine.
 	on your left panel of EC2 dashboard,, click on 
	"instances" category's "instances";
	click on button "launch instance";
	choose the system, find the 9th options--"Ubuntu Server 12.04 LTS (HVM) - ami-5fa4a236  64 bit";
	click on "select";
	keep the default setting, choose "next:configure instance details";
	put "3" into "Number of instances";
	click on "review and launch";
	click on "launch";
	choose the key pair "vivian_zhang_supstat";
	check the acknowleage box;
	click on "launch instance",
	you should see "Your instances are now launching
";
    scroll down to the bottom, click on "view instances",
    click one each instance and rename them, such as "meetup1","meetup2","meetup3",
    wait till you see the status checks is changed from "initializing" to "2/2 checks passed".

5. configure security group
   *each group is like a firewall. The nodes of the same cluster belong to the same security group.
	click on "edit security groups",
	under default security group name "launch-wizard-1", cick on add rules;
	we are adding three rules:
	first, choose type="ALL ICM", Source=Anywhere, "save"
	second, choose type="Custom TCP", port range="9000-9001"
	third, choose type="Custom TCP", port range="50000-50100".

6. manage your instance
   select the instance, right click to choose "stop", you won't be able to use this instance and won't be charged;
   select the instance, right click to choose "start", you can use the instance and will be charged.
   Next time, if you restart the instance, your "public DNS" will be different, but your "private DNS" will not changed.

7.





