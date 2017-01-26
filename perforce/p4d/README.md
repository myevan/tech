Perforce Daemon
===============

퍼포스 서버 데몬

윈도우
------

#### 직접 실행 

data 디렉토리 생성 후 유니코드 모드 서버 실행 배치 파일

	IF NOT EXIST %~dp0data GOTO INIT
	GOTO START
	:INIT
	mkdir %~dp0data
	%~dp0p4d.exe -r %~dp0data -L %~dp0log -J %~dp0journal -p 1666 -xi
	:START
	%~dp0p4d.exe -r %~dp0data -L %~dp0log -J %~dp0journal -p 1666 


시놀로지
--------

#### 퍼포스 디렉토리 생성

* 관리자 웹 접속 <http://SYNOLOGY_HOST:5000/>
* 제어판/공유 폴더: perforce 생성

#### 퍼포스 서버 설치

퍼포스 디렉토리 준비

    $ ssh admin@SYNOLOGY_HOST
    $ cd /volume1/perforce
    $ mkdir -p /volume1/perforce/bin
    $ mkdir -p /volume1/perforce/data
    $ mkdir -p /volume1/perforce/var/log

퍼포스 실행 파일 다운로드

    $ cd /volume1/perforce/bin
    $ wget ftp://ftp.perforce.com/perforce/r14.2/bin.linux26armel/p4d
    $ wget ftp://ftp.perforce.com/perforce/r14.2/bin.linux26armel/p4
    $ chmod +x p4d
    $ chmod +x p4

퍼포스 환경 설정

    $ vi ~/.profile
    export PATH=$PATH:/volume1/perforce/bin
    export P4ROOT=/volume1/perforce/data/
    export P4JOURNAL=/volume1/perforce/var/log/journal
    export P4LOG=/volume1/perforce/var/log/p4err
    export P4PORT=1666

퍼포스 서버 준비

    $ p4d -xi 

퍼포스 서버 실행

    $ p4d -d

퍼포스 서버 템프 최소 용량 줄임 (시놀로지 템프 디렉토리 용량이 250MB 보다 약간 작음)

    $ p4 configure set filesys.TEMP.min=128M

퍼포스 서버 중지

    $ p4 admin stop
