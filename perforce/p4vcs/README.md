Perforce DVCS
=============

퍼포스 분산 버전 관리 시스템 


설치
----

#### OS X

베타 버전 바이너리 다운로드

    $ wget ftp://ftp.perforce.com/perforce/r15.1/beta/bin.darwin90x86_64/p4d
    $ wget ftp://ftp.perforce.com/perforce/r15.1/beta/bin.darwin90x86_64/p4

바이너리 실행 권한 부여

    $ chmod a+x p4d
    $ chmod a+x p4

유저 로컬 바이너리 설치

    $ sudo mv ./p4d /usr/local/bin
    $ sudo mv ./p4 /usr/local/bin


사용 방법
---------

#### 프로젝트 초기화

    $ mkdir ~/Projects/PROJECT
    $ cd ~/Projects/PROJECT
    $ p4 init

#### 파일 변경 반영

    $ vim README.md
    $ p4 reconcile

#### 변경 상태 확인 

    $ p4 status

#### 로컬 저장 

    $ p4 submit 

#### 현재 브랜치 보기

    $ p4 switch 

#### 새로운 브랜치 생성

    $ p4 switch -c

#### 모든 브랜치 보기

    $ p4 switch -l

