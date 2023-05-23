# 리눅스 명령어 top, ps, jobs, kill 명령어 조사

## 1. top 명령어

### 사용 구문
- `top [option]`
- `top -b` : 순간의 정보 확인 가능
- `top -n` (number) : top 실행 주기를 (number)번 반복 가능

### top 실행 후 명령어
- `shift + p` : CPU 사용률 내림차순
- `shift + m` : 메모리 사용률 내림차순
- `shift + t` : 프로세서가 돌아가고 있는 시간 순
- k : kill. k 입력 후 PID번호 작성. signal은 9
- f : sort field 입력화면 -> q 누르면 RES 순으로 정렬
- a : 메모리 사용량에 따라 정렬
- b : Batch 모드로 작동
- 1 : CPU Core 별로 사용량 보여줌

## 2. ps 명령어

## 3. jobs 명령어

## 4. kill 명령어
