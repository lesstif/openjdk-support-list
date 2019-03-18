OS, package manager 별 OpenJDK 설치 방법(Azul 사의 Zulu JDK 권장)

## TOC

* [Windows - Scoop](#windows---scoop)
    * [JDK 8](#jdk-8)
* [Centos 7](#centos-7)
* [Ubuntu 18 LTS](#ubuntu-18-lts)

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

* [Attach the Yum Repository on a RHEL, SLES, or Oracle Linux System](http://docs.azul.com/zulu/zuludocs/#ZuluUserGuide/PrepareZuluPlatform/AttachYumRepositoryRHEL-SLES-OracleLinuxSys.htm)

### Azul 사의 Zulu OpenJDK

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

#### 설치 경로

*/usr/lib/jvm/zulu-{version}* 에 설치됨(예: zulu-8의 경우

### AdoptJDK 

```sh
$ wget https://github.com/AdoptOpenJDK/openjdk8-binaries/releases/download/jdk8u202-b08/OpenJDK8U-jdk_x64_linux_hotspot_8u202b08.tar.gz
$ sudo mkdir -p /usr/java
$ tar ztvf OpenJDK8U-jdk_x64_linux_hotspot_8u202b08.tar.gz -C /usr/java/
$ sudo ln -s /usr/java/jdk8u202-b08 /usr/java/adoptjdk-8
$ export JDK_HOME=/usr/java/adoptjdk-8
$ export PATH=${JDK_HOME}/bin:$PATH
```


## Ubuntu 18 LTS

* [Attach the APT Repository on an Ubuntu or Debian System](http://docs.azul.com/zulu/zuludocs/#ZuluUserGuide/PrepareZuluPlatform/AttachAPTRepositoryUbuntuOrDebianSys.htm)

1. import Azul's public key.

    ```sh
    $ sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys 0xB1998361219BD9C9
    ```

1. Add APT repository
    
    ```sh
    $ sudo apt-add-repository 'deb http://repos.azulsystems.com/ubuntu stable main'
    ```

1. Update the information
    
    ```sh
    $ sudo apt update 
    ```

1. list zulu packages

    ```sh
    $ sudo apt-cache search zulu-
    ```
1. Install package

    ```sh
    $ sudo apt install zulu-8 
    ```
