---
title: "Java. 파일 입출력 알아보기"
categories:
  - Java
tags:
  - Java
  - 기초
  - 프로그래밍 언어
  - 파일 입출력 함수
---



## 🌟 텍스트 파일 저장

```java

import java.io.BufferedOutputStream;
import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.io.IOException;
import java.io.OutputStream;

public class Main {
    public static void main(String[] args) throws IOException {
		BufferedOutputStream bs = null;
		try {
			bs = new BufferedOutputStream(new FileOutputStream("경로/test.txt"));
			String str ="오늘 날씨는 아주 좋습니다.";
			bs.write(str.getBytes());

		} catch (Exception e) {
                e.getStackTrace();
		}finally {
		bs.close();
		} 
    }
}
```



## 🌟 텍스트 파일 불러오기

```java
import java.io.BufferedInputStream;
import java.io.FileInputStream;
import java.io.IOException;

public class InputStreamEx {
    public static void main(String[] args) throws IOException {
	 try {
	        String filePath = "경로/test.txt";
	        FileInputStream fileStream = null;
	        
	        fileStream = new FileInputStream( filePath );
	        byte[ ] readBuffer = new byte[fileStream.available()];
	        while (fileStream.read( readBuffer ) != -1){}
	        System.out.println(new String(readBuffer));

	        fileStream.close();
	    } catch (Exception e) {
		e.getStackTrace();
	    }
    }
}
```

___

> 참고 블로그 [코딩팩토리](https://coding-factory.tistory.com/282)
