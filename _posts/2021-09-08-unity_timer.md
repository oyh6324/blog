---
title: "Unity. 타이머, 스톱워치 만들기"
categories:
  - Unity
tags:
  - Unity
  - 중급
---

## 🌟 유니티에서 초 세기

원하는 시간을 지정하고 초를 세는 스크립트를 짜 보았다!

## 🌟 코드

```c#
 private float time=21600f; //6시간을 초로 분해

 private void Update()
    {
        if (isCounting) //카운트다운 시작
        {
            time -= Time.deltaTime; //1초씩 깎임
            SetTimeText();
        }
    }
    private void SetTimeText()
    {
        int hou = ((int)time / 60) / 60; //시간
        int min = ((int)time / 60)%60; //분
        int sec = (int)time % 60; //초

        if (hou > 0)
            timeTx.text = hou + "h "+min + "m "+ sec + "s";
        else if (min > 0)
            timeTx.text = min + "m " + sec + "s";
        else if (sec >= 0)
            timeTx.text = sec + "s";

        if (time <= 0)
        {
            timeTx.text = "시간이 다 됐습니다.";
        }
    }
```

원하는 시간을 입력하고 출력할 timeTx를 미리 만들어 두면 끝! 잘 나온다.