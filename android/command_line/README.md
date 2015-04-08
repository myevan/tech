커맨드 라인 기반 안드로이드 개발
================================

<http://agiliq.com/blog/2012/03/developing-android-applications-from-command-line/>


OS X 준비
---------

#### 설치 

Homebrew wget 설치

    $ brew install wget

안드로이드 환경 폴더

    $ mkdir -p ~/AndroidEnvironments
    $ cd ~/AndroidEnvironments

아파치 ANT 설치

    $ wget http://apache.mirror.cdnetworks.com/ant/binaries/apache-ant-1.9.4-bin.tar.gz
    $ tar -zxvf apache-ant-1.9.4-bin.tar.gz

안드로이드 SDK 설치

    $ wget http://dl.google.com/android/android-sdk_r24.1.2-macosx.zip 
    $ unzip ./android-sdk_r24.1.2-macosx.zip

안드로이드 NDK 설치

    $ wget http://dl.google.com/android/ndk/android-ndk-r10d-darwin-x86_64.bin
    $ chmod +x ./android-ndk-r10d-darwin-x86_64.bin
    $ ./android-ndk-r10d-darwin-x86_64.bin

자바 JDK 설치

    $ wget --no-cookies --no-check-certificate --header "Cookie: gpw_e24=http%3A%2F%2Fwww.oracle.com%2F; oraclelicense=accept-securebackup-cookie" "http://download.oracle.com/otn-pub/java/jdk/8u40-b27/jdk-8u40-macosx-x64.dmg"

    $ open ./jdk-8u40-macosx-x64.dmg


#### 설정

    vim ~/.bash_profile
    export ANDROID_HOME="$HOME/AndroidEnvironments/android-sdk-macosx"
    export NDK_HOME="$HOME/AndroidEnvironments/android-ndk-r10d"
    export ANT_HOME="$HOME/AndroidEnvironments/apache-ant-1.9.4"

    export PATH=$PATH:$ANDROID_HOME/tools:$ANDROID_HOME/platform-tools:$ANT_HOME/bin:$NDK_HOME


POSIX 작업
----------

#### SDK 업데이트

    $ echo "y" | android update sdk -a -u --filter android-15,platform-tools,build-tools-22.0.1,sys-img-armeabi-v7a-android-15


#### 안드로이드 가상 장치 생성

    $ android avd


#### 프로젝트 생성

    $ mkdir -p ~/AndroidProjects
    $ android create project -n TestProject -t 'android-15' -k com.example -a TestActivity -p ~/AndroidProjects/TestProject


#### 프로젝트 디버그 빌드 

    $ cd ~/AndroidProjects/TestProject
    $ ant debug


#### 프로젝트 디버그 설치

    $ ant debug install

