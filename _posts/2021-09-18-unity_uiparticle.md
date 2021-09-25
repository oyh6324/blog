---
title: "Unity. UI 위에 파티클(Particle) 보여주기"
categories:
  - Unity
tags:
  - Unity
  - UGUI
  - Particle
---

## 🌟 Particle

파티클 시스템은 여러 개의 이미지를 생성해서 액체나 구름, 불꽃 같은 애니메이션으로 만들 수 있는 컴포넌트다. 파티클은 아주 유용하게 사용할 수 있는데 UGUI를 사용하면 그 위에 뿌려지지 않는 단점이 있다. 이때 UI 위에 뿌려볼 수 있도록 꼼수 ?! 를 부려야 함.

## 🌟 Canvas 설정

![image-center]({{ site.url }}{{ site.baseurl }}/assets/images/unity/unity.uiparticle1.jpg){: .align-center} _Canvas 설정_

우선 캔버스 설정을 저렇게 바꿔야 한다. Render Mode가 `Screen Space - Overlay` 상태라면 죽어도 파티클이 위에 올라오지 않기 때문에 카메라로 바꾸고, 랜더링할 카메라를 가져다 놓는다. 나는 메인 카메라를 두었음! 

그리고 적절한 Sorting Layer를 설정해준다. 

## 🌟 Particle 설정

![image-center]({{ site.url }}{{ site.baseurl }}/assets/images/unity/unity.uiparticle2.jpg){: .align-center} _Particle 설정_

그리고 UI 위에 뿌리고 싶은 파티클 시스템에 들어가서 Renderer 설정에서 파란색 부분, `Sorting Layer ID`를 UI의 레이어보다 높은 것으로 설정하면 이제 파티클이 UI 위에 뿌려질 것이다.

>  ☝ **<u>잠깐!</u>** 
>
> 파티클 시스템을 생성할 때 캔버스 아래에서 생성하면 이상하게 작게 나온다. 왜 그럴까? 원래 그런가? ㅠㅠ 레이어로 위에 뿌릴 수 있으니까 캔버스 아래에 생성하지 말자!



간단!