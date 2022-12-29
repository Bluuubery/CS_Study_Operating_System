## 메모리(기억장치)의 종류

![image-20221229023708273](Chapter8.assets/image-20221229023708273.png)

HW : CPU

SW : OS(운영체제)



## 메모리(기억장치) 계층구조

![image-20221229023747027](Chapter8.assets/image-20221229023747027.png)

블록 단위로 메모리에 올라옴

컴퓨터 32bit, 65bit : word 단위입니다(틀린 말은 아님)

## Address binding

![image-20221229024206236](Chapter8.assets/image-20221229024206236.png)

![image-20221229024351625](Chapter8.assets/image-20221229024351625.png)

![image-20221229024532421](Chapter8.assets/image-20221229024532421.png)

![image-20221229024722573](Chapter8.assets/image-20221229024722573.png)

![image-20221229024828569](Chapter8.assets/image-20221229024828569.png)



## Dynamic Loading

![image-20221229024959802](Chapter8.assets/image-20221229024959802.png)



## Swapping

![image-20221229025106799](Chapter8.assets/image-20221229025106799.png)

## Memory Allocaiton

![image-20221229025218921](Chapter8.assets/image-20221229025218921.png)

## Countinuous Memory Allocation

![image-20221229025256721](Chapter8.assets/image-20221229025256721.png)

![image-20221229025402416](Chapter8.assets/image-20221229025402416.png)



## Uni-Programming

![image-20221229025501164](Chapter8.assets/image-20221229025501164.png)

![image-20221229025510086](Chapter8.assets/image-20221229025510086.png)

![image-20221229025637400](Chapter8.assets/image-20221229025637400.png)

![image-20221229025736432](Chapter8.assets/image-20221229025736432.png)

공간 많은데 나머지 공간이 낭비됨

=> 하나만 올라간다는게 원인 => 여러개를 올려주면 됨

## Fixed partition Multiprogramming

![image-20221229025811824](Chapter8.assets/image-20221229025811824.png)

![image-20221229025912995](Chapter8.assets/image-20221229025912995.png)

![image-20221229030005821](Chapter8.assets/image-20221229030005821.png)

각 파티션 경계마다 침범 방지



![image-20221229030040511](Chapter8.assets/image-20221229030040511.png)

남은 공간 있긴 한데 연속된 메모리가 아니라 낭비됨



## Fixed partition Multitprogramming

![image-20221229030339448](Chapter8.assets/image-20221229030339448.png)



## Variable Partition Multiprogramming

![image-20221229030449845](Chapter8.assets/image-20221229030449845.png)

![image-20221229030457443](Chapter8.assets/image-20221229030457443.png)

![image-20221229030506707](Chapter8.assets/image-20221229030506707.png)

![image-20221229030522466](Chapter8.assets/image-20221229030522466.png)

![image-20221229030605548](Chapter8.assets/image-20221229030605548.png)

internal fragmentation X

![image-20221229030624993](Chapter8.assets/image-20221229030624993.png)

![image-20221229030637499](Chapter8.assets/image-20221229030637499.png)

나갔는데 아무도 안쓰는 자리 생김

![image-20221229030653649](Chapter8.assets/image-20221229030653649.png)

앞에 못 붙음



## 배치 전략(Placement strategies)

![image-20221229030800707](Chapter8.assets/image-20221229030800707.png)

![image-20221229030922663](Chapter8.assets/image-20221229030922663.png)

![image-20221229104826948](Chapter8.assets/image-20221229104826948.png)

![image-20221229104834375](Chapter8.assets/image-20221229104834375.png)

## Variable Partition Multiprogramming

![image-20221229105009826](Chapter8.assets/image-20221229105009826.png)

## Coalescing holes (공간 통합)

![image-20221229105017495](Chapter8.assets/image-20221229105017495.png)

![image-20221229105149156](Chapter8.assets/image-20221229105149156.png)



## Storage Compaction(메모리 압축)

![image-20221229105213211](Chapter8.assets/image-20221229105213211.png)

![image-20221229105221300](Chapter8.assets/image-20221229105221300.png)