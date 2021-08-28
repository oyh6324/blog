---
title: "Unity. C# 원하는 파일 유형의 경로 가져오기"
categories:
  - Unity
tags:
  - 기초
  - Unity
  - C#
---

## Directory.GetFiles()

C#의 Directory.GetFiles(경로, 파일 확장자) 함수를 사용하면 원하는 경로에 있는 파일을 모두 가져올 수 있다. using System.IO를 추가해야 함!

## 사용법

```c#
void Start()
{
        string path = Application.persistentDataPath + "/";
        string[] filePaths = Directory.GetFiles(path, "*.jpg");
}
```

이렇게 하면 `Application.persistentDataPath` 경로에 있는 모든 jpg 유형의 파일이 filePaths 배열에 들어갈 것이다.