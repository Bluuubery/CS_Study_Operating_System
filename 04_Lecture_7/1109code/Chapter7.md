# 교착상태 (Deadlock Resolution)

## Deadlock의 개념

![image-20221221064421389](Chapter7.assets/image-20221221064421389.png)

Processor가 아닌 자원이 필요할 때 blocked로 감

그런데 자원 발생 가능성이 없을 때 이벤트를 기다리면 프로세스가 deadlock 상태가 됨



## Deadlock의 개념

![image-20221221064534483](Chapter7.assets/image-20221221064534483.png)

deadlock은 asleep 상태에서 기다림, 가능성 zero

starvation은 프로세스를 기다림 (cpu) => 절대 발생하지 않는 사건은 아니고 운이 없어서 새치기 당하는거



## 자원의 분류

![image-20221221064747151](Chapter7.assets/image-20221221064747151.png)



## 선점 가능 여부에 따른 분류

![image-20221221064841856](Chapter7.assets/image-20221221064841856.png)



## 할당 단위에 따른 분류

![image-20221221065157934](Chapter7.assets/image-20221221065157934.png)

cpu는 코어 하나면 한번에 하나만 쓸 수 있음 => total allocation resources

하나의 자원을 여러 조각으로 나누어 여러 프로세스들에 할당



## 동시 사용 가능 여부에 따른 분류

![image-20221221065251218](Chapter7.assets/image-20221221065251218.png)

memory 동시에 쓸 수 있는거 아님? ㄴㄴ => 본인에게 할당 된 영역을 동시에 못 씀!, 각자 영역을 가지고 있고 해당 영역을 혼자 쓰는 것

shared : 워드 프로세서 창 여러개 띄울 수 있음, 프로그램은 동시에 여러 프로세스가 사용 가능함



## 재사용 가능 여부에 따른 분류

![image-20221221065444289](Chapter7.assets/image-20221221065444289.png)



## Deadlock과 자원의 종류

![image-20221221065543345](Chapter7.assets/image-20221221065543345.png)

Non-preemptible resources : 한 번 할당 받으면 뺏을 수 없으니깐 교착 발생

Exclusive : 혼자쓰는거니깐 문제될 수 있음 (shared는 나눠 쓸 수 있으니깐 X)

CR은 고려가 힘드니깐 빼고 생각하자



## Deadlock 발생의 예

![image-20221221065746484](Chapter7.assets/image-20221221065746484.png)

## Graph Model

![image-20221221065959604](Chapter7.assets/image-20221221065959604.png)

서로가 가지고 있는걸 요구하는 cycle 상태 => deadlock



## State Transition Model

![image-20221221071305908](Chapter7.assets/image-20221221071305908.png)

![image-20221221071401174](Chapter7.assets/image-20221221071401174.png)



## Deadlock 발생 필요 조건

![image-20221221071655536](Chapter7.assets/image-20221221071655536.png)

4 가지 중 하나만 없애도 deadlock 발생 X

## Deadlock 해결 방법

![image-20221221072210537](Chapter7.assets/image-20221221072210537.png)



## Deadlock Prevention



![image-20221221072331771](Chapter7.assets/image-20221221072331771.png)

Exclusive use of resources

![image-20221221072342850](Chapter7.assets/image-20221221072342850.png)

1. 현실적으로 불가능

2. 자원을 썼는데 취소하면 기존 자원 모두 반납하므로 낭비

Non-preemptible resources

![image-20221221072359367](Chapter7.assets/image-20221221072359367.png)

3. 필요하지 않은 순간에도 자원을 갖고 있어야 돼서 낭비, 뒤에 있는 애들은 엄청 대기 할 수 있음
4. 

Hold and wait

![image-20221221072529202](Chapter7.assets/image-20221221072529202.png)



## Deadlock Avodiance

deadlock 지켜보다가 피해가자

![image-20221221073212871](Chapter7.assets/image-20221221073212871.png)

4가지 조건 중 하나를 없앨 수 없으므로 감시하다가 가능성 있으면 피해가자

![image-20221221073312745](Chapter7.assets/image-20221221073312745.png)

![image-20221221073418530](Chapter7.assets/image-20221221073418530.png)

![image-20221221073515390](Chapter7.assets/image-20221221073515390.png)

![image-20221221073601599](Chapter7.assets/image-20221221073601599.png)

![image-20221221073902369](Chapter7.assets/image-20221221073902369.png)

프로세스가 sequence를 모두 완료할 수 있는 상태가 하나라도 존재하면 safe state

deadlock 피해갈 수 있음

![image-20221221073938748](Chapter7.assets/image-20221221073938748.png)

반드시 교착상태는 아니지만 가능성 있음 => unsafe state



![image-20221221074106392](Chapter7.assets/image-20221221074106392.png)

빌려줬다고 가정하면 해결되면

![image-20221221074205923](Chapter7.assets/image-20221221074205923.png)

빌려줬다고 가정했을 때 unsafe면 거절

가정 => simulation => safe sequecne면 ok, safe sequence 없으면 X



## Habermann's alogrithm

![image-20221221074318971](Chapter7.assets/image-20221221074318971.png)

여러개인 경우

![image-20221221074332812](Chapter7.assets/image-20221221074332812.png)

![image-20221221074417786](Chapter7.assets/image-20221221074417786.png)

safe sequence 존재 => safe state다

![image-20221221074525662](Chapter7.assets/image-20221221074525662.png)

현재 상태에서 빌려준다고 했을 때 safe sequence 찾을 수 있으면 빌려줌

![image-20221221074637911](Chapter7.assets/image-20221221074637911.png)

safe sequence 없으면 거절

![image-20221221074658302](Chapter7.assets/image-20221221074658302.png)

low resource utilizaiton : 쓸 수 있는데도 못쓰는 경우도 있을 수 있음



## Deadlock Detection

![image-20221221074903372](Chapter7.assets/image-20221221074903372.png)

deadlock이 발생 했는지 알아야함

![image-20221221074924313](Chapter7.assets/image-20221221074924313.png)

bipartite : 한쪽에서 한쪽으로만 연결 가능

![image-20221221075017193](Chapter7.assets/image-20221221075017193.png)

![image-20221221075113161](Chapter7.assets/image-20221221075113161.png)

![image-20221221075122945](Chapter7.assets/image-20221221075122945.png)

![image-20221221075202946](Chapter7.assets/image-20221221075202946.png)

## Deadlock Detection Method

![image-20221221075233834](Chapter7.assets/image-20221221075233834.png)

![image-20221221075300817](Chapter7.assets/image-20221221075300817.png)

unblocked process edg를 지운다

요청 <= 남은 수

![image-20221221075529723](Chapter7.assets/image-20221221075529723.png)

![image-20221221075630310](Chapter7.assets/image-20221221075630310.png)

모든 edge가 지워짐 => deadlock X

![image-20221221075652778](Chapter7.assets/image-20221221075652778.png)

![image-20221221080056845](Chapter7.assets/image-20221221080056845.png)



## Deadlock Avoidance vs Detection

![image-20221221080137525](Chapter7.assets/image-20221221080137525.png)



## Deadlock Recovery

![image-20221221080206411](Chapter7.assets/image-20221221080206411.png)

![image-20221221080217531](Chapter7.assets/image-20221221080217531.png)

termination cost model : 여러개 Deadlock 일 때 누굴 종료할지 기준

![image-20221221080307726](Chapter7.assets/image-20221221080307726.png)

lowest-termination cost process first : 비용이 정의 되면 쉽게 찾을 수 있음

minimum cost recovery :  모든 경우 고려 해서 최적

![image-20221221080437317](Chapter7.assets/image-20221221080437317.png)

![image-20221221080557557](Chapter7.assets/image-20221221080557557.png)

어쨌든 프로세스가 종료됨, 처음으로 돌아와야 돼서 비효율적

프로세스도 저장해 놓고 거기로 돌아감