# 윈도우

## 배치 스크립트

### IPv4 리스트

    > vim ipv4_list.bat
    chcp 1252 > NUL

    set IPV4_KEYWORD="IPv4 Address"
    for /f "usebackq tokens=2 delims=:" %%f in (`ipconfig ^| findstr /c:%IPV4_KEYWORD%`) do echo * ip:%%f

