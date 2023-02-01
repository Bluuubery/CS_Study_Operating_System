# 입출력 시스템 & 디스크 관리

## I/O System (HW)

![image-20230202000432577](Chapter12.assets/image-20230202000432577.png)

I/O : 프로세서가 필요한 정보 요청하면 데이터 읽어오거나 내 보내는 것

결국 필요한 데이터는 메인 메모리에 저장 되어야함

## I/O Mechanisms

![image-20230202000606827](Chapter12.assets/image-20230202000606827.png)

![image-20230202000617243](Chapter12.assets/image-20230202000617243.png)

CPU가 제어하는 메모리 접근 방법 2가지

프로세서가 제어하는 것 / 아닌것



## Polling (Programmed I/O)

![image-20230202000728885](Chapter12.assets/image-20230202000728885.png)

Polling : 프로세서가 주기적으로 I/O 장치 상태 확인하고 순환하면서 물어보는 방식(Processor가 controll)

키보스, 마우스 입력은 자주 받으므로 이게 좋음

but 계속 돌고 있어야 하니깐 overhead

## Interrupt

![image-20230202000931747](Chapter12.assets/image-20230202000931747.png)

계속 찌르면 프로세서는 Interrupt handling overhead 커지는 단점

## Interrupt

![image-20230202001127365](Chapter12.assets/image-20230202001127365.png)

## Direct Memory Access(DMA)

![image-20230202001217003](Chapter12.assets/image-20230202001217003.png)

보낼 때 마다 프로세서가 계속 보고 있어야함 => 오버헤드 큼

=> 프로세서는 명령만 내려 놓고 자기 일 하면 된다!

=> DMA

![image-20230202001414370](Chapter12.assets/image-20230202001414370.png)



## I/O Services of OS

OS가 어떤 support를 할 수 있을까?

![image-20230202001654067](Chapter12.assets/image-20230202001654067.png)

커널 입출력 서브시스템 : I/O service 제공!

![image-20230202001717386](Chapter12.assets/image-20230202001717386.png)

![image-20230202001937611](Chapter12.assets/image-20230202001937611.png)

![image-20230202002236332](Chapter12.assets/image-20230202002236332.png)

OS가 I/O를 위해 많은일 하고 있구나~



## Disk Scheduling

![image-20230202012002647](Chapter12.assets/image-20230202012002647.png)

성능이란게 모호하기 때문에 평가 기준 필요

![image-20230202012127065](Chapter12.assets/image-20230202012127065.png)

![image-20230202012321286](Chapter12.assets/image-20230202012321286.png)

## First Come First Service(FCFS)

![image-20230202012420494](Chapter12.assets/image-20230202012420494.png)

![image-20230202012449909](Chapter12.assets/image-20230202012449909.png)

![image-20230202012540797](Chapter12.assets/image-20230202012540797.png)

Total seek distance = 690



## Shortest Seek Time First(SSTF)

![image-20230202012609390](Chapter12.assets/image-20230202012609390.png)

멀리 있는 애가 언제 서비스 받을 수 있는지 모름 predictability

![image-20230202012725477](Chapter12.assets/image-20230202012725477.png)

total seek distance = 300


## Scan Scheduling

![image-20230202012810420](Chapter12.assets/image-20230202012810420.png)

![image-20230202012916853](Chapter12.assets/image-20230202012916853.png)

TSD = 300

효율 적이지만 starvation X



## C-Scan Scheduling

![image-20230202012951341](Chapter12.assets/image-20230202012951341.png)

![image-20230202013023932](Chapter12.assets/image-20230202013023932.png)

TSD = 490

횡단 한번해서 비효율적인 면도 있음



## Look Scheduling

![image-20230202013054541](Chapter12.assets/image-20230202013054541.png)

![image-20230202013152757](Chapter12.assets/image-20230202013152757.png)

TSD = 260



Rotational Delay 줄이기

## Shortest Latency Time First(SLTF)

![image-20230202013237486](Chapter12.assets/image-20230202013237486.png)

![image-20230202013354149](Chapter12.assets/image-20230202013354149.png)

![image-20230202013405141](Chapter12.assets/image-20230202013405141.png)



## Shortest Positioning Time First(SPTF)

![image-20230202013443205](Chapter12.assets/image-20230202013443205.png)



## Shortest Positioning Time First (SPTF)

![image-20230202013553572](Chapter12.assets/image-20230202013553572.png)



## RAID Architecture

![image-20230202013830765](Chapter12.assets/image-20230202013830765.png)

싼거 모아서 비싼거 처럼 쓰자

## RAID 0

![image-20230202013905861](Chapter12.assets/image-20230202013905861.png)

OS 입장에서 DISK는 연속된 하나의 블럭

이상적으로 4개의 디스크 쓰면 4배의 속도, 하나하나씩 안가져 와도 되니깐

디스크 하나만 고장나도 데이터 손실



## RAID 1

![image-20230202014159941](Chapter12.assets/image-20230202014159941.png)

중요한 데이터 다룰 때 씀

## RAID 3

![image-20230202014251069](Chapter12.assets/image-20230202014251069.png)

Raid 0 와 다르게 Byte 단위로 분할해서 저장

RAID 1 보단 효율적으로 쓸 수 있지만 신뢰성도 확보


## RAID 4

![image-20230202014442148](Chapter12.assets/image-20230202014442148.png)

## RAID 5

![image-20230202014610133](Chapter12.assets/image-20230202014610133.png)

패리티도 나눠서 저장

![image-20230202014704931](Chapter12.assets/image-20230202014704931.png)

참고

