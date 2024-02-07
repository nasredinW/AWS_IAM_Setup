<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>AWS IAM Setup</title>
    <style>
        body {
            font-family: 'Arial', sans-serif;
            line-height: 1.6;
            margin: 20px;
        }

        h1, h2 {
            color: #333;
        }

        ol, ul {
            margin-top: 0;
        }

        pre {
            background-color: #f8f8f8;
            padding: 10px;
            border: 1px solid #ddd;
        }

        a {
            color: #007bff;
            text-decoration: none;
        }
    </style>
</head>
<body>

<h1>AWS IAM Setup</h1>

<h2>Create Policy</h2>
<ol>
    <li>Navigate to the IAM console: <a href="https://console.aws.amazon.com/iam/" target="_blank">IAM Console</a>.</li>
    <li>Choose "Policies" in the left navigation pane.</li>
    <li>Click "Create policy."</li>
    <li>Choose the "JSON" tab and paste the policy JSON:</li>
    <pre>
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
    <li>Click "Review policy
