# mfa

It is the wrapper script to switch role with MFA, uses `~/.aws/config` as well as aws-cli.

## USAGE

Put your profile into `~/.aws/config`:

```
[profile role-with-mfa]
region = us-west-2
role_arn= arn:aws:iam::128716708097:role/cli-role
source_profile = cli-user
mfa_serial = arn:aws:iam::128716708097:mfa/cli-user
```

Execute commands via `mfa`:

```console
$ export AWS_PROFILE=role-with-mfa
$ mfa terraform plan
Enter MFA code for arn:aws:iam::128716708097:mfa/cli-user:
```
