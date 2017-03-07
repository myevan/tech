도구 (Tools)
===============
<http://ko.esotericsoftware.com/spine-tools>

에디터 영역 하단 툴 바

* Tools 색션
* Transform 섹션
* Axis 섹션
* Compensate 섹션
* Options 섹션

<p><img src="http://ko.esotericsoftware.com/img/spine-user-guide/tools/toolbar.png"/></p>

에디터 영역 우 클릭시 현재 툴과 최근 선택 툴 토글 가능

* 툴 바 버튼 클릭보다 빠름
* 여러 개 툴 교체 사용시 편리


선택 (Selection)
----------------

#### 스마트 선택 시스템 (Smart selection system)

* 단일 선택: 에디터 영역 내 선택하고 싶은 아이템 클릭
* 다중 선택: 단축키(win:ctrl, mac: cmd) 누르고 각 아이템 클릭
* 박스 선택: 단축키(win:ctrl, mac: cmd) 누르고 드래그 (첫 선택시에는 단축키 조합 없이도 가능)
* 선택 취소: esc, space, 에디터 영역 더블 클릭

#### 선택 그룹 관리 (Selection groups)

스켈레톤 포즈 작업시 파츠별 그룹 관리 (예: 몸통, 머리, 팔, 다리 선택 그룹 지정)

* 선택 저장: 단축키(win:ctrl, mac:cmd + 숫자)
* 선택 로드: 단축키(숫자)


트랜스폼 도구(Transform tools)
------------------------------

* 회전(Rotate), 이동(Translate), 스케일(Scale) 모두 동일 작동
* 마우스 드래그로 선택한 아이템 트랜스폼 조절
* 빈 공간(혹은 선택 아이템)부터 드래그 시작 
* 다른 아이템 위에서 드래그 시작시 아이템 선택이 변경됨
* 다중 선택과 박스 선택은 스마트 선택 시스템 사용

#### 수치 (Numeric entry)

기준 축 기준 수치 표시

<p><img src="http://ko.esotericsoftware.com/img/spine-user-guide/tools/transform.png"/></p>

* 직접 수치 입력 후 엔터 (혹은 탭) 
* 마우스 휠 스크롤 수치 조정 (shift 키 조합시 미세 수치 조정)
* 화살표 키 수치 조정 (shift 키 조합시 미세 수치 조정)

#### 좌표계 (Axes)

표시 수치 기준 

* 선택: Local, Parent, World
* 에디터 영역: 좌표계 방향 표시됨 (트랜스폼 가이드 제공) 

<p><img src="http://ko.esotericsoftware.com/img/spine-user-guide/tools/axes.png"/></p>

#### 트랜스폼 복사 (Transform copy)

* 조작
	* 복사하기: 단축키(win:ctrl, mac:cmd + c)
	* 붙여넣기: 단축키(win:ctrl, mac:cmd + v)
* 기능
	* 여러 개 트랜스폼 복사 가능
	* 대상 트랜스폼은 소스 트랜스폼 수치로 설정됨
	* 계층 구조 복사 가능
	* 동일한 팔다리 복사나 다음 프레임 애니 작업시 사용됨

#### 회전 도구 (Rotate tool)

* 본의 원점 기준 반시계 회전 (단축키(shift) 조합시 15도 단위 회전)
* 회전 각도: 0도 ~ 360도 사이로 정규화
* 180 도 이상 회전은 키 프레임 회전 페이지 참고 <http://ko.esotericsoftware.com/spine-key-frames#Rotation>
* 좌표계별 작동
	* Local, Parent: 부모 기준 반시계 회전(부모 X축 0도)
	* World: 반시계 회전(오른쪽 0도, 위쪽 90도, 왼쪽 180도, 아래쪽  270도)

#### 이동 도구 (Translate tool)

* XY 축 이동 (단일 축 이동 제한 가능)
* 좌표계별 작동
	* Local: 부모 기준 거리 (자기 회전 방향이 X축)
	* Parent: 부모 기준 거리 (부모 회전 방향이 X축)
	* World: 월드 기준 거리 

<p><img src="http://ko.esotericsoftware.com/img/spine-user-guide/tools/translate.png"/></p>

* Local, Parent 좌표계 선택에 따라 같은 수치로 다른 방향 이동 가능
* Parent 좌표계 선택 후 Translate 툴 아이콘의 X축(빨간색) 화살표 드래그 이동


#### 스케일 도구 (Scale tool)

* XY 축 스케일 (단일 축 스케일 제한 가능)
* 로컬 축 기준 스케일 적용
	* 스케일 X축과 로컬 회전 방향 동일
	* 부모 본 스케일 상속시에도 동일 
	* 고전적인 스케일 시스템과 다름

<p><img src="http://ko.esotericsoftware.com/img/spine-user-guide/tools/scale.png"/></p>

* spineboy 다리 구조: X축: 허벅지 → 정강이 → 발
* 허벅지 X축 확대 → 정강이와 발 확대 (원하지 않을 경우 스케일 상속(Scale Inheritance) 비활성화 설)
* 현재 스파인 스케일은 꼬이는 결과를 만들지 않음
* -1 스케일로 방향 전환 불가 (트리 뷰 하단 본 **플립** 기능 활용)

<p><img src="http://ko.esotericsoftware.com/img/spine-user-guide/tools/flip.png"/></p>

* 좌표계별 작동: 모두 로컬 좌표계 사용
	 

#### 본 길이 도구 (Bone length tool)

* 셋업 모드 트랜스폼 툴 활성화 시점
* 마우스 커서를 본 끝에 위치 시 길이 조절 가능
* 여러 개 본도 동시에 조절 가능
* 트리 뷰 하단 본 Length 수치 조절 가능

<p><img src="http://ko.esotericsoftware.com/img/spine-user-guide/tools/bone-length.png"/></p>

검 길이 조절 예제



포즈 도구 (Pose tool)
---------------------

* IK(Inverse Kinematics) 기반 본 회전 조절
* 여러 개 본 선택 시 표시되는 타겟 아이콘 드래그
* 포즈 도구 상태에서는 단축키(win:ctrl, mac:cmd) 없이도 박스 선택 가능)
* 동일한 본 구조내 다중 본 선택시 타겟 아이콘 위치 기준으로 계층 구조 내 본 회전이 역 계산됨

<p><img src="http://ko.esotericsoftware.com/img/spine-user-guide/tools/pose.png"/></p>

포즈 도구 꼬리 조절 예제

<p><img src="http://ko.esotericsoftware.com/img/spine-user-guide/tools/pose-multiple.png"/></p>

팔 & 다리 선택 예제: 타겟 아이콘 드래그시 팔에는 적용 안 되고 다리에만 적용 됨



웨이트 도구 (Weights tool)
--------------------------
<http://ko.esotericsoftware.com/spine-weights>

* 웨이트 뷰(Weights view): 메쉬당 버텍스 본 영향 표시
* 웨이트 도구(Weights tool): 웨이트 뷰 조합 


생성 도구 (Create Tool)
-----------------------

셋업 모드용 새로운 본 생성

* 조작
	* 부모 본 선택 후 드래그 → 드래그 라인 범위에 본 생성
	* 클릭 시 길이 0 본 생성 (십자 아이콘으로 표시됨)
* 본 길이
	* 장식용 (IK 나 자동 웨이트 설정시에만 사용됨)
	* 애니메이션 작동시 영향 없음

<p><img src="http://ko.esotericsoftware.com/img/spine-user-guide/tools/bones.png"/></p>


#### 본 생성

* 체크
	* 본 생성 위치 선택 시 회전 피봇 고려
	* 본 생성 위치 제한 없음 (부모 본 끝이 아니라도 가능)
* 조작
	* 새로운 본 어태치먼트 연결: 에디터 상 본 위치 기준 
		* 본 생성 후 어태치먼트 부모 설정
		* 본 생성 전 ctrl(win:cmd)로 어태치먼트 선택
	* 새로운 본 생성 시 슬롯 자동 이동 됨
* 특징: 새로운 본 이름은 슬롯내 첫번째 어태치먼트 이름 자동 선택


#### 본 수정

본 위치 변경

* 조작
	* 본 선택 후 단축키(win:alt, mac:option)조합 드래그
	* 다시 생성한 본 클릭 
* 특징: 자식 본과 어태치먼트에는 영향을 주지 않음


#### 본 컬러

본 그룹 설정

* 조작: 본 선택 후 트리 뷰 하단 Color 설정 가능
* 예제: 왼쪽 다리와 오른쪽  다리 컬러 구분

<p><img src="http://ko.esotericsoftware.com/img/spine-user-guide/tools/colors.png"/></p>



보정 (Compensation)
-------------------

보정 활성화 중 본 트랜스폼시 자식 본과 어태치먼트에 영향을 주지 않음 

<p><img src="http://ko.esotericsoftware.com/img/spine-user-guide/tools/compensate.png"/></p>

#### 어태치먼트 고정 & 본 이동

* 이미지 보정(Compensation:Images) 활성화
* 셋업 모드 모두 작동, 애니 모드 일부 작동 (메쉬  가능, 리전 불가)

#### 자식 본 고정: 본 이동
 
* 본  보정(Compensation:Bones) 활성화
* 애니 모드시 본 보정시 자식 본 키 생성(키 사이 보간으로 자식 본 이상 움직임 발생 가능)

#### 주의사항

* 혼란 방지를 위해 사용하지 않을 때는 비활성화 추천
* 유니폼스케일이 아닌 경우(X 스케일 != Y 스케일) 어태치먼트 고정이 안 될 수 있음



옵션 (Options)
--------------

* 대상: 본, 어태치먼트, 바운드
* 기능: 선택, 표시, 이름 태그

<p><img src="http://ko.esotericsoftware.com/img/spine-user-guide/tools/options.png"/></p>

#### 기능

* 선택: 실수 방지
* 표시: 본을 감추어  애니 작업 중  혼란 방지 (본이 감춰진 상태에서도 마우스 오버시 선택 가능)
* 이름 태그: 원하는 본과 어태치먼트를 쉽게 찾을 수 있음 (평소에는 감추어서 혼란 방지)

