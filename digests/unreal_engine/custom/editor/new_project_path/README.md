# 언리얼 엔진

## 커스텀

### 새로운 프로젝트 경로

#### 목적

새로운 프로젝트 기본 생성 경로를  `C:\Users\계정\Docuemtns\Unreal Projects` 대신 `C:\UnrealProjects` 로 변경

#### 분석

##### 콜스택

 	UE4Editor-DesktopPlatform.dll!FDesktopPlatformBase::GetDefaultProjectCreationPath() 줄 842	C++
 	UE4Editor-GameProjectGeneration.dll!SNewProjectWizard::SetDefaultProjectLocation() 줄 1306	C++
	UE4Editor-GameProjectGeneration.dll!SNewProjectWizard::Construct(const SNewProjectWizard::FArguments & InArgs) 줄 319	C++
 	UE4Editor-GameProjectGeneration.dll!TDecl<SNewProjectWizard,RequiredArgs::T0RequiredArgs>::operator<<=(const SNewProjectWizard::FArguments & InArgs) 줄 1087	C++
 	UE4Editor-GameProjectGeneration.dll!SGameProjectDialog::Construct(const SGameProjectDialog::FArguments & InArgs) 줄 34	C++
 	UE4Editor-GameProjectGeneration.dll!TDecl<SGameProjectDialog,RequiredArgs::T0RequiredArgs>::operator<<=(const SGameProjectDialog::FArguments & InArgs) 줄 1087	C++
 	UE4Editor-GameProjectGeneration.dll!FGameProjectGenerationModule::CreateGameProjectDialog(bool bAllowProjectOpening, bool bAllowProjectCreate) 줄 53	C++
 	UE4Editor-MainFrame.dll!FMainFrameModule::CreateDefaultMainFrame(const bool bStartImmersive, const bool bStartPIE) 줄 134	C++
 	UE4Editor-UnrealEd.dll!EditorInit(IEngineLoop & EngineLoop) 줄 124	C++

##### 소스 

    FString FDesktopPlatformBase::GetDefaultProjectCreationPath()
    {
        // My Documents
        const FString DefaultProjectSubFolder = TEXT("Unreal Projects");
        return FString(FPlatformProcess::UserDir()) + DefaultProjectSubFolder;
    }