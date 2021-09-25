---
title: "Unity. C# 딕셔너리(Dictionary) 사용하기"
categories:
  - Unity
tags:
  - 기초
  - Unity
  - C#
---

## 🌟 딕셔너리란?

C#에서 사용할 수 있는 배열로, key와 value 값을 지정해 저장하는 방식이다. 이때 key 값은 중복되면 안된다.



### 선언

```c#
Dictionary<string, int> my_dictionary=new Dictionary<string, int>();
```

딕셔너리는 이런 식으로 선언할 수 있다! 유니티에서 사용하면 변수 타입으로 더 다양한 걸 넣을 수 있다. Sprite 같은 것들! 유용함....



### 초기화

```c#
Dictionary<string, int> my_dictionary = new Dictionary<string, int>()
{
	{ "one",123}, { "two",456},
};
```

이렇게 초기화 할 수도 있고, Add로 추가할 수도 있다.



```c#
my_dictionary.Add("three", 789);
```

리스트랑 비슷함.



## 🌟 사용법

```c#
void Start()
{
    Dictionary<string, int> my_dictionary=new Dictionary<string, int>(); //선언
    my_dictionary.Add("younghyun",123456); //초기화
    my_dictionary.Add("euji",987654);
    
    Debug.Log(my_dictionary["younghyun"]); //123456 출력
    Debug.Log(my_dictionary.ContaninsKey("younghyun")); //key 검색 있다면 true, 없다면 false 반환
    
    my_dictionary.Remove("euji"); //삭제
    my_dictionary.Clear(); //모두 제거
}
```

key 값을 통해 value 값을 찾으려면 `my_dictionary["younghyun"]` 이런 식으로 사용하면 되고, 나머지는 리스트와 비슷하게 사용된다. 

key 값으로 value를 찾는 다른 방법도 있음!



```c#
int number = 0;

if(my_dictionary.TryGetValue("younghyun", out number))
{
    Debug.Log(number); //123456 출력
}
```

`TryGetValue()`를 사용하면 원하는 곳에 value 값을 담을 수 있다!

