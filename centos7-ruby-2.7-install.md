# Centos 7 에서 Ruby 2.7 설치

#### 참고

- https://www.server-world.info/en/note?os=CentOS_7&p=ruby27

### 기본 Epel 저장소 에서는 2.0 버전이 설치되어 Fedora 에서 제공 하는 EPEL 저장소를 추가한다.

> 설치 전

```
[root@localhost ~]# ruby -v
ruby 2.0.0p648 (2015-12-16) [x86_64-linux]
```

> 설치 후

```
[root@localhost ~]# yum --enablerepo=centos-sclo-rh -y install rh-ruby27
[root@localhost ~]# scl enable rh-ruby27 bash
scl enable rh-ruby27 bash
[root@localhost ~]# ruby -v
ruby 2.7.1p83 (2020-03-31 revision a0c7c23c9c) [x86_64-linux]
```

### profile 에 등록 하여 새로 접속 해도 ruby 2.7 버전으로 등록 하기

> 파일 생성

```
[root@localhost ~]# vi /etc/profile.d/rh-ruby27.sh
```

> 내용 저장

```
source /opt/rh/rh-ruby27/enable
export X_SCLS="`scl enable rh-ruby27 'echo $X_SCLS'`"
```
