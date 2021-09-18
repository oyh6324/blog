---
title: "Unity. Newtonsoft.Json으로 json 파일 저장하고 불러오기"
categories:
  - Unity
tags:
  - Unity
  - 데이터 저장
---

## 🌟 json이란?

데이터를 저장하는 파일의 형식이다. 보통

```c#
[
  {
    "name": "낙엽",
    "number": 10000
  },
  {
    "name": "코인",
    "number": 7000
  },
  {
    "name": "보석",
    "number": 10000
  }
]
```

이런 식으로 생겼다. 많이 사용되기도 하고 관리하기도 편하니 게임 만들 때 자주 쓴다!

## 🌟 Newtonsoft.Json이란?

Newtonsoft.Json은 json을 deserialize하거나 serialize하기 편하게 만든 라이브러리다. JsonUtility라고 유니티에 내장되어 있는 json 라이브러리도 있는데, 쓰기 불편해서 Newtonsoft.Json을 임포트하는 게 나을 것이다. 물론 json 사용할 일이 별로 없다면 그냥 유니티 json을 쓰면 됨!

아무튼 Newtonsoft.Json, 즉, Json.Net을 사용하기 위해서는 아래에 있는 파일을 유니티에 임포트 해야 한다.

> <https://www.newtonsoft.com/json>

파일을 받으면 net20, 35, 40 등등 여러 개의 파일이 있는데 유니티의 최신 기능이 필요하면 net45의 파일을 이용해야 한다. 그리고 이 파일을 이용하면 반드시 유니티에서 .NET 74.x로 설정해줘야 한다! 무슨 프로젝트 셋팅 들어가면 나옴!

## 🌟 저장과 불러오기

```c#
public List<MoneyData> moneyDataList;

void Start()
{
        moneyDataList = new List<MoneyData>();
        //저장할 초기 정보
        moneyDataList.Add(new MoneyData("낙엽",1000));
        moneyDataList.Add(new MoneyData("코인", 1000));
        moneyDataList.Add(new MoneyData("보석", 100));
}

void Save() //json 파일로 저장
{
        string moneyData = JsonConvert.SerializeObject(moneyDataList);
        File.WriteAllText(Application.persistentDataPath + "/MoneyData.json", moneyData);
}

void Load() //json 파일을 List에 넣기
{
        string moneyData = File.ReadAllText(Application.persistentDataPath + "/MoneyData.json");
        moneyDataList = JsonConvert.DeserializeObject<List<MoneyData>>(moneyData);
}

public class MoneyData
{
    public MoneyData(string _name, int _number)
    {
        name = _name; number = _number;
    }
    public string name; //이름
    public int number; //개수
}
```

유니티의 json 라이브러리를 쓰면 코드가 엄청 길어지는데 Json.Net은 간단하게 할 수 있다. 왜냐면 List에 바로 넣을 수 있기 때문! 

게임 재화 같은 짧은 정보는 저렇게 코드로 넣으면 되지만, npc 대사나 아이템 정보 같은 것들은 리소스 파일에 넣어서 텍스트로 저장한 다음 가져오는 편이다.

```c#
        TextAsset questMessageData = Resources.Load("QuestMessageData", typeof(TextAsset)) as TextAsset;
        questMessageDataList = JsonConvert.DeserializeObject<List<QuestMessageData>>(questMessageData.ToString());
```

이렇게!

리소스 파일에 넣는 텍스트 파일은 일단 엑셀로 데이터 테이블을 만들고 json 형태로 convert 해주는 사이트에서 json 형태로 바꿔 txt로 저장한 것이다.

> <http://shancarter.github.io/mr-data-converter/>

여기!! 완전 편함.