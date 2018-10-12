# AWS study note

## S3

### Access S3
`aws s3 ls [bucket name]`

options 
* `--summarize` 
* `--recursize`
* `--human-readable`


### Sync S3

The "sync" command will synchronize a local folder with your S3 bucket and
can be used as a very simple way to push any content changes that you’ve made to your local files up to S3 without having to log in to the AWS Console.
* `aws s3 sync . s3://[bucket name]`

options

* `--dryrun`
This option will tell you what would happen, but won’t actually do it; it’s good for testing the sync before actually performing it.

### Bucket Permission and Policy

```
{
    "Version": "2018-10-12",
    "Statement": [
        {
            "Sid": "PublicReadForGetBucketObjects",
            "Effect": "Allow",
            "Principal": "*",
            "Action": "s3:GetObject",
            "Resource": "arn:aws:s3:::[bucket name]/*"
        }
    ]
}
```