---
title: "Unity. 코루틴을 사용한 페이드 인/아웃"
categories:
  - Unity
tags:
  - Unity
  - 중급
---

## 🌟 Fade In/Out

페이드 인은 검은 화면이 투명하게 변하면서 원래의 화면이 보이는 것을 말하고, 페이드 아웃은 원래의 화면에서 검은 화면으로 바뀌는 것을 말한다.

## 🌟 코루틴을 사용한 Fade In/Out

```c#
public class FadeIO : MonoBehaviour
{
    public Image fadeImg; // fade에 쓸 이미지
    public float fadeTime; //화면이 변할 시간
    public bool fadeout;
    public bool fadein;

    private bool isPlaying = false;

    private void Start()
    {
        fadein = true; //스크립트가 활성화된 경우, 페이드인 시킴. 이 부분은 원하면 생략
    }
    private void Update()
    {
        if (fadeout == true && isPlaying == false) //페이드아웃을 원할 때
        {
            StartCoroutine(FadeOut());
        }
        else if (fadeout == false && fadein == true) //페이드인을 원할 때
        {
            StartCoroutine(FadeIn());
        }
    }
    IEnumerator FadeOut()
    {
        fadeImg.gameObject.SetActive(true);
        isPlaying = true;
        Color tempColor = fadeImg.color;
        tempColor.a = 0f;
        while (tempColor.a < 1f)
        {
            tempColor.a += Time.deltaTime / fadeTime;
            fadeImg.color = tempColor;

            if (tempColor.a >= 1f)
            {
                tempColor.a = 1f;
            }
            yield return null;
        }
        fadeout = false;
    }
    IEnumerator FadeIn()
    {
        Color tempColor = fadeImg.color;
        while (tempColor.a > 0f)
        {
            tempColor.a -= Time.deltaTime / fadeTime;
            fadeImg.color = tempColor;

            if (tempColor.a <= 0f)
            {
                tempColor.a = 0f;
                fadeImg.color = tempColor;
            }
            yield return null;
        }
        fadeImg.gameObject.SetActive(false);
        fadein = false;
        isPlaying = false;
    }
}

```

페이드아웃을 시키고 페이드인 하는 경우가 많아서 isPlaying을 페이드인에서 false 했지만, 그렇지 않다면 페이드아웃에도 false 해야 한다. fadein과 fadeout bool 함수는 다른 객체에서 접근해서 사용할 수 있도록 public으로 지정했다.