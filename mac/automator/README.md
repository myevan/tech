오토메이터
==========

자동화 도구


애플 스크립트
-------------

#### 크롬 웹 페이지 표시

* 이미 실행 중이면 오픈된 윈도우를 찾아 주소 변경
* 오픈된 윈도우가 없거나 실행중이 아니라면 타겟 URL 오픈  

	set TARGET_URL to "http://HOST/path/to"

	tell application "Google Chrome"
		if it is running then
			set WINDOW_COUNT to count windows
			if WINDOW_COUNT > 0 then
				set URL of (active tab of first window) to TARGET_URL
			else
				open location TARGET_URL
			end if
		else
			open location TARGET_URL
		endif
		activate
	end tell


#### 임의 이미지 선정 후 프리뷰 특정 크기 표시

* 지정한 경로에서 임의 파일을 골라 오픈 
* 잠시 로딩 대기 후 프리뷰 화면 크기 변경

	tell application "Finder"
		set RANDOM_FILE to some file of folder "Users:계정:경로:폴더" of startup disk

		open RANDOM_FILE
	end tell

	delay 0.5

	tell application "Preview"
		set bounds of window 1 to {1, 1, 가로크기, 세로크기}
	end tell


오토메이터 자동 실행
--------------------

<http://www.engadget.com/2013/03/18/triggering-applescripts-from-calendar-alerts-in-mountain-lion/>

칼렌더 알람을 사용해 오토메이터를 특정 시점에 실행


#### 오토메이터 앱 준비

자동 실행할 Workflow 를 오픈해 메인 메뉴 File > Convert To 를 사용해 Application 으로 변환한다. 

#### 오토메이터 캘린더 알람 생성

* 오토메이터 실행
* 도큐먼트 타입 선택: Calendar Alaram
* Launch Application 추가
	* 어플리케이션 팝업 메뉴 오픈
	* Other 선택
	* 오토메이터 앱 선택

### 캘린더 알람 설정 

* 오토메이터 캘린더 알람 저장시 Automator 캘린더 자동 등록
* 새로운 이벤트 생성 후 알람 설정 (alert:OpenFile 에서 캘린더 알람 변경 가능)
	  