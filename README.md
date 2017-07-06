# iamsshsync

iamsshsync synchronizes IAM users and their CodeCommit SSH keys to your EC2 instances every 10 minutes.

## Important notes

* It's **not production ready**.
* It gives all users sudo access.
* It doesnt't filter users in IAM: it adds all of them.

## Prerequisites

* [AWS CLI](https://aws.amazon.com/cli/) installed
* An instance profile that allows read access to IAM users, groups and SSH keys.

  For example:

  ```
  {
    "Sid": "AllowFetchAWSUserSSHKeys",
    "Effect": "Allow",
    "Action": [
      "iam:ListUsers",
      "iam:GetGroup",
      "iam:ListSSHPublicKeys",
      "iam:GetSSHPublicKey"
    ],
    "Resource": "*"
  }
  ```

## Installation

You can clone this repository and build the package:

```
dpkg -b iamsshsync_1.0-1
```

Or install the one I provided:

```
dpkg -i iamsshsync_1.0-1.deb
```

## Credits

The source comes from: https://github.com/sportebois/aws-ec2-ssh-sync
