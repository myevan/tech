이미지 (Images)
======================
<http://ko.esotericsoftware.com/spine-images>

* 스켈레톤: 본 연결 이미지 조합 	
	* 스파인은 이미지 편집 기능은 제공하지 않음
	* 이미지 편집 도구로 파츠 이미지 생성
	* 각 파츠의 독립적인 움직임을 위해 이미지 파일 분리 필요
* 스파인 이미지 배치 방법
	* 자동 배치: 이미지 편집 도구 플러그인 <http://ko.esotericsoftware.com/spine-images#Photoshop>
	* 수동 배치
* 어태치먼트: 
	* 이미지 배치 단위. 
	* 예) 리전 어태치먼트(region attachments): 본에 부착되는 사각형 이미지  <http://ko.esotericsoftware.com/spine-regions>


이미지 노드 (Images node)
----------------------

* 위치: 트리 뷰 
* 기능: 스켈레톤 사용 이미지 검색 경로 설정
 
#### 경로  
	
* 경로 종류
	* 상대 경로 (프로젝트 파일 기준) 
	* 절대 경로
* 설정  방법
	* Browse 버튼: 이미지 폴더 선택 다이얼로그 오픈
	* Path 직접 입력 후 엔터
* 이미지 노드 아래 이미지 리스트 표시 (파일 변경 발생시 즉시 반영됨)


#### 배치 

슬롯&어태치먼트 생성

* 싱글 생성: 트리 내 이미지를 에디터 영역에 드래그
* 멀티 생성: 여러 이미지 범위 단축키(shift)나 개별 단축키(win:ctrl, mac:cmd)로 선택 후 에디터 영역에  드래그
* 트리 뷰 생성: 트리 뷰 이미지 선택 후 
	* 트리 내 본이나 슬롯에 드래그
	* 트리 뷰 하단 SetParent 버튼 클릭나 단축키(P) 누름 → 에디터 영역에서  본 클릭 하거나 트리 뷰 본 슬롯 클릭 (본이 많을 경우 에디터 영역 본 클릭이 더 쉬움)

#### 상태

* 이미지 아이콘
	* 적색: 부착 되지 않음
	* 녹색: 부착 되어 있음

#### 조립

* 트랜스폼 도구: 리전 어태치먼트 생성 완료 후 스케일, 회전, 위치 조절
* Create 도구: 본 생성 후 어태치먼트 이동 <http://ko.esotericsoftware.com/spine-tools>


#### 이미지 검색 (Image file lookup)

* Images 노드 정의 경로에 어태치먼트 이름 조합
	* 기본 어태치먼트 이름: 이미지 파일 이름 (파일 확장자 제외) 
	* 지원 이미지 포멧: .png, .jpg, .jpeg
	* 운영체제 대소문자 구분 특성 따름
* Path 명시: 어태치먼트 이름 대신 사용
* 슬롯당 어태치먼트 이름 중복 불가 (다른 이름, 같은 경로 가능)
* 절대 경로와 상대 경로( 프로젝트 파일 기준) 사용 가능


드로우 오더 (DrawOrder)
--------------------

* 위치: 트리 뷰
* 표시: DrawOrder 노드 리스트

#### 우선순위 

* 리스트 위쪽이 높음 (아래에서 위 순서 그려짐)
* 드로우 오더 변경
	* 마우스: 슬롯 드래그
	* 키보드: 
		* 1단계 조절 단축키('+' or '-') 
		* 5단계 조절 단축키(shift + ('+' or '-))

<p><img src="http://ko.esotericsoftware.com/img/spine-user-guide/images/draworder1.png"/><p>
<p><img src="http://ko.esotericsoftware.com/img/spine-user-guide/images/draworder2.png"/><p>


#### 트리 필터

* 위치: 트리뷰 왼쪽 상단
* 목적: 편한 드로잉 오더 작업 가능(본과 어태치먼트를 감춤 → 슬롯만 표시됨)


<p><img src="http://ko.esotericsoftware.com/img/spine-user-guide/images/filter.png"/></p>

* 에디터 영역 어태치먼트 선택시 트리뷰에서도 선택됨
* 어태치먼트가 없어 트리가 필터링된 경우 어태치먼트가 장착될 슬롯이 선택됨


플러그인
-------

#### 포토샵

* 기능
	* 파츠 이미지 저장 및 배치 데이터 출력 
	* 스파인 임포트 가능 (스켈레톤 셋업 시간 절약 가능)
* 위치
	* 스파인 설치 폴더 내 scripts 폴더에서 복사
	* 최신 버전 다운로드 <https://gist.github.com/NathanSweet/c8e2f6e1d79dedd56e8c>

<p><img src="http://ko.esotericsoftware.com/img/spine-user-guide/images/photoshop.png"/></p>


* 절차
	* PSD(or Gimp) 파츠별 레이어 분리
	* 익스포터 실행: 레이어별 이미지 및 배치 데이터 JSON 저장
	* 스파인 로고  메뉴 Import Data 로 JSON 임포트 <http://ko.esotericsoftware.com/spine-import>
	* 루트 보에 모든 이미지가 연결된 스켈레톤 생성 (포토샵 레이어 위치 및 드로잉 순서 유지됨)
	* 본 생성: Create 도구
* 옵션 
	* Write layers as PNGs: 각 레이어 이미지 저장
	* Write a template PNG: 템플릿 용 조립 스켈레톤 이미지 저장
	* Write Spine JSON: 스파인 정보 저장
	* Ignore hidden layers: 숨겨진 그룹과 레이어 제외
	* Use groups as skins: 그룹 별 스킨 생성 & 스킨 별 이미지 서브폴더 저장 
	* Use ruler position as 0, 0: 임포트시 포토샵 룰러 위치를 월드 중심에 맞춤
	* PNG scale: 고해상도 원본 이미지 축소 저장
	* Padding: 이미지 사이 알파 간섭 방지 간격
	* Image Output Directory: 이미지 저장 폴더 
	* JSON Output Directory: JSON 저장 폴더 (빈 상태 유지나 스파인 프로젝트와 같은 경로 추천. 이외의 경우 후처리 필요) 
	
#### 일러스트레이터

* 간단한 레이어 PNG 익스포트 가능 
* JSON 익스포트 불가
* PSD 익스포트 후 포토샵 작업 추천 (File > Export > PSD)

#### 김프

* 레이어 PNG과 JSON 익스포트 가능 
* 스크립트 안정성 문제로 역시 포토샵 작업 추천


