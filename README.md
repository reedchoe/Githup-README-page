# 리눅스 명령어 top, ps, jobs, kill 명령어 조사
###### 20233082최건도

## 1. top 명령어

### 사용 구문
- `top [option]`
- `top -b` : 순간의 정보 확인 가능
- `top -n` (number) : top 실행 주기를 (number)번 반복 가능

### 사용 예시
- shift + p : CPU 사용률 내림차순
- shift + m : 메모리 사용률 내림차순
- shift + t : 프로세서가 돌아가고 있는 시간 순
- k : kill. k 입력 후 PID번호 작성. signal은 9
- f : sort field 입력화면 -> q 누르면 RES 순으로 정렬
- a : 메모리 사용량에 따라 정렬
- b : Batch 모드로 작동
- 1 : CPU Core 별로 사용량 보여줌

### 활용
시스템의 사용량을 실시간으로 확인할 수 있음

## 2. ps 명령어

### 사용 구문
- `ps [option]` : pid, cmd 등 프로세스의 기본적인 내용만 출력

### 사용 예시
- `ps -e` : 모든 프로세서 출력
- `ps -f` : 풀 포맷으로 출력
- `ps -l` : 긴 포맷으로 출력
- `ps -p (number)` : 프로세스 번호가 (number)인 프로세스 출력
- `ps -u (account name)` : 계정이 (account name)인 프로세스 출력
- `ps -ef | more` : 모든 프로세스를 풀 포맷으로 출력, more 명령어를 이용하여 페이지 단위로 출력
- `ps -ef | grep (account name)` : 모든 프로세스를 풀 포맷으로 출력한 목록에서 grep을 활용해 (account name)이 포함된 행 출력 

### 활용
현재 실행중인 프로세스 목록을 확인할 수 있음

## 3. jobs 명령어

### 사용 구문
- `jobs [option] [number]` : (number)번의 작업의 상태를 표시

### 사용 예시
- `-l` : 프로세스 그룹의 아이디를 state 필드 앞에 출력
- `-n` : 프로세스 그룹 중 대표 프로세스 아이디를 출력
- `-p` : 각 프로세스 아이디에 대해 한 행씩 출력
- `command` : 지정한 명령어 실행

### 상태값
|   상태   |       설명       |
|---------|-----------------|
| Running | 작업이 계속 진행중임 |
| Done | 작업이 완료되어 0으로 반환 |
| Done(code) | 작업이 종료되었으며 0이 아닌 코드로 반환|
| Stopped | 작업이 일시 중단 |
| Stopped(SIGTSTP) | SIGTSTP 시그널이 작업을 일시 중단 |
| Stopped(SIGSTOP) | SIGSTOP 시그널이 작업을 일시 중단 |
| Stopped(SIGTTIN) | SIGTTIN 시그널이 작업을 일시 중단 |
| Stopped(SIGTTOU) | SIGTTOU 시그널이 작업을 일시 중단 |

## 4. kill 명령어

### 사용 구문
- `kill [option] [pid]`

### 사용 예시
- `kill 12345` : pid가 12345인 프로세스를 종료
- `kill -9 ` or `-SIGKILL 12345` : pid가 12345인 프로세스를 강제로 종료
- `kill -l` : kill 명령어를 지원하는 시그널 목록을 출력

### 활용
대개 프로세스를 없앨 때 실행하지만, 원래는 프로세스에 시그널을 보내기 위한 작업을 하게 하는 명령어이다
