# Actions, Resources, and Condition Keys for AWS Shield<a name="list_awsshield"></a>

AWS Shield \(service prefix: `shield`\) provides the following service\-specific resources, actions, and condition context keys for use in IAM permission policies\.

References:
+ Learn how to [configure this service](http://docs.aws.amazon.com/shield/latest/developerguide/)\.
+ View a [list of the API operations available for this service](http://docs.aws.amazon.com/waf/latest/DDOSAPIReference/)\.
+ Learn how to protect this service and its resources by [using IAM](http://docs.aws.amazon.com/shield/latest/developerguide/waf-auth-and-access-control.html) permission policies\.

**Topics**
+ [Actions Defined by AWS Shield](#awsshield-actions-as-permissions)
+ [Resources Defined by Shield](#awsshield-resources-for-iam-policies)
+ [Condition Keys for AWS Shield](#awsshield-policy-keys)

## Actions Defined by AWS Shield<a name="awsshield-actions-as-permissions"></a>

You can specify the following actions in the `Action` element of an IAM policy statement\. By using policies, you define the permissions for anyone performing an operation in AWS\. When you use an action in a policy, you usually allow or deny access to the API operation or CLI command with the same name\. However, in some cases, a single action controls access to more than one operation\. Alternatively, some operations require several different actions\. For details about the columns in the following table, see [The Actions Table](reference_policies_actions-resources-contextkeys.md#actions_table)\.


****  

| Actions | Description | Access Level | Resource Types \(\*required\) | Condition Keys | Dependent Actions | 
| --- | --- | --- | --- | --- | --- | 
|   [ AssociateDRTLogBucket ](http://docs.aws.amazon.com/waf/latest/DDOSAPIReference/API_AssociateDRTLogBucket.html)  | Authorizes the DDoS Response team to access the specified Amazon S3 bucket containing your flow logs | Write |  |  |   s3:GetBucketPolicy   s3:PutBucketPolicy   | 
|   [ AssociateDRTRole ](http://docs.aws.amazon.com/waf/latest/DDOSAPIReference/API_AssociateDRTRole.html)  | Authorizes the DDoS Response team using the specified role, to access your AWS account to assist with DDoS attack mitigation during potential attacks | Write |  |  |   iam:GetRole   iam:ListAttachedRolePolicies   iam:PassRole   | 
|   [ CreateProtection ](http://docs.aws.amazon.com/waf/latest/DDOSAPIReference/API_CreateProtection.html)  | Activate DDoS protection service for a given resource ARN | Write |   [ protection\* ](#awsshield-protection)   |  |  | 
|   [ CreateSubscription ](http://docs.aws.amazon.com/waf/latest/DDOSAPIReference/API_CreateSubscription.html)  | Activate subscription | Write |  |  |  | 
|   [ DeleteProtection ](http://docs.aws.amazon.com/waf/latest/DDOSAPIReference/API_DeleteProtection.html)  | Delete an existing protection | Write |   [ protection\* ](#awsshield-protection)   |  |  | 
|   [ DeleteSubscription ](http://docs.aws.amazon.com/waf/latest/DDOSAPIReference/API_DeleteSubscription.html)  | Deactivate subscription | Write |  |  |  | 
|   [ DescribeAttack ](http://docs.aws.amazon.com/waf/latest/DDOSAPIReference/API_DescribeAttack.html)  | Get attack details | Read |   [ attack\* ](#awsshield-attack)   |  |  | 
|   [ DescribeDRTAccess ](http://docs.aws.amazon.com/waf/latest/DDOSAPIReference/API_DescribeDRTAccess.html)  | Returns the current role and list of Amazon S3 log buckets used by the DDoS Response team to access your AWS account while assisting with attack mitigation | Read |  |  |  | 
|   [ DescribeEmergencyContactSettings ](http://docs.aws.amazon.com/waf/latest/DDOSAPIReference/API_DescribeEmergencyContactSettings.html)  | Lists the email addresses that the DRT can use to contact you during a suspected attack | Read |  |  |  | 
|   [ DescribeProtection ](http://docs.aws.amazon.com/waf/latest/DDOSAPIReference/API_DescribeProtection.html)  | Get protection details | Read |   [ protection\* ](#awsshield-protection)   |  |  | 
|   [ DescribeSubscription ](http://docs.aws.amazon.com/waf/latest/DDOSAPIReference/API_DescribeSubscription.html)  | Get subscription details, such as start time | Read |  |  |  | 
|   [ DisassociateDRTLogBucket ](http://docs.aws.amazon.com/waf/latest/DDOSAPIReference/API_DisassociateDRTLogBucket.html)  | Removes the DDoS Response team's access to the specified Amazon S3 bucket containing your flow logs | Write |  |  |   s3:DeleteBucketPolicy   s3:GetBucketPolicy   s3:PutBucketPolicy   | 
|   [ DisassociateDRTRole ](http://docs.aws.amazon.com/waf/latest/DDOSAPIReference/API_DisassociateDRTRole.html)  | Removes the DDoS Response team's access to your AWS account | Write |  |  |  | 
|   [ GetSubscriptionState ](http://docs.aws.amazon.com/waf/latest/DDOSAPIReference/API_GetSubscriptionState.html)  | Get subscription state | Read |  |  |  | 
|   [ ListAttacks ](http://docs.aws.amazon.com/waf/latest/DDOSAPIReference/API_ListAttacks.html)  | List all existing attacks | List |  |  |  | 
|   [ ListProtections ](http://docs.aws.amazon.com/waf/latest/DDOSAPIReference/API_ListProtections.html)  | List all existing protections | List |  |  |  | 
|   [ UpdateEmergencyContactSettings ](http://docs.aws.amazon.com/waf/latest/DDOSAPIReference/API_UpdateEmergencyContactSettings.html)  | Updates the details of the list of email addresses that the DRT can use to contact you during a suspected attack | Write |  |  |  | 

## Resources Defined by Shield<a name="awsshield-resources-for-iam-policies"></a>

The following resource types are defined by this service and can be used in the `Resource` element of IAM permission policy statements\. Each action in the [Actions table](#awsshield-actions-as-permissions) identifies the resource types that can be specified with that action\. A resource type can also define which condition keys you can include in a policy\. These keys are displayed in the last column of the table\. For details about the columns in the following table, see [The Resource Types Table](reference_policies_actions-resources-contextkeys.md#resources_table)\.


****  

| Resource Types | ARN | Condition Keys | 
| --- | --- | --- | 
|   [ attack ](http://docs.aws.amazon.com/waf/latest/DDOSAPIReference/API_AttackDetail.html)  |  arn:$\{Partition\}:shield::$\{Account\}:attack/$\{Id\}  |  | 
|   [ protection ](http://docs.aws.amazon.com/waf/latest/DDOSAPIReference/API_Protection.html)  |  arn:$\{Partition\}:shield::$\{Account\}:protection/$\{Id\}  |  | 

## Condition Keys for AWS Shield<a name="awsshield-policy-keys"></a>

Shield has no service\-specific context keys that can be used in the `Condition` element of policy statements\. For the list of the global context keys that are available to all services, see [Available Keys for Conditions](reference_policies_condition-keys.html#AvailableKeys) in the *IAM Policy Reference*\.