CAP'N PROTO
===========

소개
----

* 매우 빠른 데이터 교환 포멧
* 인코딩-디코딩 시간 없음
* 메모리 그대로 사용
* 플랫폼 독립적
* 모던 CPU 친화적 (리틀 엔디안 사용)
* 새로운 필드 구조체 끝 추가 (기존 필드 위치 변화 없음)
* 간단한 공간 절약 기능 제공 (일반 압축 써도 무방)
* 안전한 메시지 접근 클래스 생성
* 점진적 읽기
* 전체 파싱 없이 임의 필드 읽기 가능
* 메모리 맵 지원
* 다른 언어간 통신 지원
* 커널 통하지 않고 프로세스간 통신 지원
* 아레나(리전) 메모리 할당
* 매우 작은 생성 코드
* 매우 작은 런타임 라입
* 시간 여행 RPC

설치
----

### 윈도우

#### 도구 설치
* 다운로드 <https://capnproto.org/capnproto-c++-win32-0.5.3.zip>
* 압축 해제
 * 경로: `C:/Tools`
 * 목록: `capnp.exe, capnpcc-c++.exe, capnpc-capnp.exe`
* 환경 변수 PATH 연동 (귀찮으면 C:\Windows 로 복사)

#### 소스 준비
* 다운로드 <https://capnproto.org/capnproto-c++-0.5.3.tar.gz>
* 압축 해제: `C:/Projects/capnproto-c++-0.5.3`

#### 솔류션 준비
* CMake 설치 <https://cmake.org/>
* CMake 실행
 * Where is the source code: `C:/Projects/capnproto-c++-0.5.3`
 * Where to build the binaries: `C:/Projects/capnproto-c++-0.5.3/__build`
 * Configure 버튼 클릭
* CMake 설정
 * BIN_INSTALL_DIR: `C:/Libraries/x86/Cap'n Proto/bin`
 * BUILD_TESTING: [ ] 체크 해제
 * BUILD_TOOLS: [ ] 체크 해제
 * CAPNPC_CXX_EXECUTABLE: `C:/Tools/capnpc-c++.exe` 자동 설정
 * CAPNP_EXECUTABLE: `C:/Tools/capnp.exe` 자동 설정
 * CAPNP_INCLUDE_DIRS: `C:/Projects/capnproto-c++-0.5.3/src`
 * CAPNP_LITE: [v] 체크 필요
 * CMAKE_CONFIGURATION_TYPES: `Debug;Release;MinSizeRel;RelWithDebugInfo` 기본 설정
 * CMAKE_INSTALL_PREFIX: `C:/Libraries/x86/Cap'n Proto`
 * EXEC_INSTALL_PREFIX: `C:/Libraries/x86/Cap'n Proto`
 * EXTERNAL_CAPNP: [v] 체크 필요
 * INCLUDE_INSTALL_DIR: `C:/Libraries/x86/Cap'n Proto/include`
 * LIB_INSTALL_DIR: `C:/Libraries/x86/Cap'n Proto/lib`
 * Generate 버튼 클릭
