<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>AWS IAM Setup</title>
   
</head>
<body>

<h1>AWS IAM Setup</h1>

<h2>Create Policy</h2>
<ol>
    <li>Navigate to the IAM console: <a href="https://console.aws.amazon.com/iam/" target="_blank">https://console.aws.amazon.com/iam/</a>.</li>
    <li>Choose "Policies" in the left navigation pane.</li>
    <li>Click "Create policy."</li>
    <li>Choose the "JSON" tab and paste the policy JSON.</li>
    <pre style="
            background-color: #f8f8f8;
            padding: 10px;
            border: 1px solid #ddd;">
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Action": [
        "ec2:*",
        "s3:*",
        "cloudwatch:*",
        "waf:*",
        "sns:*",
        "elasticloadbalancing:*",
        "autoscaling:*",
        "secretsmanager:CreateSecret",
        "secretsmanager:DescribeSecret",
        "secretsmanager:GetSecretValue",
        "secretsmanager:ListSecrets",
        "secretsmanager:UpdateSecret",
        "secretsmanager:TagResource",
        "secretsmanager:UntagResource"
      ],
      "Resource": "*"
    },
    {
      "Effect": "Allow",
      "Action": [
        "ec2:CreateVpc",
        "ec2:CreateSubnet",
        "ec2:CreateInternetGateway",
        "ec2:CreateRouteTable",
        "ec2:CreateSecurityGroup",
        "ec2:CreateRoute",
        "ec2:AssociateRouteTable",
        "ec2:AttachInternetGateway",
        "ec2:CreateNetworkAcl",
        "ec2:CreateNetworkAclEntry"
      ],
      "Resource": "*"
    }
  ]
}
    </pre>
    <li>Click "Review policy," provide a name: Technical_test, and description: deploy webApplication for the policy, and click "Create policy."</li>
</ol>

<h2>Create IAM User</h2>
<ul>
    <li>In the IAM console, click on "Users" in the left navigation pane.</li>
    <li>Click the "Add user" button.</li>
    <li>Enter "nasredinwesleti" as the username.</li>
    <li>Choose the type of access (select "Programmatic access" for AWS CLI, SDK).</li>
    <li>Click "Next: Permissions."</li>
    <li>Attach the "Technical_test" Policy (See Attached policy section).</li>
    <li>In the "Add user to group" step, you can skip this for now and click "Next: Tags" unless you want to add tags.</li>
    <li>Click "Next: Review."</li>
    <li>Review the settings, and if everything looks correct, click "Create user."</li>
    <li>After user creation, you'll see a success message. Click "Show" next to "Secret access key" and copy the secret key. Note: This is the only opportunity to view or download the secret key. If you lose it, you need to create a new access key.</li>
    <li>Click "Download .csv" to download a CSV file with the access key ID and secret access key.</li>
</ul>

<h2>Attach Policy to the User</h2>
<ol>
    <li>Now, go back to the IAM dashboard.</li>
    <li>Click on "Users," and find "nasredinwesleti" in the list of users.</li>
    <li>Click on the user to open the user details.</li>
    <li>In the "Permissions" tab, click on "Attach policies."</li>
    <li>In the "Filter policies" search box, type "Technical_test" to find the policy.</li>
    <li>Select the policy and click "Attach policy."</li>
</ol>

</body>
</html>

