# my-utilities
my utilities to build and maintenance my web


## Backup & Restore DB using Mongodb
docs: https://docs.mongodb.com/manual/tutorial/backup-and-restore-tools/
1. Backup

```
$ mongodump --db $database_name (local)
$ mongodump --host mongodb1.example.net --port 3017 --username user --password "pass" --out /opt/backup/mongodump-2013-10-24

```
##### Explanation
- `--out` is output path
-


2. Restore

```
$ mongorestore --db db_name db_path_backup_file (local)

$ mongorestore --host mongodb1.example.net --port 3017 --username user --password 'pass' /opt/backup/mongodump-2013-10-24

```

## Store your backup data to S3
docs: https://docs.aws.amazon.com/en_us/cli/latest/userguide/cli-services-s3-apicommands.html

Make sure you are already install aws-cli, for check your aws config, type `aws configure`, check your aws id, and access key.


1. Check your aws list bucket s3

```
$ aws s3 ls
```

2. Move Your Backup or Copy your backup and store it to s3

```
$ aws s3 cp $your_file s3://your_bucket_name/folder_if_any

$ aws s3 mv $your_file s3://your_bucket_name
```

##### Explanation
- `cp` copy
- `mv` move
