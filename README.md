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

| Region Name	            | Region	        |
| ----------------------- | -------------- |
| US West (N. California) | us-west-1      |
| US West (Oregon)	       | us-west-2	     |
| Asia Pacific (Tokyo)	   | ap-northeast-1	|

* Install AWS CLI on OSX

```shellscript
sudo pip install --upgrade pip # upgrade pip
sudo pip install awscli --ignore-installed six 
```

* To add new users in EC2 instance manually.
  * [Managing User Accounts on Your Linux Instance](http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/managing-users.html)
* 

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

## Shellscript

* Close a terminal without killing the command running in it. [Gist](https://gist.github.com/jonascheng/0c18b97378b3e375542538b77c1f2ec9)
* List files over 100MB

```
find . -type f -size +100M
```

