# AWS MFA Login

## Introduction:
This script logs in an AWS Access Key / Secret Key via 2FA on your CLI.

This script assumes you're already having a working AWS CLI and profile.  If you are using AWS CLI profiles, make sure you set your profile before running this script with eg: `export SOURCE_PROFILE=mycompany` which is the same name you used to `aws configure --profile mycompany`.

For a helper for this, see: https://github.com/DevOps-Nirvana/aws-missing-tools/tree/master/aws-choose-profile

OR...

```
# First, try this command (replace mycompany with your awscli profile name and the name of your aws account alias or company name)
AWS_DEFAULT_PROFILE=mycompany ASSUME_ROLE_LABEL=mycompany aws-virtual-mfa

# and if that works, make an alias in your ~/.bash_profile like this...
echo "alias mycompany_aws_2fa='AWS_DEFAULT_PROFILE=mycompany-aws-root ASSUME_ROLE_LABEL=mycompany aws-virtual-mfa'" >> ~/.bash_profile

# begin using it instantly
source ~/.bash_profile

# then run it with...
mycompany_aws_2fa
```

This combos nicely with the [AWS IAM Require MFA Allow Self Service Profile](../aws-iequire-mfa-allow-self-service)