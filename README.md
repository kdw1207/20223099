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
```
shift + p : CPU 사용률이 높은 프로세스 순서대로 표시
shift + m : 메모리 사용률이 높은 프로세스 순서대로 표시
shift + t : 프로세스가 돌아가고 있는 시간 순서대로 표시
k : 프로세스 kill -k 입력 후 종료할 PID 입력 signal을 입력하라고 하면 kill signal인 9를 입력
a : 메모리 사용량에 따라 정렬
b : Batch 모드 작동
c : 명령행/프로그램 이름 토글
d : 지연 시간 간격은 다음과 같다. -d ss.tt(second.tenths)
h : 도움말
H : 스레드 토글
i : 유휴 프로세스 토글
m : VIRT/USED 토글
M : 메모리 유닛 탐지
n : 반복 횟수 제한 : -n number
p : PID를 다음과 같이 모니터 : -pN1 -pN2 ... or -pN1, N2[,...]
s : 보안 모드 작동
S : 누적 시간 모드 토글
u : 사용자별 모니터링 : u somebody
U : u랑 같음
숫자 1 : CPU Core별로 사용량을 보여줌
```
![image](https://user-images.githubusercontent.com/102851163/171876799-0bfe9e79-9f9d-4d5b-a685-f416a864c592.png "shift + t")

![image](https://user-images.githubusercontent.com/102851163/171877631-2c0fb9c9-a76c-451c-b0a2-509f8219cfa4.png "h")


* Tip 명령어 페이지 이동
```
Page Down/Up 키를 통해 다음 목록과 이전 목록을 확인 가능하다.
```

## ps
현재 실행중인 프로세스 목록과 상태를 보여줌
![image](https://user-images.githubusercontent.com/102851163/171881537-bbac82b2-fba4-4d8f-9322-efe92aad1fb7.png)


* __사용법__ - $ ps [option]

|옵션|내용|
|:---:|:---:|
|-A|모든 프로세스를 출력한다.|
|a|터미널과 연관된 프로세스를 출력한다.|
|-a|세션 리더를 제외하고 데몬 프로세스처럼 터미널에 종속되지 않은 모든 프로세스를 출력한다.|
|-e|커널 프로세스를 제외한 모든 프로세스를 출력해준다.|
|-f|풀 포맷으로 보여준다.|
|-l|긴 포맷으로 보여준다.|
|-o 값|출력 포맷을 지정하는 옵션으로 값으로는 pid, tty, time, cmd 등을 지정할 수 있다.|
|-M|64비트 프로세스들을 보여준다.|
|-m|프로세스들 뿐만 아니라 커널 스레드들도 보여준다.|
|-p|특정 PID를 지정할 때 사용한다.|
|-r|현재 실행중인 프로세서를 보여준다.|
|u|프로세스의 소유자를 기준으로 출력한다.|
|-u|특정 사용자의 프로세스 정보를 확인할 때 사용한다. 사용자를 지정하지 않으면 현재 사용자를 기준으 로 정보를 출력한다.|
|X|데몬 프로세스처럼 터미널에 종속되지 않는 프로세스를 출력한다.|
|-x|로그인 상태에 있는 동안 아직 완료되지 않은 프로세스들을 보여준다.|

특정 프로세스를 확인하는 데 주로 grep이라는 명령어와 함께 사용한다.

ex) ps -ef | grep '프로세스명'

![image](https://user-images.githubusercontent.com/102851163/171883149-09ae110b-3b56-4dde-a701-e75c5293385c.png "ps ax 작동 중인 모든 프로세스를 보고 싶을 때 사용")


* __ps 항목__
```
USER : BSD계열에서 나타나는 항목으로 프로세스 소유자의 이름
UID : SYSTEM V계열에서 나타나는 항목으로 프로세스 소유자의 이름
PID : 프로세스의 식별번호
PPID : 부모 프로세스 ID
%CPU : CPU 사용 비율의 추정치
%MEM : 메모리의 사용 비율의 추정치
VSZ : K단위 또는 페이지 단위의 가상메모리 사용량
RSS : 실제 메모리 사용량
TTY : 프로세스와 연결된 터미널
S, STAT : 현재 프로세스의 상태 코드
TIME : 총 CPU 사용 시간
COMMAND : 프로세스의 실행 명령행
STIME : 프로세스가 시작된 시간 혹은 날짜
C, CP : 짧은 기간 동안의 CPU 사용률
F : 프로세스의 플래그
PRI : 실제 실행 우선순위
NI : nice 우선순위 번호
```

## jobs
작업이 중지된 상태, 백그라운드로 진행 중인 작업 상태, 변경되었지만 보고되지 않은 상태 등을 표시함

![image](https://user-images.githubusercontent.com/102851163/171886480-0e597b29-7a75-4632-a018-180b569ee37f.png)

* __사용법__ - jobs [옵션][job ID], jobs -x command[args]

|옵션|내용|
|:---:|:---:|
|-l|프로세스 그룹 ID를 state 필드 앞에 출력|
|-n|프로세스 그룹 중에 대포 프로세스 ID를 출력|
|-p|각 프로세스 ID에 대해 한 행씩 출력|
|command|지정한 명령어를 실행|

* __jobs로 알 수 있는 상태 값__

|상태|내용|
|:---:|:---:|
|Running|작업이 일시 중단되지 않았고 종료하지 않고 계속 진행 중임|
|Done|작업이 완료되어 0을 반환하고 종료했음을 의미|
|Done(code)|작업이 정상적으로 완료되었으며, 0이 아닌 코드를 반환했음을 의미|
|Stopped|작업이 일시 중단|
|Stopped(SIGTSTP)|SIGTSTP신호가 작업을 일시 중단|
|Stopped(SIGSTOP)|SIGSTOP신호가 작업을 일시 중단|
|Stopped(SIGTTIN)|SIGTTIN신호가 작업을 일시 중단|
|Stopped(SIGTTOU)|SIGTTOU신호가 작업을 일시 중단|

## kill
대개 프로세스를 죽일 때 사용한다. 또는 프로세스에 시그널을 보내 원한는 작업을 하게 한다.

* __사용법__ - $kill [pid], $kill -s [signal id][pid] $kill -s [signal text][pid]
![image](https://user-images.githubusercontent.com/102851163/171890535-634a36d3-f17b-4895-af7b-9acaa1bfd7f2.png)

* __시그널__ - 어떤 이벤트의 발생을 프로세스에게 알려주는 것이다, kill -l명령어를 통해 확인 가능하다.

![image](https://user-images.githubusercontent.com/102851163/171894828-4801e831-bf42-407e-88a7-0f2b737a64f0.png)
