# Unreal Engine

## 버전 관리 

### 윈도우 git 저장소 

#### 미러링

공식 저장소를 미러링합니다

    > md C:\Repositories\git
    > cd C:\Repositories\git
    > git clone --mirror https://github.com/EpicGames/UnrealEngine

이미 받아 놓은 저장소가 있다면 미러 클론 후 설정을 변경합니다.

    > git clone --mirror C:\OldProjects\UnrealEngine C:\Repositories\git
    > vim C:\Repositories\git\UnrealEngine\config
    [remote "origin"]
    -    url = C:/OldProjects/UnrealEngine
    +    url = https://github.com/EpicGames/UnrealEngine
	fetch = +refs/*:refs/*
	mirror = true

#### 호스팅

<http://aspiringcraftsman.com/2012/02/20/hosting-a-git-repository-in-windows/>

데몬 실행용 배치 파일을 생성합니다.

    > vim C:\Repositories\git\gitd.bat
    @echo off
    "C:\Program Files\Git\bin\git.exe" daemon --reuseaddr --base-path=%~dp0 --export-all --enable=receive-pack --timeout=1800

서비스 등록 앱<https://github.com/derekgreer/serviceRunner>을 빌드한 다음 서비스 배치 파일을 작성합니다.

    > vim C:\Repositories\git\gitd_service_create.bat
    @echo off
    sc.exe create "GitDaemon" binpath="%~dp0\ServiceRunner.exe %~dp0\gitd.bat" start=auto
    pause

    > vim C:\Repositories\git\gitd_service_start.bat
    @echo off
    sc.exe start "GitDaemon"
    pause

    > vim C:\Repositories\git\gitd_service_stop.bat
    @echo off
    sc.exe stop "GitDaemon"
    pause

    > vim C:\Repositories\git\gitd_service_delete.bat
    @echo off
    sc.exe delete "GitDaemon"
    pause

관리자 권한으로 서비스 배치 파일을 실행해 서비스를 등록-시작합니다. 

#### 로컬 테스트

    > git clone git://localhost/UnrealEngine

#### 원격 업데이트

    > cd C:\Repositories\git\UnrealEngine
    > git remote update