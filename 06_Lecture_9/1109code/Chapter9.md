# 가상 메모리

## Virtual Storage (Memory)

![image-20230104184258101](Chapter9.assets/image-20230104184258101.png)

swap device ~= 디스크



## Address Mapping

![image-20230104184438770](Chapter9.assets/image-20230104184438770.png)

![image-20230104184502433](Chapter9.assets/image-20230104184502433.png)

![image-20230104184544802](Chapter9.assets/image-20230104184544802.png)

Non continuous : virtual을 real로 바꿈

![image-20230104184653428](Chapter9.assets/image-20230104184653428.png)



## Block Mapping

![image-20230104184743320](Chapter9.assets/image-20230104184743320.png)

![image-20230104184822274](Chapter9.assets/image-20230104184822274.png)

![image-20230104185045475](Chapter9.assets/image-20230104185045475.png)

![image-20230104185057920](Chapter9.assets/image-20230104185057920.png)



## Virtual Storage Methods

![image-20230104185220541](Chapter9.assets/image-20230104185220541.png)



## Paging System

![image-20230104185234604](Chapter9.assets/image-20230104185234604.png)

![image-20230104185340340](Chapter9.assets/image-20230104185340340.png)

블록들이 하나의 프로세스 => 같은 크기의 페이지들로 나누어져 있음(swapdevice)에 들어가 있음

나누어진 애들 중 실제 사용할 애들이 메인 메모리에 올라가 있음 (non continous로)



![image-20230104185456334](Chapter9.assets/image-20230104185456334.png)

function 단위로 자른게 아니라 크기로 자른거라 공유, 보호 힘듬(겹치게도 잘리고 하니깐)

간단하고 효율적임

외부 단편화가 존재하지 않음, 내부 단편화는 존재할 수 있음



## Paging System(in Windows)

![image-20230104185821788](Chapter9.assets/image-20230104185821788.png)



## Address Mapping

![image-20230104190008224](Chapter9.assets/image-20230104190008224.png)

Block mapping과 유사

Direct mapping ~~ block mapping과 거의 유사



![image-20230104191440529](Chapter9.assets/image-20230104191440529.png)

secondary storage address : 페이지들이 어디에 올라가 있는지

![image-20230104191554258](Chapter9.assets/image-20230104191554258.png)

![image-20230104191627237](Chapter9.assets/image-20230104191627237.png)

![image-20230104191746435](Chapter9.assets/image-20230104191746435.png)

page fault : 페이지를 읽는데 실패했다 => overhead 큼(context switching 땜시)

가상메모리 성능 올릴리면 page fault  줄이는게 중요



![image-20230104191944734](Chapter9.assets/image-20230104191944734.png)

![image-20230104192015455](Chapter9.assets/image-20230104192015455.png)

PMT, kernel, memory 한번 보고 또 메머리 보니깐 두 번 봄



## Associative mapping

![image-20230104192216876](Chapter9.assets/image-20230104192216876.png)

![image-20230104192336436](Chapter9.assets/image-20230104192336436.png)

## Hybrid Direct/Associative Mapping

![image-20230104192545117](Chapter9.assets/image-20230104192545117.png)

PMT 일부만 올리기 => 어떤 entry를 올릴 것인가?

Locality

![image-20230104192730824](Chapter9.assets/image-20230104192730824.png)

![image-20230104192743469](Chapter9.assets/image-20230104192743469.png)

TLB에 있으면 associatve mapping으로 찾아가고 없으면 direct mapping 하면됨(잠깐 들려서 정보 갖고 있으라고 말하고)



## Memory Management

![image-20230104193051292](Chapter9.assets/image-20230104193051292.png)

FPM : Fixed Partition Multiprogramming

![image-20230104193154874](Chapter9.assets/image-20230104193154874.png)

AV : 가장 처음으로 비어있는 entry 지칭

PID : 누가 가져갔는지 process id

할당되면 av 옮겨줌



## Page Sharing

![image-20230104193431260](Chapter9.assets/image-20230104193431260.png)

![image-20230104193557903](Chapter9.assets/image-20230104193557903.png)

![image-20230104193626822](Chapter9.assets/image-20230104193626822.png)

![image-20230104193719210](Chapter9.assets/image-20230104193719210.png)

![image-20230104193819982](Chapter9.assets/image-20230104193819982.png)

## Page Protection

![image-20230104194002417](Chapter9.assets/image-20230104194002417.png)

## Paging System - Summary

![image-20230104194048418](Chapter9.assets/image-20230104194048418.png)



## Segmentation System

![image-20230104194254141](Chapter9.assets/image-20230104194254141.png)

block 크기가 다를 수 있어서 미리 자를 수는 없음

논리적으로 잘라놔서 공유, 보관 용이

대신 관리 overhead가 큼

내부 단편화는 없는데 외부 단편화는 발생 가능

![image-20230104194400737](Chapter9.assets/image-20230104194400737.png)

![image-20230104194418182](Chapter9.assets/image-20230104194418182.png)

swap device : 가상 메모리

![image-20230104194509401](Chapter9.assets/image-20230104194509401.png)

![image-20230104194542113](Chapter9.assets/image-20230104194542113.png)

![image-20230104195333525](Chapter9.assets/image-20230104195333525.png)

![image-20230104195346615](Chapter9.assets/image-20230104195346615.png)

segment fault

segment protection => protection bits 확인

![image-20230104195620367](Chapter9.assets/image-20230104195620367.png)

![image-20230104195651989](Chapter9.assets/image-20230104195651989.png)

내부에서 얼마나 점프해야되는지 적어놓으면 돼서 공유 용이

![image-20230104195832016](Chapter9.assets/image-20230104195832016.png)

non continuous니깐 필요한것만 올릴 수 있음

## Paging vs Segmentation

![image-20230104200013976](Chapter9.assets/image-20230104200013976.png)

## Hybrid Paging/Segmentation

![image-20230104200959218](Chapter9.assets/image-20230104200959218.png)

![image-20230104201016083](Chapter9.assets/image-20230104201016083.png)

크기가 다르게 잘라놓은 segment를 다시 페이지로 잘라서 메모리에 저장

![image-20230104201040262](Chapter9.assets/image-20230104201040262.png)

![image-20230104201156737](Chapter9.assets/image-20230104201156737.png)

메모리에는 페이지가 올라가니깐 residence bit는 필요하지 않음 but PMT address는 필요하니깐 추가됐음

![image-20230104201232403](Chapter9.assets/image-20230104201232403.png)

![image-20230104201302444](Chapter9.assets/image-20230104201302444.png)

![image-20230104201333467](Chapter9.assets/image-20230104201333467.png)

![image-20230104201557093](Chapter9.assets/image-20230104201557093.png)