# Cheatsheet

This is personal cheatsheet to help my daily work.

## AWS 

* Frequent Used AMI

| Region Name    | AMI-ID       |
| -------------- | ------------ |
| us-west-1      | ami-e59bda85 |
| ap-northeast-1 | ami-23b54e42 |

[Amazon EC2 AMI Locator](https://cloud-images.ubuntu.com/locator/ec2/)

* Frequent Used Region Code

| Region Name	            | Region	        | Available Zone        |
| ----------------------- | -------------- | --------------------- |
| US West (N. California) | us-west-1      | us-west-1a 1b 1c      |
| US West (Oregon)	       | us-west-2	     | us-west-2a 2b 2c      |
| Asia Pacific (Tokyo)	   | ap-northeast-1	| ap-northeast-1a 1c    |

* Install AWS CLI on OSX

```shellscript
sudo pip install --upgrade pip # upgrade pip
sudo pip install awscli --ignore-installed six 
```

* To add new users in EC2 instance manually.
  * [Managing User Accounts on Your Linux Instance](http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/managing-users.html)
* [Instance metadata url](http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-instance-metadata.html)

```
curl http://169.254.169.254/latest/meta-data/
# If there is an IAM role associated with the instance at launch.
curl http://169.254.169.254/latest/meta-data/iam/info
```

* List of frequent AWS CLI commands

```
# list associated elb
aws elb describe-load-balancers
```

## MySQL

* Connect to server

```
mysql -h [host] -P 3306 -u root -p # password is required
use [database];
```

* Tables

```
show tables; # show all tables
show table status; # show all table status
```

* Process

```
show [full] processlist;
kill [Id]; # Kill the specific query
CALL mysql.rds_kill(Id); # If permission denied, try this
```

## Shellscript

* Close a terminal without killing the command running in it. [Gist](https://gist.github.com/jonascheng/0c18b97378b3e375542538b77c1f2ec9)
* Misc.
```
# Change default shell to zsh
chsh -s /usr/local/bin/zsh
# List files over 100MB
find . -type f -size +100M
# List export environments
printenv
```

## Git

```
# To bring your remote refs up to date
git remote update
# Revert to specifit commit
git reset --hard <old-commit-id>
git push -f <remote-name> <branch-name>
```

## Docker

```
# compose start or stop
docker-compose [up|stop]
# attach to running image
docker exec -it <containerIdOrName> bin/bash
# remove inactive images
docker rmi -f $(docker images | grep "<none>" | awk "{print \$3}")
# remove dangling volumes
docker volume rm `docker volume ls -q -f dangling=true`
```
