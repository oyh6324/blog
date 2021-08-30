---
title: "Unity. UI로 메시지(DM) 화면 만들기"
categories:
  - Unity
tags:
  - Unity
  - UGUI
---

## DM 화면

카카오톡이랑 더 유사할 것 같지만 아무튼 메시지 화면을 만들어 봤다. 

![image-center]({{ site.url }}{{ site.baseurl }}/assets/images/unity/unity.makedm1.jpg){: .align-center}
_최종 화면_

상대방 쪽은 프로필 사진 두라고 비워 놓았고, 말풍선도 비워두었음.

## Scroll View

화면 안에 메시지를 보여줄 창은 스크롤 뷰다. UI의 Scroll View를 넣어서 크기를 키우고 Scroll View의 컴포넌트 중 Scroll Rect에서 Horizontal의 체크를 해제한다. 위 아래로만 움직이기 때문!

그리고 뷰 포트 안의 컨텐트에 `Content Size Fitter`와 `Vertical Layout Group` 컴포넌트를 넣어준다.

![image-center]({{ site.url }}{{ site.baseurl }}/assets/images/unity/unity.makedm2.jpg){: .align-center}
_Content의 컴포넌트_

설정은 이렇게!!!!! `Content Size Fitter`는 오브젝트의 사이즈를 자식 사이즈만큼 알아서 늘려주거나 줄여줌. 지금은 Vertical만 조정하도록 했다.

## 상대방 말풍선

우선 빈 오브젝트(leftMessage)를 생성해서 화면의 가로 크기만큼 대충 맞춰 주고, `Content Size Fitter`와 `Horizontal Layout Group` 컴포넌트를 넣어준다.

![image-center]({{ site.url }}{{ site.baseurl }}/assets/images/unity/unity.makedm3.jpg){: .align-center}
_leftMessage의 컴포넌트_

프로필 사진이 들어갈 이미지 하나 넣고 말풍선이 될 이미지와 그 자식에 텍스트를 넣는다.

![image-center]({{ site.url }}{{ site.baseurl }}/assets/images/unity/unity.makedm4.jpg){: .align-center}
_말풍선 이미지의 컴포넌트_

여기서 중요한 건 피벗을 **0과 1**로 맞춰야 한다는 거! 안 그러면 말풍선에 텍스트가 추가될 때마다 이상한 방향으로 자란다 ㅠ ㅠ

말풍선 안의 텍스트도 0과 1로 하면 됨! 그럼 상대방 말풍선은 끝!

## 작성자 말풍선

내 말풍선은 위에서 한 것처럼 빈 오브젝트 하나 만들고 컴포넌트 추가하고 오른쪽으로 정렬하게끔 한 다음에, 바로 말풍선 이미지와 텍스트를 넣으면 된다. 피벗이 1과 1이 되는 거 말고는 다 똑같음! 끝!

leftMessage와 rightMessage를 프리팹으로 만들어서 스크립트로 말을 바꿔가며 복제하면 메시지 창에서 대화하는 듯한 연출을 할 수 있음~!