OmniSharpSublime + Unity
========================

OmniSharpSublime 은 **C#** 코드 관리를 위해 만들어진 **OS X** 용 **mono** 기반 Sublime Text **3** 플러그인입니다.


OS X
----

#### 환경 준비

* Sublime Text 3 <http://www.sublimetext.com/3>
* Sublime Package Control <https://packagecontrol.io/> 
* Unity3D  <http://unity3d.com/unity/download>

#### 플러그인 설치

* Package Control 오픈 (단축키: cmd + shift + p)
* Package Control: Install Package 검색
* OmniSharpSublime 선택

#### 유니티 설정

* 메인 메뉴 Unity > Preferences... 클릭
* Unity Preferences 다이얼로그 사이드 바 > External Tools 선택 
* External Script Editor 버튼 클릭: 응용 프로그램 > Sublime Text 선택

#### 유니티 프로젝트 연결

* 메인 메뉴 Assets > Sync MonoDevelop Project 클릭
* Sublime Text 메인 메뉴 Project > Save Project As ... > 새로운 프로젝트 저장
* Sublime Text 메인 메뉴 Project > Edit Project 클릭

    {
        "solution_file": "./유니티_솔류션.sln",
        "folders":
        [
            {
                "name": "유니티_솔류션",
                "path": ".",
                "file_exclude_patterns":
                [
                    "*.meta"
                ]
            }
        ],
        "settings":
        {
            "auto_complete_triggers": [
                {
                    "characters": ".", 
                    "selector": "source.cs"
                }
            ]
        }
    }


FAQ
---

#### 문제 확인 방법

콘솔창(메인 메뉴 View > Show Console, 단축키: ctrl + `)을 통해 로그를 확인 할 수 있습니다.


