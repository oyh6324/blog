---
title: "Unity. Handles.DrawSolidArc로 호 그리기"
categories:
  - Unity
tags:
  - 중급
  - Unity
---

## 🌟 Handles.DrawSolidArc()

Handles는 그림을 그리는 함수가 들어 있는 클래스다. 기즈모와 비슷함!

## 🌟 사용법

```c#
using UnityEngine;
using UnityEditor;

[CustomEditor( typeof( DrawSolidArc ) )]
public class DrawSolidArcEditor : Editor
{
	public float arrowSize = 1;

	void OnSceneGUI( )
	{
		DrawSolidArc t = target as DrawSolidArc;

		Handles.color = Color.blue;
		Handles.Label( t.transform.position + Vector3.up * 2,
							 t.transform.position.ToString( ) + "\nShieldArea: " +
							 t.shieldArea.ToString( ) );

		Handles.BeginGUI( );
		GUILayout.BeginArea( new Rect( Screen.width - 100, Screen.height - 80, 90, 50 ) );

		if( GUILayout.Button( "Reset Area" ) )
			t.shieldArea = 5;

		GUILayout.EndArea( );
		Handles.EndGUI( );

		Handles.color = new Color( 1, 1, 1, 0.2f );
		Handles.DrawSolidArc( t.transform.position, t.transform.up, -t.transform.right,
								180, t.shieldArea );

		Handles.color = Color.white;
		t.shieldArea = Handles.ScaleValueHandle( t.shieldArea,
						t.transform.position + t.transform.forward * t.shieldArea,
						t.transform.rotation, 1, Handles.ConeCap, 1 );
	}
}
```

유니티 공식 문서에서 들고 왔다. 아래에서 세 번째 줄이 호를 그리고 있다. 인자는 **원형의 중심**, **원형의 종류**(어느 축을 기준으로 회전할 것인지), **부채꼴의 시작점**, **몇 도만큼 회전하는지**, **반지름**이다.

몬스터의 시야를 만들 때 유용할듯.