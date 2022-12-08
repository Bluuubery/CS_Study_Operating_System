# 스레드(Thread)

## 프로세스(Process)와 스레드(Trhead)

![image-20221207150553785](Chatper4.assets/image-20221207150553785.png)

>  제어 부분이 쓰레드, 여러개일 수 있음



## 스레드(Thread)의 개념

![image-20221207150742807](Chatper4.assets/image-20221207150742807.png)

> 프로세스는 제어와 리소스로 나뉨
>
> 제어부분이 Thread, 여러개 존재 가능
>
> 프로세스가 할당 받은 자원은 공유함, 이를 제어하는건 여러개 일 수 있는 거임

![image-20221207150853172](Chatper4.assets/image-20221207150853172.png)

> 각 스레드마다 스택 영역을 가짐
>
> 코드에서 프로그램 카운터로 흐름 제어



* Light Weight Process (LWP)

> 자원은 공유하고 제어부분만 가지고 있으므로

* 프로세서(e.g, CPU) 활용의 기본 단위

> CPU를 활용하는 기본단위가 스레드

* 구성요소
  * Thread ID
  * Register set (PC등)
  * Stack(i.e. local data)
* 제어 요소 외 코드, 데이터 및 자원들은 프로세스의 다른 스레드 들과 공유
* 전통적 프로세스 = 단일 스레드 프로세스



## Single-Thread vs Multi-threads

![image-20221207151123829](Chatper4.assets/image-20221207151123829.png)



## 스레드의 장점

* 사용자 응답성 (Responsiveness)
  * 일부 스레드의 처리가 자연되어도, 다른 스레드는 작업 계속 처리 가능
* 자원 공유 (Resource sharing)
  * 자원을 고유해서 효율성 증가(커널의 개입을 피할 수 있음)
    * 예)동일 address space에서 스레드 여러 개

> 프로세스는 context switch 발생 => 비싼 연산
>
> 스레드면 동시에 사용할 수 있어서 context switch 발생 X

* 경제성 (Economy)
  * 프로세스의 생성, context switch에 비해 효율적
* 멀티 프로세서(multi-processor) 활용
  * 병렬처리를 통해 성능 향상

![image-20221207151413987](Chatper4.assets/image-20221207151413987.png)

> IO 발생하면 run => block으로,
>
> 스레드 하나로만 하면 하나의 작업을 하는 중에 다른 애들을 할 수 없음



![image-20221207151659074](Chatper4.assets/image-20221207151659074.png)



## 스레드(Thread)의 구현

### 사용자 수준 스레드(User Thread)

![image-20221207151812341](Chatper4.assets/image-20221207151812341.png)

![image-20221207151826556](Chatper4.assets/image-20221207151826556.png)

### 커널 수준 스레드 (Kernel Threads)

![image-20221207152047844](Chatper4.assets/image-20221207152047844.png)

![image-20221207152056279](Chatper4.assets/image-20221207152056279.png)

![image-20221207152216865](Chatper4.assets/image-20221207152216865.png)

### Multi-Threading Model

![image-20221207152228616](Chatper4.assets/image-20221207152228616.png)

![image-20221207152247890](Chatper4.assets/image-20221207152247890.png)

> 사용자, 커널 중심 스레드 다 취함

![image-20221207152339918](Chatper4.assets/image-20221207152339918.png)

> 실제로 OS들이 사용하는 모델

