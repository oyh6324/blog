---
title: "Unity. 이미지 점점 크게 만들기"
categories:
  - Unity
tags:
  - Unity
  - UGUI
---

## 🌟 localScale

localScale은 부모 오브젝트에 대한 상대적인 크기를 말하며, localScale을 사용하여 이미지의 크기를 스크립트에서 조정할 수 있다. 기본적으로는 `trasform.localScale = new Vector3(1f, 1f,  1f)` 이런 식으로 사용함!

## 🌟 코드

```c#
    private float size = 1f; //원하는 사이즈
    public float speed; //커질 때의 속도

    private float time;
    private Vector2 originScale; //원래 크기

    private void Awake()
    {
        originScale = transform.localScale; //원래 크기 저장
    }
    private void OnEnable()
    {
        StartCoroutine(Up());
    }
    IEnumerator Up()
    {
        while (transform.localScale.x < size)
        {
            transform.localScale = originScale * (1f + time * speed);
            time += Time.deltaTime;

            if (transform.localScale.x >= size)
            {
                time = 0;
                break;
            }
            yield return null;
        }
    }
    private void OnDisable()
    {
        gameObject.transform.localScale = originScale;
    }
```

> <https://wolfy.tistory.com/11>

여기 블로그의 코드를 보고 변형함! 근데 time에 왜 1을 더하는지 모르겠다.  아! 시작할 때 작아지면 안되서?! 아무튼 이걸 커져야 하는 오브젝트에 넣으면 알아서 localScale이 1이 될 때까지 커진다. 게임 만들 때 메시지 창에 쓰면 유용할듯!