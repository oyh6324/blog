---
title: "Java.InputStream과 OutputStream 알아보기"
categories:
  - Java
tags:
  - Java
  - 기초
  - 프로그래밍 언어
---



## 🌟 InputStream이란?

바이트 단위로 데이터를 읽고, 키보드에서 입력한 값을 읽는다.



### 사용법

```java
public void read() throw IOException{
    byte[] bytes = {1, 2, 3};
    InputStream is = new ByteArrayInputStream(bytes);
    int data;
    while((data = is.read())!= -1){
        System.out.print(data);
    }
}
```

바이트를 모두 읽으면 -1을 출력함!



## 🌟 OutputStream이란?

바이트 기반의 출력 스트림이다.



### 사용법

```java
public void write() throws IOException{
            byte[] bytes = {9, 8, 7, 6, 5, 4, 3, 2, 1, 0};

        File file = new File("D://write_test.txt");
        OutputStream outputStream = new FileOutputStream(file);

        for (byte b : bytes) {
            outputStream.write(b);
        }
        
        //바이트를 한번에 넣을 수 있다.  
        //outputStream.write(bytes);
        
        outputStream.close();
}
```



___

{: .primary--notice}

참고 https://bamdule.tistory.com/179
