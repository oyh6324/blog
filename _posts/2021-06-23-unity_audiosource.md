---
title: "Unity. 오디오 소스(Audio Source)"
categories:
  - Unity
tags:
  - Unity
  - 기초
---

## Audio Source

유니티에서 소리를 낼 수 있게 하는 컴포넌트 중 하나다. Audio Clip을 사용해서 소리를 재생한다. Audio Clip이 3D인 경우, Audio Source와 멀어질수록 소리가 작아진다.

![2](/assets/images/unity/unity.audiosource.jpg)
_Audio Source Component_

위 사진의 프로퍼티를 조정하여 볼륨이나 오디오 믹서를 정할 수 있다. 오디오 믹서는 다음에!

## 사용법

```c#
    private AudioSource audioSource;
    public AudioClip audioClip;

    void Start()
    {
        audioSource = GetComponent<AudioSource>();
        audioSource.PlayOneShot(audioClip);

        audioSource.clip = audioClip;
        audioSource.Play();
    }
```

`GetComponent`로 오디오 소스를 가져오고, 미리 정해둔 Audio Clip을 재생하는 코드다. 여기서 `PlayOneShot`은 소리가 겹쳐서 나올 수도 있다는 것이고, `Play`는 전의 소리가 나오고 있다면 끊은 뒤 지금 가지고 있는 Audio Clip을 재생하는 함수다.