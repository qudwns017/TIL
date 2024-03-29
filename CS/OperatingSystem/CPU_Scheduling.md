# CPU Scheduling Algorithm

> CPU 스케줄러는 CPU 스케줄링 알고리즘에 따라 프로세스에서 해야 하는 일을 스레드 단위로 CPU에 할당하는 것.
> 프로그램이 실행될 때는 CPOU 스케줄링 알고리즘이 어떤 프로그램에 CPU 소유권을 줄 것인지 결정한다.

## 알고리즘 목표
1. CPU 이용률 높이기
2. 주어진 시간에 많은 일 시키기
3. 준비 큐에 있는 프로세스는 최소화로 배치
4. 응답 시간은 짧게 설정

## 비선점형 방식
> 프로세스가 스스로 CPU 소유권을 포기하는 방식이며, 강제로 프로세스를 중지하지 않는다. <br>단순 반복 작업, 일괄 처리 방식에 적합

### 장점
* 복잡한 알고리즘이 필요 없으며 Context Switching 발생이 매우 적으므로 응답 시간이 적다.
### 단점 : 
* 공정성이 없으며 대기시간이 높다. 
* 우선순위에 의해 무한정 대기가 발생할 수 있으며 그에 따라 시스템의 중요한 작업을 빠르게 해결하지 못할 수 있다.
* 알고리즘에 따라 인터럽트가 발생하더라도 CPU를 반환하지 않는 경우도 있으며 사용 효율이 줄어든다.

### FCFS(First com, First Served)
* 가장 먼저 온 프로세스를 가장 먼처 처리하는 알고리즘
* 길게 수행되는 프로세스 때문에 '준비 큐에서 오래 기다리는 현상(Convoy effect)'이 발생

### SJF(Shortest Job First)
* 실행 시간이 가장 짧은 프로세스를 가장 먼저 실행하는 알고리즘
* 짧은 프로세스에게 밀려 긴 실행 시간을 가진 프로세스가 실행되지 않는 현상(Starvation)이 일어나며, 평균 대기 시간이 가장 짧음
* 하지만 실제로는 실행 시간을 알 수 없기 때문에 과거의 실행했던 시간을 토대로 추측해서 사용

### 우선순위(HRN, Highest Response-ratio Next)
* 기존 SJF 알고리즘의 Starvation 현상에 의한 단점을 보완한 알고리즘
* 오래된 작업일 수록 '우선순위를 높이는 방법(Aging)'을 통해 단점을 보완
* Starvation을 방지할 수 있지만 실행시간 예측이 불가능하다

## 선점형 방식
> 현대 운영체제가 쓰는 방식으로 지금 사용하고 있는 프로세스를 우선 순위에 따라 알고리즘에 의해 중단시키고, 강제로 다른 프로세스에 CPU 소유권을 할당하는 방식이다.<br>
> 멀티 프로그래밍 환경, 여러 개의 프로그램이 실시간으로 동작하는 환경에 적합
### 장점
* 우선순위가 높은 프로세스를 빠르게 처리할 수 있다.
* 비선점 스케줄링에 비하여 대기시간이 적다.
* 적절한 알고리즘을 통해 공정성과 대기시간 최소화, CPU 사용률을 극대화시킬 수 있다.
### 단점
* 복잡한 알고리즘이 필요하며 구조 설계가 어렵다.
* 스케줄링 동작에 의해 기본적으로 오버헤드가 있으며 Context Switching이 자주 발생하므로 응답시간이 늘어 성능에 영향을 미친다.

### 라운드 로빈(RR, Round Robin)
* 동일한 할당 시간을 주고 그 시간 안에 끝나지 않으면 다시 준비 큐의 뒤로 가는 알고리즘
* 예를 들어 $q$만큼의 할당 시간이 부여되었고 $N$개의 프로세스가 있다고 해보자
* 각 프로세스는 동일한 시간인 $q$만큼의 시간을 할당 받기 때문에 $N$번째 프로세스가 CPU를 할당 받기 위해서는 $(N - 1) * q$만큼의 시간이 지나야한다.
* 할당 시간이 너무 길면 FCFS 알고리즘이 되고, 너무 짧으면 Context Switching이 잦아져서 오버헤드, 즉 비용이 커진다.
* 전체 작업 시간은 길어지지만 평균 응답 시간은 짧아진다.

### SRF(Shortest Remaining Time First)
* 중간에 더 짧은 작업이 들어오면 수행하던 프로세스를 중지하고 해당 프로세스를 수행하는 알고리즘
* SJF는 실행 시간이 더 짧은 작업이 와도 순서대로 처리하지만, SRF는 프로세스를 중지하고 그 프로세스를 수행한다는 차이점이 있다.

### 다단계 큐 스케줄링(Multilevel Queue Scheduling)
* 우선 순위마다 별도의 준비 큐를 사용
* 프로세스의 특성에 맞는 큐마다 성격에 맞는 다양한 스케줄링 알고리즘 적용 가능
* 큐 간의 프로세스 이동이 안 되므로 스케줄링 부담은 적지만 유연성이 떨어진다.

### 다단계 피드백 큐 스케줄링(Multilevel Feedback Queue Scheduling)
* 다단계 큐와는 다르게 프로세스가 큐들 사이를 이동을 허용한 알고리즘
* 즉, 다단계 피드백 큐 스케줄링 = 다단계 큐 스케줄링 + 동적인 프로세스 우선순위 변화