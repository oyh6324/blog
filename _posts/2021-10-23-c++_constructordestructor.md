---
title: "C++. Class의 생정자와 소멸자 알아보기"
categories:
  - C++
tags:
  - C++
  - 프로그래밍 언어
  - 기초
---

## 🌟 생성자란?

생성자는 어떤 클래스를 이용해서 객체를 생성할 때, 자동으로 호출되는 메소드다. 객체의 멤버 변수를 초기화할 때 유용하다. 



{: .notice--primary}
생성자를 만들지 않으면 자동으로 기본 생성자가 만들어진다!



### 사용법

```c++
#include <iostream>
#include <string>
using namespace std;

class CStudent
{
private:
    string name;
    int number;
    
public:
    CStudent(string name, int number){ //생성자
        this->name = name;
        this->number = number;
    }
};

int main()
{
    CStudent student = CStudent("영현", 1010);
    return 0;
}
```

생성자는 `클래스명() {}`이렇게 사용하고, 안에는 클래스가 생성될 때 사용하고 싶은 코드를 작성하면 된다. 위 코드는 클래스의 멤버 변수를 초기화하는 코드를 작성했다. 그리고 메인에서 원하는 데이터로 생성하면 끝!



## 🌟 소멸자란?

소멸자는 어떤 클래스를 이용해서 생성한 객체가 메모리에서 해제될 때, 자동으로 호출되는 메소드다. 객체를 사용하고 나서 마무리 작업할 때 유용하다.



### 사용법

```c++
class CStudent
{
private:
    string name;
    int number;
    
public:
    CStudent(string name, int number){ //생성자
        this->name = name;
        this->number = number;
    }
    ~CStudent(){ //소멸자
        cout << "소멸";
    }
};
```

이렇게 해두면 나중에 객체가 메모리에서 사라질 때 소멸자가 호출되어 텍스트를 출력할 것이다. 소멸자 역시 클래스명과 동일하게 사용해야 한다. 앞에는 꼭 '~'를 붙이고!