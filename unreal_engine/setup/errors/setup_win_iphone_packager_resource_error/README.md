# 언리얼 엔진

## 셋업

### iPhonePackager Resources.resx 에러

#### 재현 환경

* OS: Windows 10 Pro 64bit
* UE: 4.15.0

#### 재현 방법
    
    > Setup.bat -exclude=IOS

#### 문제 상황

    > \Engine\Source\Programs\IOS\iPhonePackager\Properties\Resources.resx(123,5): error MSB3103: Resx 파일이 잘못되었습니다. '\Engine\Source\Programs\IOS\iPhonePackager\Resources\GreyCheck.png' 파일을 찾을 수 없습니다. 줄 123, 위치 5


#### 문제 원인

`\Engine\Source\Programs\IOS\iPhonePackager\Resources` 폴더 내 GreyCheck.png 파일이 존재하지 않음

#### 문제 해결

IOS 제외 옵션을 사용하지 않음