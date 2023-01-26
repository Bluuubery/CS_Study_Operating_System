# 파일 시스템



## Disk System

![image-20230124202716519](Chapter11.assets/image-20230124202716519.png)

Disk pack : 실제 데이터 저장

![image-20230124202933195](Chapter11.assets/image-20230124202933195.png)

Disk drive : 플레터에서 정보를 읽음

용량, rpm : 분당 회전 수 => 높으면 정보를 빨리 읽을 수 있음

(HDD)

## Disk Address

![image-20230124203111082](Chapter11.assets/image-20230124203111082.png)

주소 찾아가는건 OS 역활

OS가 모든 종류의 하드디스크를 알 수는 없음 => block들의 나열로 취급

block 번호가 logical disk address

블록 번호로 저장해 달라고 말하면 실제 디스크는 Physical address 필요 : driver가 변환해 줌



## Disk Address mapping

![image-20230124203425730](Chapter11.assets/image-20230124203425730.png)

Disk driver는 하드웨어 제조사가 제공

## Data Access in Disk System

![image-20230124203459811](Chapter11.assets/image-20230124203459811.png)

disk access time 은 이 세가지 합한 것



## File System

![image-20230124203649667](Chapter11.assets/image-20230124203649667.png)

Partitions (C: D:)



## File Concept

![image-20230124203735849](Chapter11.assets/image-20230124203735849.png)

text : 문자, binary : 이진으로 저장

![image-20230124203830834](Chapter11.assets/image-20230124203830834.png)

![image-20230124203905800](Chapter11.assets/image-20230124203905800.png)

os기능 중 사용자가 사용할 수 있는 기능 : system call



## Fiel Access Methods

![image-20230124203948233](Chapter11.assets/image-20230124203948233.png)



## File System Organization

![image-20230124204108200](Chapter11.assets/image-20230124204108200.png)

=> OS가 system call로 제공

디스크 논리적으로 나눠 놓은걸 partition

디스크 두개로 합쳐놓은 것도 aprtition

![image-20230124204301929](Chapter11.assets/image-20230124204301929.png)

현재 File System에 다른 File System 붙이는 것


## Directory Structure

![image-20230124204421544](Chapter11.assets/image-20230124204421544.png)

파일 분류 보관

## Flat Directory Structure

![image-20230124204439377](Chapter11.assets/image-20230124204439377.png)

![image-20230124204450423](Chapter11.assets/image-20230124204450423.png)

ex) mp3



## 2-Level Directory Structure

![image-20230124204631385](Chapter11.assets/image-20230124204631385.png)

![image-20230124204715023](Chapter11.assets/image-20230124204715023.png)



## Hierarchical Directory Structure

![image-20230124204733015](Chapter11.assets/image-20230124204733015.png)

계층 구조

Home directory : 일반적으로 root 디렉토리

curr : 현재

absol : 절대 경로

rel : 상대 경로

![image-20230124205015782](Chapter11.assets/image-20230124205015782.png)

## Acyclic Graph Directory Structure

![image-20230124205030512](Chapter11.assets/image-20230124205030512.png)

내부 루프 발생 X 구조

Link : 바로가기

![image-20230124205148197](Chapter11.assets/image-20230124205148197.png)

## Genral Graph Directory Structure

![image-20230124205248918](Chapter11.assets/image-20230124205248918.png)

![image-20230124205304958](Chapter11.assets/image-20230124205304958.png)

inf loop 고려해서 설계

## File Protection

![image-20230124205411190](Chapter11.assets/image-20230124205411190.png)

## File Protection Mechanism

![image-20230124205349630](Chapter11.assets/image-20230124205349630.png)

개인 정보 파일에 암호 걸기


## Access Matrix

![image-20230124205518023](Chapter11.assets/image-20230124205518023.png)

domain : 사용자(user group)

object : 파일

![image-20230124205604879](Chapter11.assets/image-20230124205604879.png)

접근 권한 적어 놓은 표

![image-20230124205624527](Chapter11.assets/image-20230124205624527.png)

실제 구현



## Global Table

![image-20230124205641197](Chapter11.assets/image-20230124205641197.png)

통째로 저장

저장 관리 힘듬, 빈공간도 저장함

## Access Matrix

![image-20230124205706807](Chapter11.assets/image-20230124205706807.png)

빈 영역 저장 안할 수 있는 방법

Access list : 열 저장

Capability list : 행 저장

## Access List

![image-20230124205756671](Chapter11.assets/image-20230124205756671.png)

권한 없는건 저장 안해서 데이터 줌

but 파일 access 할 때 마다 계속 체크해야된다는 overhead 발생

=> 그래서 팔목에 도장 찍어주는게 Capability List

## Capability List

![image-20230124205912677](Chapter11.assets/image-20230124205912677.png)

매번 리스트 봐야하는 부담 줌

=> but capability list 잘 확인 안하면 문제 생길 수 있어서 보호해야함



## Lock-key Mechanism

![image-20230124210121870](Chapter11.assets/image-20230124210121870.png)

## Comparison of Implementations

![image-20230124210206029](Chapter11.assets/image-20230124210206029.png)

![image-20230124210440620](Chapter11.assets/image-20230124210440620.png)



## File System Implementation

![image-20230124210606268](Chapter11.assets/image-20230124210606268.png)

## Allocation Methods

![image-20230124210616541](Chapter11.assets/image-20230124210616541.png)



## Continuous Allocation

![image-20230124210631334](Chapter11.assets/image-20230124210631334.png)

접근 편하고 읽기도 좋음

but 연속 공간 6갠데 필요 공간 10개면 문제 : external fragmentation(외부 단편화)

처음 배정 공간 보다 append등 해서 더 큰 공간 필요할 수도 있는데 얼마나 줘야할지 결정 어려움



## Linked Allocation



![image-20230124210749829](Chapter11.assets/image-20230124210749829.png)

jump하고 싶을 때 비 효율적

포인터 저장 공간

=> overhead



## Linked Allocation : variation => FAT

![image-20230124210923629](Chapter11.assets/image-20230124210923629.png)

## Indexed Allocation

![image-20230124211051534](Chapter11.assets/image-20230124211051534.png)

읽다가 넘어가고 싶으면 다시 인덱스 테이블 찾아갸아됨 => 비효율적

인덱스 block 에 대한 공간 필요



## Free Space Management

![image-20230124211235003](Chapter11.assets/image-20230124211235003.png)



## Bit Vector

![image-20230124211252157](Chapter11.assets/image-20230124211252157.png)

## Linked List

![image-20230124211457792](Chapter11.assets/image-20230124211457792.png)

링크 공간 갖고 있어야되고

10번 따라가야 되면 10번 접근해야됨



## Grouping

![image-20230124211534124](Chapter11.assets/image-20230124211534124.png)

link 메모리 오버헤드 부담 줌



## Counting

![image-20230124211610332](Chapter11.assets/image-20230124211610332.png)