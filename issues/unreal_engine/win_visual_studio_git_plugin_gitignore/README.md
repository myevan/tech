# 언리얼 엔진

## 이슈

### 비주얼 스튜디오 팀 탐색기 변경 내용 많음

#### 재현 환경

* OS: Windows 10 Pro 64bit
* UE: 4.15.0
* IDE: VisualStudio Community 2015 14.0.25431.01 Update 3

#### 재현 방법

언리얼 git 저장소 클론 후 Setup.bat 를 실행합니다    

#### 문제 상황

팀 탐색기 > 변경 내용 (15781개)

    .suo [추가]
    AgentInterface.dll [추가]
    AllDesktop.Automation.dll [추가]
    AllDesktop.Automation.pdb [추가]
    ...

#### 문제 원인

언리얼에서는 버전 관리 대상 파일을 블랙 리스트 대신 화이트 리스트 관리하는데 비주얼 스튜디오 git 플러그인에서 제대로 지원하지 못함

### 문제 분석

팀 탐색기 > 프로젝트 > 설정 > Git > 리포지토리 설정 > 무시 및 특성 파일 > 무시 파일 편집

    # Ignore all files by default, but scan all directories
    *
    !*/

비주얼 스튜디오 git 플러그인에서 `!*/` 문구를 제대로 처리하지 못함

<http://stackoverflow.com/questions/25554504/what-does-mean-in-gitignore>


### 문제 해결

Git 앱을 다른 앱으로 교체한다

* SmartGit
* SourceTree




