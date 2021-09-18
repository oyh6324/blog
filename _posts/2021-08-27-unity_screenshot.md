---
title: "Unity. 화면 캡쳐하기(ScreenShot)"
categories:
  - Unity
tags:
  - 중급
  - Unity
  - C#
---

## 🌟 ScreenCapture.CaptureScreenshot()

유니티 내부에는 화면을 캡쳐하는 함수가 따로 있다. `ScreenCapture.CaptureScreenshot(저장할 파일 이름)`을 하면 알아서 프로젝트 폴더에 저장이 된다. 모바일을 Application.persistentDataPath! 하지만 잘 안될 때가 많아 이 함수 대신 다른 방법을 쓰기도 한다.

## 🌟 다른 방법

```c#
    void SaveScreenPGN(string filePath) //로컬 저장소에 저장
    {
        Texture2D texture = new Texture2D(Screen.width, Screen.height, TextureFormat.RGB24, false);
        texture.ReadPixels(new Rect(0, 0, Screen.width, Screen.height), 0, 0);
        texture.Apply();
        byte[] bytes = texture.EncodeToPNG();
        File.WriteAllBytes(filePath, bytes);
        Destroy(texture);
    }
```

텍스쳐를 사용해서 저장하는 방법이다. ScreenCapture.CaptureScreenshot()는 유니티에서 사용하면 프로젝트 폴더 안에 저장되지만, 이렇게 텍스쳐를 사용해서 저장하면 경로도 바꿀 수 있다.
