# Using Instance Profiles<a name="id_roles_use_switch-role-ec2_instance-profiles"></a>

An instance profile is a container for an IAM role that you can use to pass role information to an EC2 instance when the instance starts\.

## Managing Instance Profiles \(Console\)<a name="instance-profiles-manage-console"></a>

If you use the AWS Management Console to create a role for Amazon EC2, the console automatically creates an instance profile and gives it the same name as the role\. When you then use the Amazon EC2 console to launch an instance with an IAM role, you can select a role to associate with the instance\. In the console, the list that's displayed is actually a list of instance profile names\. The console does not create an instance profile for a role that is not associated with Amazon EC2\.

## Managing Instance Profiles \(AWS CLI or AWS API\)<a name="instance-profiles-manage-cli-api"></a>

If you manage your roles from the AWS CLI or the AWS API, you create roles and instance profiles as separate actions\. Because roles and instance profiles can have different names, you must know the names of your instance profiles as well as the names of roles they contain\. That way you can choose the correct instance profile when you launch an EC2 instance\. 

**Note**  
An instance profile can contain only one IAM role, although a role can be included in multiple instance profiles\. This limit of one role per instance profile cannot be increased\. You can remove the existing role and then add a different role to an instance profile\. You must then wait for the change to appear across all of AWS because of [eventual consistency](https://en.wikipedia.org/wiki/Eventual_consistency)\. To force the change, you must [disassociate the instance profile](http://docs.aws.amazon.com/AWSEC2/latest/APIReference/API_DisassociateIamInstanceProfile.html) and then [associate the instance profile](http://docs.aws.amazon.com/AWSEC2/latest/APIReference/API_AssociateIamInstanceProfile.html), or you can stop your instance and then restart it\. 

### Managing Instance Profiles \(AWS CLI\)<a name="instance-profiles-manage-cli"></a>

You can use the following AWS CLI commands to work with instance profiles in an AWS account\. 
+ Create an instance profile: [http://docs.aws.amazon.com/cli/latest/reference/iam/create-instance-profile.html](http://docs.aws.amazon.com/cli/latest/reference/iam/create-instance-profile.html)
+ Add a role to an instance profile: [http://docs.aws.amazon.com/cli/latest/reference/iam/add-role-to-instance-profile.html](http://docs.aws.amazon.com/cli/latest/reference/iam/add-role-to-instance-profile.html) 
+ List instance profiles: [http://docs.aws.amazon.com/cli/latest/reference/iam/list-instance-profiles.html](http://docs.aws.amazon.com/cli/latest/reference/iam/list-instance-profiles.html), [http://docs.aws.amazon.com/cli/latest/reference/iam/list-instance-profiles-for-role.html](http://docs.aws.amazon.com/cli/latest/reference/iam/list-instance-profiles-for-role.html) 
+ Get information about an instance profile: [http://docs.aws.amazon.com/cli/latest/reference/iam/get-instance-profile.html](http://docs.aws.amazon.com/cli/latest/reference/iam/get-instance-profile.html) 
+ Remove a role from an instance profile: [http://docs.aws.amazon.com/cli/latest/reference/iam/remove-role-from-instance-profile.html](http://docs.aws.amazon.com/cli/latest/reference/iam/remove-role-from-instance-profile.html)
+ Delete an instance profile: [http://docs.aws.amazon.com/cli/latest/reference/iam/delete-instance-profile.html](http://docs.aws.amazon.com/cli/latest/reference/iam/delete-instance-profile.html) 

You can also attach a role to an already running EC2 instance by using the following commands\. For more information, see [IAM Roles for Amazon EC2](http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/iam-roles-for-amazon-ec2.html#attach-iam-role)\.
+ Attach an instance profile with a role to a stopped or running EC2 instance: [http://docs.aws.amazon.com/cli/latest/reference/ec2/associate-iam-instance-profile.html](http://docs.aws.amazon.com/cli/latest/reference/ec2/associate-iam-instance-profile.html) 
+ Get information about an instance profile attached to an EC2 instance: [http://docs.aws.amazon.com/cli/latest/reference/ec2/describe-iam-instance-profile-associations.html](http://docs.aws.amazon.com/cli/latest/reference/ec2/describe-iam-instance-profile-associations.html) 
+ Detach an instance profile with a role from a stopped or running EC2 instance: [http://docs.aws.amazon.com/cli/latest/reference/ec2/disassociate-iam-instance-profile.html](http://docs.aws.amazon.com/cli/latest/reference/ec2/disassociate-iam-instance-profile.html) 

### Managing Instance Profiles \(AWS API\)<a name="instance-profiles-manage-api"></a>

You can call the following AWS API operations to work with instance profiles in an AWS account\.
+ Create an instance profile: [http://docs.aws.amazon.com/IAM/latest/APIReference/API_CreateInstanceProfile.html](http://docs.aws.amazon.com/IAM/latest/APIReference/API_CreateInstanceProfile.html) 
+ Add a role to an instance profile: [http://docs.aws.amazon.com/IAM/latest/APIReference/API_AddRoleToInstanceProfile.html](http://docs.aws.amazon.com/IAM/latest/APIReference/API_AddRoleToInstanceProfile.html) 
+ List instance profiles: [http://docs.aws.amazon.com/IAM/latest/APIReference/API_ListInstanceProfiles.html](http://docs.aws.amazon.com/IAM/latest/APIReference/API_ListInstanceProfiles.html), [http://docs.aws.amazon.com/IAM/latest/APIReference/API_ListInstanceProfilesForRole.html](http://docs.aws.amazon.com/IAM/latest/APIReference/API_ListInstanceProfilesForRole.html) 
+ Get information about an instance profile: [http://docs.aws.amazon.com/IAM/latest/APIReference/API_GetInstanceProfile.html](http://docs.aws.amazon.com/IAM/latest/APIReference/API_GetInstanceProfile.html) 
+ Remove a role from an instance profile: [http://docs.aws.amazon.com/IAM/latest/APIReference/API_RemoveRoleFromInstanceProfile.html](http://docs.aws.amazon.com/IAM/latest/APIReference/API_RemoveRoleFromInstanceProfile.html) 
+ Delete an instance profile: [http://docs.aws.amazon.com/IAM/latest/APIReference/API_DeleteInstanceProfile.html](http://docs.aws.amazon.com/IAM/latest/APIReference/API_DeleteInstanceProfile.html) 

You can also attach a role to an already running EC2 instance by calling the following operations\. For more information, see [IAM Roles for Amazon EC2](http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/iam-roles-for-amazon-ec2.html#attach-iam-role)\.
+ Attach an instance profile with a role to a stopped or running EC2 instance: [http://docs.aws.amazon.com/AWSEC2/latest/APIReference/API_AssociateIamInstanceProfile.html](http://docs.aws.amazon.com/AWSEC2/latest/APIReference/API_AssociateIamInstanceProfile.html) 
+ Get information about an instance profile attached to an EC2 instance: [http://docs.aws.amazon.com/AWSEC2/latest/APIReference/API_DescribeIamInstanceProfileAssociations.html](http://docs.aws.amazon.com/AWSEC2/latest/APIReference/API_DescribeIamInstanceProfileAssociations.html) 
+ Detach an instance profile with a role from a stopped or running EC2 instance: [http://docs.aws.amazon.com/AWSEC2/latest/APIReference/API_DisassociateIamInstanceProfile.html](http://docs.aws.amazon.com/AWSEC2/latest/APIReference/API_DisassociateIamInstanceProfile.html) 