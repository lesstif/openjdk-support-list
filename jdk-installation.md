OS, package manager 별 OpenJDK 설치 방법

## Windows - Scoop

```sh
scoop bucket add java
```

### JDK 8

OpenJDK 8
```sh
scoop install openjdk8
```

AdoptJDK 8 with HotSpot
```sh
scoop install adopt8-hotspot
```

Zulu 8
```sh
scoop install zulu8
```

## Centos 7

http://repos.azulsystems.com/

```sh
$ sudo rpm --import http://repos.azulsystems.com/RPM-GPG-KEY-azulsystems
$ sudo curl -o /etc/yum.repos.d/zulu.repo http://repos.azulsystems.com/rhel/zulu.repo
```

Zulu 패키지 목록 확인

```sh
$ sudo yum list zulu*

Available Packages
zulu-10.x86_64                                       10.3+5-1                                 zulu
zulu-11.x86_64                                       11.2+3-1                                 zulu
zulu-6.x86_64                                        6.22.0.3-1                               zulu
zulu-7.x86_64                                        7.25.0.5-1                               zulu
zulu-8.x86_64                                        8.33.0.1-1                               zulu
zulu-9.x86_64                                        9.0.7.1-1                                zulu
```

설치하려면 Zulu 버전 설치(EX: 8)

```sh
$ sudo yum install zulu-8
```

## Ubuntu 18 LTS