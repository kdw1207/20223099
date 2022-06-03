# 리눅스 명령어

## top
실시간으로 cpu 사용률을 체크해주는 도구

* __사용법__ - 리눅스에서 top 명령어를 친다.
  
  ![image](https://user-images.githubusercontent.com/102851163/171868817-ed6ff9ab-acc8-49d4-aa53-92ddb58b646b.png)
    흰색 칸 위로는 현재 시스템의 상태를 보여주는 것이다.
    시스템의 시간이나 uptime 등등을 전체적으로 확인 가능하다.
    
    흰색 칸 아래는 현재 실행하고 있는 프로세스 현황을 볼 수 있다.
  
* __top 정보 시스템 내용__
```
22:54:42 : 현재 서버의 시간
up 0 min : uptime(켜져있는 시간)
0 users : 유저
load average : 현재 시스템이 얼마나 일을 하고 있는지 1분, 5분, 15분 단위로 실행/대기 중인 프로세스 수를 나타내고 있음
Tasks : 프로세스 개수
```
  ```
  %us : 유저 레벨에서 사용하고 있는 CPU 비중
  %sy : 시스템 레벨에서 사용하고 있는 CPU 비중
  %id : 유휴 상태의 CPU 비중
  %wa : 시스템이 I/O 요청을 처리하지 못한 상태에서의 CPU idle 상태인 비중
  ```
    KiB Mem, Swap : 각 메모리의 상태 정보
    
* 프로세스 상태 정보
``` 
PID : 프로세스 ID(PID)
USER : 프로세스를 실행시킨 사용자 ID
PRI : 프로세스의 우선순위(priority)
NI : NICE 값. 일의 nice value값이다. 마이너스를 가지는 nice value는 우선순위가 높음.
VIRT : 가상 메모리의 사용량(SWAP + RES)
RES : 현재 페이지가 상주하고 있는 크기(Resident Size)
SHR : 분할된 페이지, 프로세스에 의해 사용된 메모리를 나눈 메모리의 총합.
S : 프로세스의 상태[S(sleeping), R(running), W(swapped out process), Z(zombies)]
%CPU : 프로세스가 사용하는 CPU의 사용율
%MEM : 프로세스가 사용하는 메모리의 사용율
COMMAND : 실행된 명령어
```

* Top 명령어 옵션(top 실행 중 사용가능)
