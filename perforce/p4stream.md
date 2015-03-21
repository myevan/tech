Perforce Stream
===============

퍼포스 스트림


사용 방법
---------

#### 스트림 연결 

* 메인 메뉴 VIew > Workspaces 메뉴 선택
* 워크스페이스들 (Workspaces) 뷰 현재 워크 스페이스 선택
* 스트림 브라우즈(Stream Browse) 버튼: main 스트림 선택

#### 환경 설정

* 메인 메뉴 Edit > Preferences 메뉴 선택
* 스트림들 (Streams) 패널 선택
* 스트림 워크스페이스들 (Stream Workspaces) 섹션 
	* 이 스트림에서 작업 선택시 (When clicking 'Work in this Stream'): reuse current workspace 선택
	* 워크스페이스 아이콘 드래그시 (When dragging workspace icon to a new steam): reuse current workspace 선택
        * 스트림 전환시 모든 스트림 자동 업데이트 (Automatically update the workspace with all stream files when switching between streams): 체크

#### 작업 스트림 교체

* 스트림 리스트 (Streams) 뷰 그래프 패널에서 대상 스트림 더블 클릭 
* 이 스트림에서 작업(Work is this Stream) 클릭 or 모니터 아이콘 드래그


#### 자식 스트림 수정 사항 부모 스트림 반영

* 스트림 리스트 (Streams) 뷰 그래프 패널에서 부모 스트림 우클릭
* 부모 스트림으로 복사(Copy to '부모 스트림 이름') 메뉴 선택 
* 복사(Copy) 다이얼로그 오픈
    * 작업 스트림이 부모 스트림으로 변경됨
    * 리졸브와 서밋(Resolve and Submit) 탭
        * 머지 후 파일 자동 리졸브(Automaticaly resolve files after merging): 체크
        * 프리뷰(Prewiew) 버튼 클릭: 변경 사항 확인
        * 복사(Copy) 버튼 클릭
* 펜딩(Pending) 뷰에서 충돌 사항 확인
* 서밋(Submit) 버튼 클릭


#### 부모 스트림 수정 사항 자식 스트림 반영

* 스트림 리스트 (Streams) 뷰 그래프 패널에서 자식 스트림 우클릭
* 자식 스트림으로 머지/통합(Merge/Integrate to '자식 스트림 이름') 메뉴 선택 
* 머지/통합(Merge/Integrate) 다이얼로그 오픈
    * 작업 스트림이 자식 스트림으로 변경됨
    * 리졸브와 서밋(Resolve and Submit) 탭
        * 머지 후 파일 자동 리졸브(Automaticaly resolve files after merging): 체크
        * 프리뷰(Prewiew) 버튼 클릭: 변경 사항 확인
        * 머지(Merge) 버튼 클릭
* 펜딩(Pending) 뷰에서 충돌 사항 확인
* 서밋(Submit) 버튼 클릭


#### 메인 스트림 수정 사항 디팟 반영

* 스트림과 디팟 모두 맵핑된 워크 스페이스 오픈 (관리자 워크 스페이스)
* 디팟(Depot) 뷰에서 소스 디팟 선택 후 우클릭
* 머지(Merge...) 메뉴 선택
    * 머지 메소드(Merge method): Use branch mapping 선택
    * 브랜치 맵핑(Branch mapping) 뉴(New) 버튼 클릭
        * 브랜치 맵핑 다이얼로그 오픈
            * 브랜치 맵핑(Branch mapping): 브랜치 이름 작성
            * 뷰(View) 작성
                * //team1/main/TO1/... //depot/PATH1/TO1/...
                * //team1/main/TO2/... //depot/PATH1/TO2/...
    * 머지 방향 화살표(To reverse the direction of integration, click the arrow): -> 방향 선택
    * 리졸브와 서밋(Resolve and Submit) 탭
        * 머지 후 파일 자동 리졸브(Automaticaly resolve files after merging): 체크
        * 프리뷰(Prewiew) 버튼 클릭: 변경 사항 확인
        * 머지(Merge) 버튼 클릭
* 충돌 확인 후 서밋(Submit) 버튼 클릭


#### 디팟 수정 사항 메인 스트림 반영

* 메인 스트림이 맵핑된 워크 스페이스 오픈 (작업자 워크 스페이스)
* 디팟(Depot) 뷰에서 소스 디팟 선택 후 우클릭
* 머지(Merge...) 메뉴 선택
    * 머지 메소드(Merge method): Use branch mapping 선택
    * 브랜치 맵핑(Branch mapping) 뉴(New) 버튼 클릭
        * 브랜치 맵핑 다이얼로그 오픈
            * 브랜치 맵핑(Branch mapping): 브랜치 이름 작성
            * 뷰(View) 작성
                * //team1/main/TO1/... //depot/PATH1/TO1/...
                * //team1/main/TO2/... //depot/PATH1/TO2/...
    * 머지 방향 화살표(To reverse the direction of integration, click the arrow): <- 방향 선택
    * 리졸브와 서밋(Resolve and Submit) 탭
        * 머지 후 파일 자동 리졸브(Automaticaly resolve files after merging): 체크
        * 프리뷰(Prewiew) 버튼 클릭: 변경 사항 확인
        * 머지(Merge) 버튼 클릭
* 충돌 확인 후 서밋(Submit) 버튼 클릭




관리 방법 
---------


#### P4V: 워크 스페이스 맵핑 확인

스트림은 맵핑 변경 불가능

 * //depot/PATH1/TO1
 * //depot/PATH2/TO2



#### P4Admin: 스트림 디팟 준비

팀 단위로 스트림 디팟 

* 디팟 이름(depot name): TEAMX
* 디팟 타입(depot type): stream



#### P4V: 메인 라인 생성

* Streams 탭 > Graph View Options 패널 > No items Available 우 클릭
* 컨텍스트 메뉴 New Stream 선택
	* 스트림 이름(Sream name): main
	* 스트림 타입(Steam type): mainline
	* 스트림 디팟(The depot where the mainline stream will be located): TEAMX
	* 스트림 워크스페이스 생성(Create a workspace to use with this tream): 체크 안함
	* 스트림 생성 후 메인 스트림 준비(Populate the main stream after it is created): 체크 안함
* 워크 스페이스들 (Workspaces) 뷰: 현재 워크스페이스 선택 후 편집 
	* 스트림(Stream) 선택: //TEAM//main
	* OK 버튼 클릭
* 디팟(Depot) 뷰 선택
	*  기존 맵핑 폴더 선택: //depot/PATH1/TO1
		* 카피(Copy...) 메뉴 클릭
			* 소스 파일 및 폴더 선택(Source files/folders): //depot/PATH1/TO1/...
			* 타겟 파일 및 폴더 선택(Choose target files/folders): //TEAM/main/TO1/...
			* 프리뷰(Preview) 버튼 클릭
			* 카피(Copy) 버튼 클릭


#### P4V: 개발 라인 생성 

* Streams 탭 > Graph View Options 패널 > main 스트림 선택 후 우클릭
* 메인 기반 새로운 스트림 생성(Create New Stream from 'main')
	* 스트림 이름(Stream name): dev
	* 스트림 타입(Steam type): development
	* 부모 스트림(The parent stream from which this stream will be branched)
        * 스트림 생성시 부모 브랜치(Branch files from parent on stream creation): 체크
	* 확인(OK) 버튼 클릭
