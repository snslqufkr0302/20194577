# 20194577
오픈소스SW개론

## 1. 리눅스 명령어 : top, ps, jobs, kill 명령어 조사하기
### top
___시스템 프로세스/메모리 사용 현황을 실시간으로 출력한다___
#### top [옵션]

* -b : 배치모드로 정보를 출력한다. 실시간 상화 대화형모드로 정보를 화면에 일렬로 출력한다.
* -d delay : 지정한 시간(delay 초)의 간격으로 정보를 업데이트하여 출력한다.
* -i idle : 토글값이 off일 때, idle 프로세스나 좀비 프로세스 정보를 출력하지 않는다.
* -n num : 지정한 시간(num)만큼 업데이트 정보를 출력한다.
* -p pid : 지정한 프로세스 ID(pid)의 정보만을 출력한다.
* -q : 시간의 간격 없이 계속하여 업데이트 정보를 출력한다.
* -s : 몇 개의 대화식 명령을 비활성화한다(시큐어 모드).
* -S : 누적된 정보를 출력한다(cumulative 모드).


#### top 단축키 명령어
|명령어|설명|
|--------------|------------------------------------|
|F or f|정보를 업데이트한다.|
|O or o|스크린을 다시 초기화한다.|
|h or ?|필드를 추가나 제거한다.|
||아래 ‘top 항목에 대한 설명’을 참조한다.|
||확인하고자 하는 항목의 알파벳을 누를 때마다 선택/취소가 반복된다.|
|O or o|출력하는 필드의 정렬 순서를 변경한다.|
||아래 ‘top 항목에 대한 설명’을 참조하자.|
||대문자로 선택한 항목을 누르면 왼쪽으로 이동하고 소문자를 누르면 오른쪽으로 이동한다.|
|h or ?|사용 가능한 명령어를 출력한다.|
|k|프로세스를 종료시킨다.|
|n or #|출력할 프로세스의 수를 지정한다.|
|s|출력할 정보의 업데이트 시간을 지정한다.|
|W|~/.toprc에 설정된 내용을 저장한다.|
|q|top을 종료한다.|




### ps
___프로세스의 현재 상태를 출력한다___

#### ps [옵션]

__전체 프로세스와 관련된 옵션__
* -A : 모든 프로세스를 출력한다.
* -N : -A 옵션과 비슷하나 ps 프로세스를 제외하고 출력한다.
* -a : 세션 리더 및 터미널에 속하지 않는 프로세스를 제외하고 출력한다.
* -d : 세션 리더를 제외한 모든 프로세스를 출력한다.
* -e : 커널 프로세스를 제외한 모든 프로세스를 출력한다.

* T : 현재 터미널에서의 모든 프로세스를 출력한다.
* a : 현재 터미널의 사용자 고유 프로세스를 출력한다.
* r : 현재 실행 중인 프로세스를 출력한다.
* x : 터미널이 없는 프로세스를 출력한다.
* --deselect : -N 옵션과 같다.

__특정 프로세스를 선택하여 보여주는 옵션__
* -C : 지정한 명령어의 이름에 관련된 정보를 출력한다.
* -G : 그룹 ID에 관련된 정보를 출력한다(이름도 지원).
* -U : 사용자 ID에 관련된 정보를 출력한다(이름도 지원).
* -g : 지정한 세션 리더 혹은 그룹명에 관련한 정보를 출력한다.
* -p : 프로세스 ID를 출력한다.

* -s : 세션에 속한 프로세스를 지정한다.
* -t : tty를 지정한다.
* -u : 사용자 ID를 지정한다(이름도 지원).
* U : 지정한 사용자의 프로세스를 출력한다.
* p : 프로세스 ID를 지정한다.
* t : tty를 지정한다.

* --Group : 실제 그룹 이름이나 ID를 지정한다.
* --User : 실제 사용자 이름이나 ID를 지정한다.
* --group : 유효 사용자 이름이나 ID를 지정한다.
* --pid : 프로세스 ID를 지정한다.
* --sid : 세션 ID를 지정한다.

* --tty : 터미널을 지정한다.
* --user : 유효 사용자 이름이나 ID를 지정한다.
* -123 : --sid 123과 같은 의미이다.
* 123 : --pid 123과 같은 의미이다.

__출력 결과 필드를 제어하는 옵션__
* -0 : PID, TTY, STAT, TIME, COMMAND 등의 필드 목록을 출력한다.
* -c : PID, CLS, PRI, TTY, TIME. CMD 등의 필드 목록을 출력한다.
* -f : UID, PID, PPID, C, STIME, TTY, TIME, CMD 등의 필드를 CMD 필드의 전체 명령어 형태로 출력한다.
* -j : PID, PGID, SID, TTY, TIME, CMD 등의 필드 목록을 출력한다.
* -l : F, S, UID, PID, PPID, C, PRI, NI, ADDR, SZ, WCHAN, TTY, TIME, CMD 필드의 상세 정보를 출력한다.

* -o : 사용자가 정의한 포맷을 지정한다.
* -y : -l 이나 l 옵션과 함께 ADDR 필드를 RSS 필드로 출력한다.
* 0 : PID, TTY, STAT, IME COMMAND 필드 정보를 출력한다.
* X : PID, STACKP, ESP, EIP, TMOUT, ALARM, STAT, TTY, TIME, COMMAND 필드의 정보를 리눅스 i386 레지스터 형식으로 출력한다.

* j : PPID, PID, PGID, SID, TTY, TPGID, STAT, UID, TIME, COMMAND 필드의 정보를 작업 제어에 관련된 형식으로 출력한다.
* l : F, S, UID, PID, PPID, C, PRI, NI, ADDR, SZ, PSS, WCHAN, TTY, TIME, CMD 필드의 정보를 출력하고 -l 옵션과 함께 PSS 필드를 추가하여 출력한다.

* o : 사용자 지정 형식으로 출력한다.
* s : UID, PID, PENDING, BLOCKED, IGNORED, CAUGHT, STAT, TTY, TIME, COMMAND 필드의 정보를 출력한다.
* u : USER, PID, %CPU, %MEM, VSZ, RSS, TTY, STAT, START, TIME, COMMAND 필드의 정보를 출력한다.
* v : PID, TTY, STAT, TIME, MAJFL, TRS, DRS, RSS, %MEM, COMMAND 필드의 정보를 출력한다.
* --format : 사용자 지정 형식으로 출력한다.

__출력 필드의 내용을 변경하는 옵션__
* -H : 프로세스를 계층형으로 출력한다.
* -m : 스레드 정보를 출력한다.
* -n namelist : 시스템 이름 리스트 파일(namelist)을 지정한다.
* -w : 너비에 맞게 잘려진 내용을 제한이 없는 너비의 내용으로 상세하게 출력한다.

* --cols : 스크린의 너비를 설정한다.
* --columns : 스크린의 너비를 설정한다.
* --cumulative : 죽은 자식 프로세스 데이터를 포함하여 출력한다.
* --forest : 아스키 문자의 프로세스 트리 형태로 출력한다.
* --html : HTML 이스케이프로 출력한다.

* --headers : 헤더 라인을 반복한다.
* --no-headers : 헤더를 보이지 않는다.
* --lines : 스크린의 높이를 설정한다.
* --rows : 스크린의 높이를 설정한다.
* --sort : 정렬 방식을 지정한다. 
* --sort ＝ [+|-]key[,[+|-]key[,···] 형식으로 여기서 사용할 수 있는 키(key)는 예제에서 설명한다. 예를 들어 ps jax --sort＝uid,-ppid,+pid 형식으로 지정할 수 있다. 

* C : CPU 시간을 이용한다.
* N : 지정한 시스템 이름의 리스트 파일을 사용한다.
* O : 정렬 순서 지정하기 위한 옵션으로 O[+|-]K[,[+|-]K[,···]]의 형식으로 지정한다. K는 예제로 설명한다. +는 오름차순 정렬, –는 내림차순 정렬이다.

* S : 죽은 자식 프로세스의 데이터를 포함한다.
* c : 시스템 내부에 보관 중인 명령어 이름을 출력한다.
* e : 명령어에 대한 매개 변수와 함께 환경 변수를 출력한다.
* f : 아스키(*) 아트로 프로세스 트리를 출력한다.

* h : 헤더 라인은 출력하지 않는다.
* m : 모든 스레드 정보를 출력한다.
* n : WCHAN과 USER 필드를 숫자 값으로 출력한다.
* w : 필드의 너비에 맞게 잘려진 내용을 너비보다 상세하게 출력한다.

__프로그램의 정보__
* -V : 버전 정보를 출력한다.
* L : 모든 형태의 지시자를 출력한다.
* V : 버전 정보를 출력한다.
* --help : 사용법을 출력한다.
* --info : 디버깅 정보를 출력한다.
* --version : 버전 정보를 출력한다.





### jobs

### kill

## 2. vim 에디터에서 매크로 사용방법에 대하여 조사하기
1. 매크로 시작 = *q[name]*
2.  ...(매크로 입력)
3.  매크로 종료 = *q*
4.  매크로 실행 = *@[name]*
5.  매크로 여러번 실행 = *[number]@[name]*
