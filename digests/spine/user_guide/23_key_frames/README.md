키 프레임 (Key Frames)
======================
<http://ko.esotericsoftware.com/spine-key-frames#Key-Frames>

* 키 프레임(key frames) 기반 애니메이션 
* 키(key): 시작 값과 끝 값의 트랜지션
* 키 사이 중간 값 보간됨(트윈됨)


작업 준비
---------

* 애니메이션 모드 전환
* 트리 뷰 Animations 선택
* 작업 애니 표시 점(visibility dot) 클릭

<p><img src="http://ko.esotericsoftware.com/img/spine-user-guide/key-frames/animation.png"/></p>


타임 라인 (Timeline)
--------------------

* 애니 모드 포즈: 현재 타임 라인 위치 키로 결정
* 도프 시트(dope sheet) 뷰: 타임 라인 편집

<p><img src="http://ko.esotericsoftware.com/img/spine-user-guide/key-frames/dopesheet.png"/></p>

* 초 당 30프레임 기준
* 위치 설정: 프레임 클릭
* 키 설정시 타임 라인 아래 표시됨
* 상세 설명: 도프 시트 페이지 참고 <http://ko.esotericsoftware.com/spine-dopesheet>


키 설정 (Setting Keys)
----------------------

* 애니 모드 스켈레톤 변경 사항 자동 저장 안됨 
* 타임라인 위치 변경시 스켈레톤 변경 사항 사라짐
* 키 저장: 툴 바(or 트리 뷰) 키 버튼 클릭
	* 녹색: 키없음
	* 황색: 변경됨
	* 적색: 저장됨


#### 트랜스폼 (Transforms)

툴바 Rotate, Translate, Scale 도구 수치 키 아이콘 버튼 클릭

<p><img src="http://ko.esotericsoftware.com/img/spine-user-guide/key-frames/keys.png"/></p>

* 황색키 표시: 저장되지 않은 변경 사항 알림
* 특정키 저장: 트리 내 키 버튼 클릭

<p><img src="http://ko.esotericsoftware.com/img/spine-user-guide/key-frames/bone.png"/></p>

현재 XY 이동 및 배율 개별 저장 불가 (동시 저장만 가능)


#### 회전 (Rotation)

* 회전 방향: 키 사이 최단 거리 방향으로 회전
	* 180도 회전: 키 2개 필요
	* 360도 회전: 키 3개 필요

<p><img src="http://ko.esotericsoftware.com/img/spine-user-guide/key-frames/rotate.png"/></p>


#### 어태치먼트 (Attachments)

* 어태치먼트 키: 슬롯 표시 여부
* 트리 뷰 슬롯 아래 어태치먼트 표시 여부 클릭 (슬롯 키 버튼 노란색으로 변경됨)
* 슬롯 키 아이콘 버튼 클릭시 설정됨

<p><img src="http://ko.esotericsoftware.com/img/spine-user-guide/key-frames/attachment.png"/></p>


#### 슬롯 컬러 (Slot color)

애니메이션 중 어태치먼트 틴트 변경
→ 슬롯 선택 후 트리 뷰 아래 컬러 프로퍼티 변경

<p><img src="http://ko.esotericsoftware.com/img/spine-user-guide/key-frames/color.png"/></p>

* 투명 처리:알파 0 설정보다 **감춤** 설정 추천
	* 알파 0 설정시 렌더링 비용 소모
	* 트리 뷰 표시점(Visibility dot) 체크 해제 
* 상세 설명: 키 프레임 페이지 어태치먼트 섹션 참고 <http://ko.esotericsoftware.com/spine-key-frames#Attachments>


#### 드로우 오더 (Draw order)

트리 뷰 드로우 오더 옆 키 버튼 사용

<p><img src="http://ko.esotericsoftware.com/img/spine-user-guide/key-frames/draworder.png"/></p>

* 상세 설명: 이미지 페이지 드로우 오더 섹션 참고 <http://ko.esotericsoftware.com/spine-images#Draw-order>


#### 이벤트 (Events)

* 트리 뷰 Events 노드 아래 각 이벤트 옆 키 버튼 클릭
* 키 설정 전 이벤트 프로퍼티 변경

<p><img src="http://ko.esotericsoftware.com/img/spine-user-guide/key-frames/event.png"/></p>

* 상세 설명: 이벤트 페이지 키잉 섹션 참고 <http://ko.esotericsoftware.com/spine-events#Keying>


#### 메쉬 (Meshes)

* 메쉬 버텍스 위치 키 저장
* 트리 뷰 메쉬 옆 키 버튼 클릭

<p><img src="http://ko.esotericsoftware.com/img/spine-user-guide/key-frames/mesh.png"/></p>

* 상세 설명: 메쉬 페이지 키잉 섹션 참고 <http://ko.esotericsoftware.com/spine-meshes#Keying>


#### IK

* IK 제약 혼합과 휨 방향 키 설정
* 트리 뷰 IK 제약(Constraints) 키 버튼 클릭
* 혼합과 휨 방향 모두 저장됨 

<p><img src="http://ko.esotericsoftware.com/img/spine-user-guide/key-frames/ik.png"/></p>

* 상세 설명: 메쉬 페이지 키잉 섹션 참고 <http://ko.esotericsoftware.com/spine-meshes#Keying>


#### 플립 (Flip)

* 트리 뷰 하단 본 프로퍼티 내 플립 방향 키 설정
* X 플립과 Y 플립 개별 저장됨

<p><img src="http://ko.esotericsoftware.com/img/spine-user-guide/key-frames/flip.png"/></p>


#### 단축키 (Shortcuts)

* 변경 사항 저장(Key Edited): 단축키(K) 키 되지 않은 모든 변경 사항 키 설정
* 도프 시트 자동 키(Auto Key) 활성 화: 변경 사항 발생시 자동 저장
* 상세 설명: 도프 시트 페이지 자동 저장 섹션 참고 <http://ko.esotericsoftware.com/spine-dopesheet#Auto-Key>
* 실행 취소(undo) 
	* 단축키(win:ctrl, mac:cmd + z) 
	* 타임 라인 위치 변경으로 인한 포즈 소실 복구 가능 
* 다시 실행(redo)
	* 단축키(win:ctrl, mac:cmd + shift + z) 
	* redo 변경 사항은 타임 라인 위치 변경시 복구 불가


런타임 차이점(Runtime Differences)
----------------------------------

키가 존재하지 않을 경우 애니 변경 안 됨

* 에디터: 애니 적용 전 셋업 포즈 리셋
* 런타임: 
	* 애니 적용 전 셋업 포즈 리셋
	* 키가 없을 경우 최근 값 사용

#### 예제 상황

* 무기 슬롯에 검 어태치먼트 표시 애니 플레이 → 다음 애니에서도 검 어태치먼트 표시 유지
* 루트 본 45도 회전 상태 종료 애니 플레이 → 다음 애니 루트 본 키가 없음 → 루트 본 45도 회전 상태 유지
* 다음 애니가 원점으로 돌아오는 경우도 **중간 캔슬**될 경우 같은 현상 발생

#### 해결 방법

모든 애니메이션의 모든 키에 0프레임 값 설정

* 한계
	* 애니메이터 노가다 필요
	* 런타임 비효율적 실행
* 추천
	* 프로그램에서 애니 플레이 전 포즈 리셋
	* 애니메이션 변경시 어태치먼트 슬롯 리셋


키 작업 시작 (Explore Keying)
-----------------------------

* 스파인 예제 오픈 
* 트리 뷰 애니메이션 노드 클릭 
* New Animation 버튼 클릭
* 애니 모드 전환 후 0프레임 포즈 설정 후 키 저장(키보드: 단축키(K) 누름)
* 타임라인 적당한 프레임 위치 클릭 후 다른 포즈 설정
* 작업 확인: 타임라인 드래그 혹은 플레이 버튼 클릭