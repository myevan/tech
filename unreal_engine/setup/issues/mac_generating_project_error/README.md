# 언리얼 엔진

## 셋업

### 맥 프로젝트 생성 스크립트 실행 에러

#### 재현 환경

* OS: OS X sierra 
* UE: 4.15.0

#### 재현 방법
    
    $ ./GenerateProject.command

#### 문제 상황

	An error occurred while trying to generate project files.


	Running Mono...

	Setting up Mono
	/Users/Shared/UnrealEngine/4.14/Engine /Users/Shared/UnrealEngine/4.14/Engine/Binaries/Mac
	Discovering modules, targets and source code for project...
	Compiling with non-standard Xcode (xcode-select): /Library/Developer/CommandLineTools/
	Triggered an exception while looking for SDK directory in Xcode.app
	System.IO.DirectoryNotFoundException: Directory '/Library/Developer/CommandLineTools/Platforms/MacOSX.platform/Developer/SDKs' not found.
	  at System.IO.Directory.ValidateDirectoryListing (System.String path, System.String searchPattern, System.Boolean& stop) [0x00000] in <filename unknown>:0 
	  at System.IO.Directory.GetFileSystemEntries (System.String path, System.String searchPattern, FileAttributes mask, FileAttributes attrs) [0x00000] in <filename unknown>:0 
	  at System.IO.Directory.GetDirectories (System.String path, System.String searchPattern) [0x00000] in <filename unknown>:0 
	  at System.IO.Directory.GetDirectories (System.String path) [0x00000] in <filename unknown>:0 
	  at UnrealBuildTool.AppleToolChain.SelectSDK (System.String BaseSDKDir, System.String OSPrefix, System.String& PlatformSDKVersion, Boolean bVerbose) [0x00000] in <filename unknown>:0 
	ERROR: Invalid SDK MacOSX.sdk, not found in /Library/Developer/CommandLineTools/Platforms/MacOSX.platform/Developer/SDKs


#### 문제 원인

Xcode SDK 를 설치 하지 않음
