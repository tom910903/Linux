# Linux System Programming

- [1장. **기본 명령어**](#1장.-기본-명령어)
  * [로그인/로그아웃 명령어](#로그인/로그아웃-명령어)
  * [파일/디렉터리 명령어](#파일/디렉터리-명령어)
  * [프로세스 명령어](#프로세스-명령어)
  * [기타 명령어](#기타-명령어)

### 1장. **기본 명령어**
#### 로그인/로그아웃 명령어
|명령어|기능|주요 옵션|
|:--:|:--:|:--:|
|telnet|리눅스 시스템에 접속|-|
|ssh|리눅스 시스템에 접속|-|
|exit|리눅스 시스템 접속 해제|-|
|logout|리눅스 시스템 접속 해제|-|
<br>

#### 파일/디렉터리 명령어
|명령어|기능|주요 옵션|
|:--:|:--:|:--:|
|pwd|현재 디렉터리 경로 출력|-|
|ls|디렉터리 내용 출력|-a: 숨김 파일 출력<br>-l: 파일 상세정보 출력|
|cd|디렉터리 이동|-|
|cp|파일복사<br>폴더 복사|<br>-r|
|mv|파일명/디렉터리명 변경<br>파일/디렉터리 이동|-|
|rm|파일삭제<br>디렉터리 삭제|<br>-r|
|mkdir|디렉터리 생성|-|
|rmdir|빈 디렉터리 삭제|-|
|cat|파일 내용 출력|-|
|more|화면 크기 단위로 파일 내용 출력|-|
|chmod|파일/디렉터리 접근 권한 변경|-|
|grep|패턴 검색|-|
<br>

#### 프로세스 명령어
|명령어|기능|주요 옵션|
|:--:|:--:|:--:|
|ps|현재 실행중인 프로세스 정보 출력|-ef: 모든 프로세스의 상세 정보 출력|
|kill|프로세스 강제 종료|-9: 강제 종료|
|top|실시간 CPU 사용률 확인|-|
<br>

#### 기타 명령어
|명령어|기능|주요 옵션|
|:--:|:--:|:--:|
|su|사용자 계정 변경|-: 변경할 사용자의 환경 초기화 파일 실행|
|tar|cvf<br>tvf<br>xvf|tar파일 생성<br>tar파일 내용 보기<br>tar파일 풀기|
|whereis|파일 위치 검색|-|
|which|파일 위치 검색|-|
<br>

#### 컴파일러
컴파일: 작성한 프로그램을 기계어로 변환하는 과정
> 프로그램 작성 &#8594; 컴파일 &#8594; 라이브러리 링크 &#8594; 실행파일

GNU C 컴파일러: gcc
|형식|gcc[옵션][파일명]|
|:--:|:--:|
|옵션|-c : 오브젝트 파일(.o)만 생성<br>-o 실행 파일명 : 지정한 이름으로 실행 파일 생성|


#### Makefile/make
Makefile은 컴파일 명령, 컴파일 방법, 링크할 파일, 실행 파일명등을 설정하는 파일.  
make 명령은 Makefile을 읽고 파일에서 지정한 대로 컴파일을 실행함.

// TO-DO : Makefile 명령어 정리

#### 오류 처리 함수
기본적으로 시스템 함수는 오류 발생시 -1을 return.  
라이브러리 함수는 오류 발생시 NULL을 return.

perror(),strerror() 함수는 오류 코드를 메시지로 변환해 출력 함.
|perror()|에러 메시지를 표준 출력으로 출력함|
|--|--|
|strerror()|에러 메시지를 return함|  

#### 메모리 할당

|void *malloc(size_t size)|size만큼의 메모리를 할당|
|--|--|
|void *calloc(size_t nmemb, size_t size)|nmemb * size만큼의 메모리를 할당함|
|void *realloc(void *ptr, size_t size)|할당 받은 메모리에 추가로 메모리를 할당함<br>이전 메모리와 추가 메모리의 합친 크기의 메모리를 할당하고 그 주소에 이전 메모리의 내용을 복사|

#### 명령행 인자
int main(int argc, char *argv[])  
argc - 명령과 인자를 포함한 개수(argv 배열의 크기)  
argv - 명령과 각 인자를 담고있는 배열


참고 사이트 [GitHub Markdown](https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax)