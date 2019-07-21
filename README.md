# icgc- 数据下载
>ICGC的数据存储在不同的repository中，不同的仓库有不同的下载工具，所以当在ICGC上搜索到想要下载的数据后，确定其仓库，安装好对应的客户端。
 1.Collaboratory和AWS使用客户端 score-client
  wget -O score-client.tar.gz https://artifacts.oicr.on.ca/artifactory/dcc-release/bio/overture/score-client/[RELEASE]/score-client- [RELEASE]-dist.tar.gz
  tar -xvzf score-client.tar.gz 软件位于bin下
  实际要使用还要安装依赖
  The Score Client requires Java 8 to be installed. It has been tested using the Oracle distribution. The procedure for installing Java 8 will vary depending on the operating system and package manager used. 
 2.GDC使用客户端gdc-client，这个没什么好说的，文档很多，也很简单。
 3.EGA 看https://ega-archive.org/download/using-ega-download-client#DownloadClient， 我暂时也用不到
 4.PDC这个仓库很重要，It is a secure data cloud that stores US   PCAWG data. 它存了PCAWG很多样本的WGS数据，里面就有TCGA的！使用的客户端是Amazon Web Services Command Line Interface，需要follow https://docs.aws.amazon.com/cli/latest/userguide/installing.html进行安装，其实也使用pip，一句话pip install awscli --upgrade --user 安装完后要把执行文件添加到路径中去 export PATH=~/.local/bin:$PATH 。
[师兄](https://www.jianshu.com/p/0de229b751a9)


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
   #### 按要求配置
## aws-cli
