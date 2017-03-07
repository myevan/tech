기본 컨셉(Basic Concepts)
=========================
<http://ko.esotericsoftware.com/spine-basic-concepts>

스켈레톤 셋업시 필요한 기본 컨셉 지식


스켈레톤(Skeletons)
-------------------

* 위치: 트리 뷰  
* 구성 요소: 본, 슬롯, 어태치먼트
* 스켈레톤 추가: 스파인 메뉴 New Skeleton 메뉴 선택

<p><img src="http://ko.esotericsoftware.com/img/spine-user-guide/basic-concepts/tree.png"/></p>


본(Bones)
---------

스켈레톤: 계층적 본 구조
 
#### 기능 
* 트랜스폼
	* 이동, 회전, 스케일
	* 자식 본 영향 (예: 팔(arm) 이동시 손(hand) 같이 이동) 
* 직관적인 이미지 관리
* 애니 작업에 포커스 가능
* 구성 요소간 거리 유지 

<p><img src="http://ko.esotericsoftware.com/img/spine-user-guide/basic-concepts/bones.png"/></p>

#### 용도

* 대부분 종류(인간형, 동물형,...) 애니 가능
* 간단한 골격: 이미지 당 본 1개로 구성
* 메쉬: 본 없이 이미지 애니 작업시 사용


어태치먼트(Attachments)
-----------------------

* 본 부착물(이미지, 메쉬, ...)
* 본 트랜스폼 영향
* 슬롯을 통해 간접 부착됨 


#### 예시

root 본 eyes, head 부착)

<p><img src="http://ko.esotericsoftware.com/img/spine-user-guide/basic-concepts/slots.png"/></p>


슬롯(Slots)
-----------
* 목적: 드로잉 순서 유연성을 위해 존재
* 위치: 스켈레톤 아래 DrawOrder 노드 내
* 기능: 본 계층 구조와 별개로 **슬롯 순서**대로 그려짐

#### 예시

* 본 계층 구조: 엉덩이(hip) 본 → 상체(torso) 본
* 본 슬롯 연결
	* 상체(torso) 본: 배(belly), 셔츠(shirt) 슬롯
	* 엉덩이(hip) 본: 바지(pants) 슬롯
* 드로잉 순서 설정:
	* 바지(pants)아래 배(belly) 드로잉 
	* 바지(pants)위 셔츠(shirt) 드로잉

<p><img src="http://ko.esotericsoftware.com/img/spine-user-guide/basic-concepts/draworder.png"/></p>


#### 활용

* 슬롯 당 여러 개 어태치먼트 보유
	* 한 시점 1개 어태치먼트만 표시 
	* 드로잉 순서 문제로 여러개 어태치먼트 드로잉 불가
* 어태치먼트 그룹 기능 
	* 드로잉 순서 관리 편의 향상
	* 예) 무기 슬롯: 단검, 장검, 도끼 보유 가능



