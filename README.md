# tokentest

## AWS credential check

Create a repository Actions secret named `AWS_CREDS` with the contents of an
AWS shared credentials file. The workflow writes the secret to a temporary
`creds` file on the runner; do not commit the file.

```ini
[default]
aws_access_key_id = YOUR_ACCESS_KEY_ID
aws_secret_access_key = YOUR_SECRET_ACCESS_KEY
```

For temporary credentials, also add `aws_session_token` to the profile. In the
**Actions** tab, select **AWS credential check** and click **Run workflow**.
The workflow calls AWS STS `GetCallerIdentity` and reports success without
printing the returned identity.

The same workflow checks a Slack user token with `auth.test`. Create a
repository Actions secret named `SLACK_USER_TOKEN` containing only the
`xoxp-...` token, without quotes or a `Bearer` prefix.
