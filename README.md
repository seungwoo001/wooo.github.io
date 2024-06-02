# README 파일 작성하기 과제
리눅스명령어 top, ps, jobs, kill 조사하기.

+ top

  top 명령어는 실시간으로 cpu 사용량, 메모리 사용량 등 서버를 모니터링할 수 있는 정보를 출력하는 명령어 입니다.
```
    top -b -n 1
```
  ex)
![top](https://github.com/seungwoo001/wooo.github.io/blob/main/%EB%8B%A4%EC%9A%B4%EB%A1%9C%EB%93%9C.png)

**top** - 시스템 현재시간, 서버 구동시간, 현재 접속 유저수, 로드 에버리지를 출력합니다.

**TasKs** - 현재 프로세스들의 상태를 나타내고 실행중, 대기중, 종료, 좀비 수를 출력합니다.

**Cpu** - CPU 사용량을 나타내고 사용자 프로세스, 커널 프로세스, 프로세스 우선순위, 사용안하는 비율, IO완료기다리는 비율, 소프트웨어 인터럽트, VM에 할당된 비율을 출력합니다.

**MiB Men** - 시스템이 가진 메모리에 대한 사용률을 나타냅니다.

total은 설치된 총 메모리, free는 사용 가능한 메모리, used는 사용된 메모리, buff/cache는 쓰기 위해 버퍼링되는 정보의 양을 나타냅니다.

**MiB Swap** - 가상 메모리를 활용할 때, 원할하게 작동하도록 메모리를 분배시킨 정보를 나타냅니다.

---
+ ps

  ps 명령어는 현재 실행중인 프로세스에 관한 정보를 출력하여 사용자에게 정보를 제공하는 명령어 입니다. 프로세스 중에서 CPU, 메모리 등등을 많이 점유하고 있거나, 지나치게 많은 자식 프로세스를 생성하는 등등에 시스템에 속도가 느려지는 경우 ps 명령어로 분석하여 시스템 오류를 감지할 수 있습니다.

        # ps [option]

**-e** : 실행중인 모든 프로세스를 출력 (-A와 동일한 옵션)

**-f** : 풀-포맷으로 리스트를 보여준다. UID, PID, PPID 등을 포함해서 출력해준다.

**-l** : -f 옵션보다 더 자세하게 출력

**-a** : 세션 리더와 터미널에 연관되어있지 않은 프로세스들을 제외한 모든 프로세스를 출력

**a(BSD 계열)** : 터미널과 연관되어 있는 프로세스만 출력

**-u** : -u [userlist] 와 같이 사용하며, 특정 유저의 프로세스 정보를 출력, 유저를 지정하지 않으면 현재 사용자를 기준

**u(BSD 계열)** : 프로세스의 소유자를 기준으로 출력

**x(BSD 계열)** : a 옵션과 결합하여 모든 프로세스를 출력

위 처럼 여러 옵션들이 있지만, 주로 자주 사용하는 옵션으로는 ps -ef 옵션을 가장 많이 사용합니다.

ex)
![top](https://github.com/seungwoo001/wooo.github.io/blob/main/%EB%8B%A4%EC%9A%B4%EB%A1%9C%EB%93%9C1.png)


  
