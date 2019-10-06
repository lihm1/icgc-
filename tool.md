## tool.md
## icgc-get
[icgc-get](https://docs.icgc.org/download/icgc-get/#icgc-get-user-guide)
~~~
$:curl https://dcc.icgc.org/api/v1/ui/software/icgc-get/linux/latest -o icgc-get.latest.zip -L
$:unzip icgc-get.latest.zip 
$:./icgc-get 
$:./icgc-get configure ## 配置
Enter a directory for downloaded files to be saved to. icgc-get will attempt to create it if it does not exist.
output []: icgc

Enter a location for the process logs to be stored.  Must be in an existing directory.  Optional.
logfile [/home/lhm/.icgc-get/icgc_get.log]: icgc
Error: Logfile destination "icgc" is a directory
logfile [/home/lhm/.icgc-get/icgc_get.log]: 

Enter which repositories you want to download from.
 Valid repositories are: collaboratory aws-virginia ega gdc pdc
repos []: collaboratory aws-virginia ega gdc pdc
Enter true or false if you wish to use a docker container to download and run all download clients
docker []: true
Configuration file saved to /home/lhm/.icgc-get/config.yaml

$:vi /home/lhm/.icgc-get/config.yaml
# Configuration for icgc-get
# For documentation, see: http://docs.icgc.org/cloud/icgc-get/#configuration

# Location of the log file that icgc-get will log to.
logfile: /home/lhm/.icgc-get/icgc_get.log

# Location for the destination directory for downloaded files.
output: icgc

# Use docker container for the storage clients, rather than providing your own client.
docker: True

# Repositories to use and their precedence.
repos:
- 

# ICGC
#icgc:
# token: <icgc_token>
# path: path/to/icgc/storage/client


# GNOS
#gnos:
# key:
#   <repo_code> : <key>
# path: path/to/genetorrent/client
~~~
   #### 按要求配置，官网有介绍
## aws-cli
[aws安装教程](https://docs.aws.amazon.com/zh_cn/cli/latest/userguide/cli-chap-install.html#post-install-uninstall)

Python 2.7.9 + 或 Python 3.4+ 以上版本都自带 pip 工具。
如果没有pip，需要安装pip
~~~
curl https://bootstrap.pypa.io/get-pip.py -o get-pip.py
python gt-pip.py
pip -version
~~~
用python的pip进行安装
~~~
pip install awscli
aws -version
~~~
安装后需要配置awscli
~~~
aws configure --profile pdc
aws
bash manifest.pdc.1562119959624.sh  #.sh可以直接在icgc官网上下载
~~~
配置的文件在 /home/lhm/.aws 可以看到

## gdc数据下载
~~~
wget https://gdc.cancer.gov/system/files/authenticated%20user/0/gdc-client_v1.4.0_Ubuntu_x64.zip
unzip gdc-client_v1.4.0_Ubuntu_x64.zip
./gdc-client download -m gdc_manifest.2019-07-03.txt -t token.txt
~~~
[网址](https://docs.gdc.cancer.gov/Data_Transfer_Tool/Users_Guide/Data_Download_and_Upload/)
## score-client
###### 需要The Score Client requires Oracle Java 8 to be installed. The procedure for installing Java 8 will vary depending on the operating system and package manager used. As an example, here we show how to install Oracle JDK 8 on Ubuntu Linux distribution
[score_client 官网](https://docs.icgc.org/download/guide/#score-client-usage)
~~~
wget -O score-client.tar.gz https://artifacts.oicr.on.ca/artifactory/dcc-release/bio/overture/score-client/\[RELEASE\]/score-client-\[RELEASE\]-dist.tar.gz
tar -xvzf score-client.tar.gz
cd score-client-1.4.0  # or newer version
bin/score-client
bin/score-client help download
~~~


