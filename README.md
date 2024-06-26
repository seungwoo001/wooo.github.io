# README 파일 작성하기 과제
리눅스명령어 top, ps, jobs, kill 조사하기.

+ **top**

  top 명령어는 실시간으로 cpu 사용량, 메모리 사용량 등 서버를 모니터링할 수 있는 정보를 출력하는 명령어 입니다.
```
    # top -b -n 1
```
  ex)
![top](https://github.com/seungwoo001/wooo.github.io/blob/main/%EB%8B%A4%EC%9A%B4%EB%A1%9C%EB%93%9C2.png)


**top** : 시스템 현재시간, 서버 구동시간, 현재 접속 유저수, 로드 에버리지를 출력합니다.

**TasKs** : 현재 프로세스들의 상태를 나타내고 실행중, 대기중, 종료, 좀비 수를 출력합니다.

**Cpu** : CPU 사용량을 나타내고 사용자 프로세스, 커널 프로세스, 프로세스 우선순위, 사용안하는 비율, IO완료기다리는 비율, 소프트웨어 인터럽트, VM에 할당된 비율을 출력합니다.

**MiB Men** : 시스템이 가진 메모리에 대한 사용률을 나타냅니다.

total은 설치된 총 메모리, free는 사용 가능한 메모리, used는 사용된 메모리, buff/cache는 쓰기 위해 버퍼링되는 정보의 양을 나타냅니다.

**MiB Swap** : 가상 메모리를 활용할 때, 원할하게 작동하도록 메모리를 분배시킨 정보를 나타냅니다.

---
+ **ps**

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

---
+ **jobs**

  jobs 명령어는 백그라운드로 실행 중인 프로세스나 현재 중지된 프로세스의 목록을 출력해 주는 명령어 입니다. 특정 작업 번호를 지정하면 해당 작업의 정보만 볼 수도 있습니다.

      # jobs [option] [JOB]

주로 사용하는 옵션들 입니다.

**-p** :	백그라운드에 있는 프로세스의 프로세스 아이디(PID)만 출력한다.

**-l** :	백그라운드에 있는 프로세스의 프로세스 아이디(PID)를 함께 출력한다.

**-s** :	백그라운드에 있는 프로세스 중 멈춰있는 프로세스만 출력한다.

**-r** :	백그라운드에 있는 프로세스 중 실행중인 프로세스만 출력한다.

**-n** : 마지막로 알림 이후 변경된 잡만 출력합니다.

ex)

![top](https://github.com/seungwoo001/wooo.github.io/blob/main/%EB%8B%A4%EC%9A%B4%EB%A1%9C%EB%93%9C3.png)
  
|항목|출력 예시|의미|
|---|:---|:---:|
|작업 번호| [1] |작업 번호로서 백그라운드로 실행할 때마다 순차적으로 증가합니다. ([1],[2],[3],...)|
|작업 순서|+|+ : 가장 최근에 접근한 작업<br>- : + 작업보다 바로 전에 접근한 작업 <br>공백 : 그 외의 작업<br>|
|상태|Running|작업 상태를 표시합니다. <br>Running, Done, Stopped...<br> |
|명령|sleep 100&|백그라운드로 실행 중인 명령입니다.|

---
+ **kill**

  kill 명령어는 프로세스를 종료하는 명령어 입니다. 백그라운드에 있는 프로그램과 같은 경우 kill명령어를 통해 제어할 수 있습니다. 지정한 프로세스에 지정한 시그널을 보냅니다. 시스템에 문제가 생겨 해당 프로세스를 종료할 필요가 있을 경우 많이 사용됩니다. 단순 kill 명령어로 종료가 되지 않는 프로세스는 9 시그널을 보내어 강제로 종료시킬수 있습니다. 프로세스를 안전하게 종료하기 위해서는 "kill -9 pid", "kill -SIGKILL pid" 형태로 프로세스 강제 종료를 권장하지 않습니다. (데이터 유실 위험) 정상종료는 시그널 번호 1번 SIGHUP을 권장드립니다.


시그널이란?

인터럽트의 일종으로 어떤 이벤트의 발생을 프로세스에게 알려주는 것입니다.

 특정 이벤트가 발생했을 때 프로세스에게 전달하는 신호(메시지)

 리눅스에서 프로세스끼리 통신할 때 사용합니다.

 주요 시그널 입니다.

 ![top](https://github.com/seungwoo001/wooo.github.io/blob/main/%EB%8B%A4%EC%9A%B4%EB%A1%9C%EB%93%9C5.png)


      # kill [option] [PID]

  주로 사용하는 옵션들 입니다.

  **-9** :	프로세스아이디(PID)를 직접 지정하여 종료시 사용 됩니다
  
  **-l** :	신호(Signal)로 사용할 수 있는 신호(Signal) 이름들을 보여준다.

  ex)

  ![top](https://github.com/seungwoo001/wooo.github.io/blob/main/%EB%8B%A4%EC%9A%B4%EB%A1%9C%EB%93%9C6.png)

  ---

  
