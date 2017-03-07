스킨 (Skins)
============
<http://ko.esotericsoftware.com/spine-skins>

* 스켈레톤 당 어태치먼트 세트 단위 교체
* 본과 애니메이션이 비슷한 캐릭터 제작시 유용
* 스킨 플레이스홀더(Skin Placeholder) 기반 작동
	* 슬롯 아래 어태치먼트 형태로 부착
	* 현재 액티브 스킨 정보에 따라 실제 어태치먼트 표시
	* 스킨 교체시 스켈레톤 내 모든 스킨 플레이스 홀더의 어태치먼트 변경

셋업(Setup)
-----------
스킨과 스킨 플레이스홀더를 만든 후 어태치먼트 부착

#### 스킨 (Skin)

* 트리 뷰 Skins 노드 선택
* New Skin 버튼 클릭 

<p><img src="http://ko.esotericsoftware.com/img/spine-user-guide/skins/new.png"/><p>


#### 스킨 플레이스 홀더 (Skin Placeholders)

* 본 선택 (or 트리 뷰 슬롯 선택)
* New 버튼 클릭
* Skin Placeholder 메뉴 클릭

<p><img src="http://ko.esotericsoftware.com/img/spine-user-guide/skins/new-placeholder.png"/><p>

* 스킨 별 어태치먼트 보유
* 스킨에 관련된  이름보다는 어태치먼트에 관련된 이름 사용 추천
	* 어태치먼트 이름: `head`
	* 스킨 이름 :`red_skin`, `blue_skin` 
	* 좋은 스킨 플레이스 홀더 이름: `head`
	* 나쁜 스킨 플레이스 홀더 이름: `red_head`, `blue_head` 


#### 어태치먼트 (Attachments) 배치

스킨 활성화: 트리 뷰 Skins 노드 아래 스킨 표시점(Visibility Dot) 클릭
 
<p><img src="http://ko.esotericsoftware.com/img/spine-user-guide/skins/active.png"/><p>

* 스킨 활성화 후 플레이스 홀더 아래 어태치먼트 배치 가능
* 활성화 스킨 변경시 기존 스킨에 배치된 어태치먼트는 사라지고 새로운 스킨에 정의된 어태치먼트가 표시됨


빠른 작업(Shortcuts)
--------------------

#### 스킨 플레이스홀더 추가
 
어태치먼트만 존재하는 스켈레톤에 스킨 플레이스홀더 대량 추가

* 트리 뷰 필터: 본과 슬롯 감춤 → 어태치먼트만 표시됨
* 새로운 스킨 생성 (or 기존 스킨 활성화)
* 기존 어태치먼트 선택
* New 버튼 클릭 > Skin Placeholder 선택

<p><img src="http://ko.esotericsoftware.com/img/spine-user-guide/skins/convert-placeholder.png"/><p>

어태치먼트와 동일한 이름의 스킨 플레이스 홀더 생성됨

#### 스킨 플레이스홀더 제거

필요가 없어진 스킨 플레이스홀더 대량 제거

* 스킨 플레이스 홀더 선택 후 트리 뷰 하단 삭제 버튼 클릭
* 삭제 다이얼로그에서 Keep current attachment 체크

<p><img src="http://ko.esotericsoftware.com/img/spine-user-guide/skins/delete.png"/><p>

스킨 플레이스홀더만 제거되고 어태치먼트는 자동으로 슬롯으로 이동됨


애니메이션 재활용
-----------------
스파인 예제: goblins


#### 예제1 

남여 고블린 구현

* 직접 구현:
	* 남여 고블린 어태치먼트 생성
	* 남여 고블린 어태치먼트 이름 목록 구축
	* 런타임시 고블린 성별에 따라 어태치먼트 표시 여부 결정
* 스킨 구현:
	* male, female 스킨 생성
	* 스킨별 어태치먼트 연결
	* 런타임시 스킨 변경
 

#### 예제2

남여 고블린 눈 깜박임

* 직접 구현: 
	* eyesClosed-male, eyesClosed-female 어태치먼트별 애니 생성
	* 런타임시 고블린 성별에 따라 애니 플레이
* 스킨 구현:
	* male, female 스킨 생성
	* eyesClosed 스킨 플레이스홀더 생성
	* eyesClosed 단일 애니 생성
	* 런타임시 eyesClosed 애니 플레이


스킨 조합
---------

* 에디터상 스킨 조합 불가능 (향후 계획: <https://trello.com/c/7WRv4DuN/71-allow-multiple-skins-to-be-activated-at-once>)
* 런타임상 스킨 조합 가능 

#### 아바타 시스템

얼굴, 몸체, 복장 조합과 매치 필요

* 에디터 작업
	* 스킨 플레이스홀더 생성
	* 아이템별 어태치먼트 그룹 스킨 생성
* 런타임 작업  
	* 동적 스킨 생성
	* 아이템별 어태치먼트 배치

#### 아바타 구현 예제

* 에디터 작업
	* red_skirt 스킨 생성
	* torso, sleeveLeft, sleeveRight 플레이스홀더 구성
* 런타임 작업
	* 동적 스킨 생성
	* red_skirt 스킨에서 어태치먼트들을 가져와 동적 스킨에 배치


동영상 강좌
-----------
<https://www.youtube.com/watch?v=xY4m3iNtSUQ>