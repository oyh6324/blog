---
title: "Unity. PlayerPrefs로 간단한 데이터 저장하기"
categories:
  - Unity
tags:
  - Unity
  - 데이터 저장
---

## 🌟 PlayerPrefs란?

유니티에서 제공하는 데이터 관리 클래스다. 방대한 정보는 저장할 수 없지만, 간단한 정보는 아주 쉽게 저장할 수 있다.

## 🌟 사용법

```c#
void Start()
{
        PlayerPrefs.SetInt("오늘 날짜", 0831); //int 형식의 데이터 저장
        PlayerPrefs.SetFloat("사용자 키", 167.8f); //float 형식의 데이터 저장
        PlayerPrefs.SetString("사용자 이름", "영현"); //string 형식의 데이터 저장


        int date = PlayerPrefs.GetInt("오늘 날짜"); //원하는 데이터 불러오기

        PlayerPrefs.Save(); //모든 데이터 저장
        PlayerPrefs.DeleteKey("오늘 날짜"); //원하는 데이터 삭제
        PlayerPrefs.DeleteAll(); //모든 데이터 삭제
}
```

PlayerPrefs는 key 값과 value 값을 동시에 지정해줘야 하며, 언제든지 저장된 정보를 불러올 수 있다. PlayerPrefs로 저장한 데이터는 프로그램을 꺼도 남아있음!