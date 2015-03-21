Perforce Stream
===============

퍼포스 스트림이란 다른 버전 관리 시스템의 **브랜치**를 말합니다.
퍼포스는 브랜치란 용어를 이미 약간 다른(?) 개념으로 사용하고 있었기 때문에
대신 **스트림**이라는 용어를 도입해 사용하고 있습니다.


P4V 사용 방법
-------------

#### 준비 확인

스트림을 사용하기 위해서는 퍼포스 관리자가 스트림 디팟을 구성한 후 접근 권한을 열어줘야 합니다.

디팟(Depot) 뷰를 보면 아래와 비슷한 내용을 확인할 수 있습니다.

    //depot/
        PATH1/
            TO1/
        PATH2/
            TO2/
    //TEAM1/
        main/
            TO1/
            TO2/
        dev/
            TO1/
            TO2/

//depot 아래 있는 TO1, TO2 가 기존 프로젝트로 //TEAM1 아래 TO1, TO2 에 복사되어 있는 모습입니다.
스트림에서는 워크스페이스 맵핑을 사용할 수 없으므로 팀별로 작업할 프로젝트들을 모아둬야 합니다.


#### 환경 설정

워크스페이스가 퍼포스 핵심 BM 모델(?)이라 그런지, P4V 디폴트 설정은 스트림별로 워크 스페이스를 만들도록 되어있습니다.
심지어 매번 스트림 전환 후 최신 소스 갱신도 필요합니다 ㄱ-); (디렉토리로 나눌거면 브랜치 쓰지 뭐하러 스트림을...)

다행히 현재 워크스페이스에서 스트림 전환 및 자동 갱신 옵션이 있어 git 처럼 편리하게 스트림 변경을 할 수 있습니다.

![P4V Preference Streams](./images/p4v_preferences_streams.png?raw=true)

* 메인 메뉴 Edit > Preferences 메뉴 선택
* 스트림들 (Streams) 패널 선택
* 스트림 워크스페이스들 (Stream Workspaces) 섹션 
	* 이 스트림에서 작업 선택시 (When clicking 'Work in this Stream'): reuse current workspace 선택
	* 워크스페이스 아이콘 드래그시 (When dragging workspace icon to a new steam): reuse current workspace 선택
        * 스트림 전환시 모든 스트림 자동 업데이트 (Automatically update the workspace with all stream files when switching between streams): 체크


#### 작업 스트림 연결

스트림 디팟에 접근이 가능하면 워크스페이스 다이얼로그의 스트림 항목이 활성화됩니다. 
스트림 선택시 기존 워크스페이스 맵핑이 사라지므로 스트림 연결하기전에 진행 중인 작업은 모두 서밋되었는지 확인이 필요합니다.

![P4V WorkspaceView Stream](./images/p4v_workspace_view_stream.png?raw=true)

* 메인 메뉴 View > Workspaces 메뉴 선택
* 워크스페이스들(Workspaces) 뷰 현재 워크 스페이스 선택
* 스트림 브라우즈(Stream Browse) 버튼: main 스트림 선택


#### 작업 스트림 변경

현재 구성된 스트림간 전환이 가능합니다. 
펜딩(Pending) 정보에 연관된 스트림이 표시되지 않으므로, 전환전에 서밋 여부를 확인하는게 좋습니다.

![P4V StreamView Switch](./images/p4v_stream_view_graph_switch.png?raw=true)

* 스트림 리스트 (Streams) 뷰 그래프 패널에서 대상 스트림 더블 클릭 
* 이 스트림에서 작업(Work is this Stream) 클릭 or 모니터 아이콘 드래그


#### 자식 스트림 수정 사항 부모 스트림 반영

부모 스트림에 반영은 디폴트로 **복사**만 가능하기 때문에 반영전에 부모 스트림 변경 사항을 가져와야 합니다.
복사 특성상 자식 스트림에 수정한 내역이 통합되어 전달됩니다.

![P4V StreamView Graph CopyToParent](./images/p4v_stream_view_graph_copy_to_parent.png?raw=true)

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

부모 변경 사항을 가져오지 않고 반영시 경고가 표시되며, 자식에도 수정사항이 있을 경우 빨간색 선으로 표시됩니다. 

![P4V StreamView Graph Collision](./images/p4v_stream_view_graph_collision.png?raw=true)

#### 부모 스트림 수정 사항 자식 스트림 반영

자식 스트림에 반영은 디폴트로 **머지**만 가능합니다. 머지 특성상 부모 스트림에 수정한 내역이 그대로 전달됩니다.

![P4V StreamView Graph MergeToChild](./images/p4v_stream_view_graph_merge_to_child.png?raw=true)

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

스트림 기반으로 작업한 내용을 다른 팀에서도 사용할 수 있게하려면 디팟에 반영해야 합니다.
디팟 반영시 수정한 내역은 통합됩니다.

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

다른 팀이나 디팟에서 수정된 내용을 다시 스트림에 적용하려면 머지 기능을 사용합니다.
스트림이 연결된 워크스페이스에서만 가능합니다.

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


#### 워크 스페이스 맵핑 확인

스트림은 맵핑 변경 불가능

 * //depot/PATH1/TO1
 * //depot/PATH2/TO2



#### 스트림 디팟 준비

P4Admin 에서 팀 단위로 스트림 디팟을 생성합니다. 

* 디팟 이름(depot name): TEAMX
* 디팟 타입(depot type): stream


#### 메인 라인 생성

P4V 에서 스트림 메인 라인을 생성합니다. 
디폴트 설정은 디팟 구조 그대로 복제하므로 간편한 구조를 원하면 직접 구성해줘야 합니다.

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


#### 개발 라인 생성 

P4V 를 통해 메인 라인을 토대로 새로운 스트림을 생성합니다. 
부모 브랜치 기반 구성 체크를 안 하면 스트림이 빈 상태로 만들어져 기존 파일들이 사라진 것으로 보이므로 주의해야 합니다.

* Streams 탭 > Graph View Options 패널 > main 스트림 선택 후 우클릭
* 메인 기반 새로운 스트림 생성(Create New Stream from 'main')
	* 스트림 이름(Stream name): dev
	* 스트림 타입(Steam type): development
	* 부모 스트림(The parent stream from which this stream will be branched)
        * 스트림 생성시 부모 브랜치(Branch files from parent on stream creation): 체크
	* 확인(OK) 버튼 클릭

#### 특정 파일 제외

스트림에서는 워크스페이스 맵핑이 불가능하기 때문에 작업에 불필요한 대용량 파일을 제외해야 합니다.

스트림 생성시 Advanced 탭 Ignored 섹션에서 제외 파일 패턴을 입력할 수 있습니다.

    /dir/...
    *.ext


참고 자료
---------
* <http://www.perforce.com/blog/110324/streams-tiny-tutorial>
