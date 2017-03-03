# 언리얼 엔진

## 셋업

### silk_common.lib 링크 에러

#### 재현 환경

* OS: Windows 10 Pro 64bit
* UE: 4.15.0

#### 재현 방법
    
    > Setup.bat -exclude=Win32 

#### 문제 상황

    > LINK : fatal error LNK1181: 'silk_common.lib' 입력 파일을 열 수 없습니다.

#### 문제 원인

`\Engine\Source\ThirdParty\libOpus\opus-1.1\win32` 폴더 내 라이브러리가 존재하지 않음

### 문제 분석

`\Engine\Source\ThirdParty\libOpus\libOpus.build.cs`

    if ((Target.Platform == UnrealTargetPlatform.Win64) ||
        (Target.Platform == UnrealTargetPlatform.Win32))
    {
        LibraryPath += "win32/VS2012/"; // BUG: Win32 제외로 인해 다운로드 되지 않음
        if (Target.Platform == UnrealTargetPlatform.Win64)
        {
            LibraryPath += "x64/";
        }
        else
        {
            LibraryPath += "win32/";
        }

        // ...
    }

#### 문제 해결

Win32 제외 옵션을 사용하지 않음