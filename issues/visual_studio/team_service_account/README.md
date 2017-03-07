# 비주얼 스튜디오 이슈

## 팀 서비스 계정에 연결할 수 없음

### 환경

* IDE: VisualStudio Community 2015 14.0.25431.01 Update 3

### 재현

비주얼 스튜디오 실행 후 로그 확인

### 상황

비주얼 스튜디오 시작시 에러 표시됨

    We were unable to automatically populate your Visual Studio Online accounts.
    F400813: Resource not available for anonymous access. Client authentication required.


### 해결
    
<https://connect.microsoft.com/VisualStudio/feedback/details/2199711/we-were-unable-to-automatically-populate-your-visual-studio-online-accounts>

    On the top right corner of the IDE you will see your name and or initials. 
    Click the drop down, select account settings then sign out. 
    Restart Visual Studio. Sign in and problem solved.

IDE 상단 오른쪽 계정 정보 클릭

계정 다이얼로그 상단 왼쪽 계정 설정에서 로그 아웃 후 비주얼 스튜디오 재실행

