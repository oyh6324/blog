---
title: "Unity. 타이핑 효과 구현하기"
categories:
  - Unity
tags:
  - 중급
  - Unity
---

```c#
public Text dialTx; //텍스트를 출력하는곳
public float typing_speed; //타이핑 속도

string[] texts; //출력할 문자열
bool isTyping;
int textNum; //현재 출력하는 텍스트 인덱스
void Start()
{
	texts = new string[] {"타이핑 테스트", "한 글자씩 출력하기", "클릭하면 타이핑 효과 종료"};
	StartCoroutine(typing(texts[0]));
}

IEnumerator typing(string message) //말풍선 text 타이핑 모션 구현
{
	isTyping = true; //타이핑 중
	for(int i=0; i< message.Length; i++) 
	{
		if (message.Length == i + 1 || isTyping == false) //string이 모두 구현됐거나 타이핑을 끝낼 때
		{
			isTyping = false; //타이핑 종료
                		break;
		}
	dialTx.text = message.Substring(0, i + 1); //한 글자씩 말풍선 text에 추가
	yield return new WaitForSeconds(typing_speed); //타이핑 속도 기다림
	}
}

public void BtClick() //텍스트 창 버튼 클릭
{
	if (isTyping) //text가 타이핑 중이라면
	{
		isTyping = false; //타이밍 끝냄
		dialTx.text = tutorials[textNum]; //해당 텍스트 string 출력
	}
	else //타이핑 중이 아니라면
	{
		//다음 텍스트로 넘어감
		textNum++;
		StartCoroutine(typing(tutorials[textNum]));
	}
}
```

보통 타이핑을 구현할 때 넘어가기 버튼을 누르면 타이핑하던 문자열이 한 번에 출력되곤 한다. BtClick은 그걸 구현한 것! 타이핑하고 있는 창을 버튼으로 만들고, 그 창을 클릭하면 비주얼노벨이나 뭐 그런 거처럼 한 번에 출력될 것이다!