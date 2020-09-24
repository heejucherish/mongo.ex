### 몽고디비 install on CentOS 6/7

- 검색 Mongodb yum install centos

- https://docs.mongodb.com/manual/tutorial/install-mongodb-on-red-hat/

```bash
vi /etc/yum.repos.d/mongodb-org-4.4.repo

# Add and Save
[mongodb-org-4.4]
name=MongoDB Repository
baseurl=https://repo.mongodb.org/yum/redhat/$releasever/mongodb-org/4.4/x86_64/
gpgcheck=1
enabled=1
gpgkey=https://www.mongodb.org/static/pgp/server-4.4.asc
#

yum update
yum install mongodb-org
```


### 리눅스에서 시스템 서비스 설정 위치(CentOS 6/7)

- /etc/rc.d/init.d

```bash
cd /etc/rc.d/init.d

ls mongo*
cat mongod
```

- /var/lib/mongo : 데이터 디렉터리
- /var/log/mongodb : 로그 디렉터리
- /etc/mongod.conf : 설정 파일


### 설정 및 시작

```bash
vi /etc/mongod.conf

bindIp를 0.0.0.0으로 설정 # 외부 접속 허용
```

```bash
# 서비스 시작
service mongod start
ps -ef | grep mongod
```
