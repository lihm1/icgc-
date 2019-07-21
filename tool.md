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
   #### 按要求配置
## aws-cli
