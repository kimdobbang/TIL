# CS 스터디 1주차

# 01장 컴퓨터 구조 시작하기

### 컴퓨터 구조에서 명령어와 데이터의 차이

**컴퓨터가 이해하는 정보: 명령어 & 데이터**

- 명령어
: 실질적으로 컴퓨터를 작동시키는 정보. 데이터를 움직이고 컴퓨터를 작동시킴
- 데이터
: 컴퓨터가 이해하는 정적인 정보 덩어리(숫자, 문자, 이미지, 영상)로서 컴퓨터와 주고받거나 저장할 수 있다.
: 컴퓨터와 주고 받는 숫자, 문자 ,이미지, 동영상과 같은 정보나 컴퓨터에 저장된 정보

### 컴퓨터의 4가지 핵심 부품

- CPU (중앙처리장치)
- 주기억장치(메모리)
- 보조기억장치
- 입출력장치
    - 참고: 메인보드 - 여러 컴퓨터 핵심 부품을 부착할 수 있는 부품(마더보드)라고도 부름

![Untitled](CS%20%E1%84%89%E1%85%B3%E1%84%90%E1%85%A5%E1%84%83%E1%85%B5%201%E1%84%8C%E1%85%AE%E1%84%8E%E1%85%A1%205f361e9dfcea45f091ddddec27906961/Untitled.png)

1. **메모리**
: **현재 실행되는 프로그램의 명령어와 데이터를 저장하는 부품.** 프로그램이 실행되려면 반드시 메모리에 저장되어 있어야함
: 실행되는프로그램의 명령어와 데이터를 저장하는 부품. 크게 RAM, ROM 두가지가 있으며, 메모리라는 용어는 보통 RAM을 지칭
주소: 메모리에 저장된 값에 빠르고 효율적으로 접근하기 위함
- 프로그램이 실행되기 위해서는 반드시 메모리에 저장되어 있어야한다.
- 메모리는 현재 실행되는 프로그램의 명령어와 데이터를 저장한다.
- 메모리에 저자된 값의 위치는 주소로 알 수 있다.
2. **CPU** (중앙처리장치)
: **메모리에 저장된 명령어를 읽어 들이고, 해석하고 실행하는 부품**
: 메모리에 저장된 명령어를 읽어 들이고, 읽어 들인 명령어를 해석하고, 실행하는 부품.
    - CPU 내부 구성 요소 중 가장 중요한 세 가지
    : 산술연산장치(ALU), 레지스터, 제어장치
    - 산술논리연산장치(ALU): 계산만을 위해 존재하는 계산기
    - 레지스터: CPU 내부의 작은 임시 저장장치 여러개
    - 제어장치: 제어신호라는 전기신호를 보내고 명령어 해석
3. **보조기억장치**
: 전원이 꺼져도 보관할 프로그램을 저장하는 부품
: 전원이 꺼져도 저장된 내용을 기억할 수 있는 장치 (HHD, SSD, USB, 메모리, DVD, CD-ROM 등)
4. **입출력장치**
    
    : 컴퓨터 외부에 연결되어 컴퓨터 내부와 정보를 교환할 수 있는 장치 (마스크, 스피커, 프린터, 마우스, 키보드 등)
    
5. **시스템 버스**
    
    : 컴퓨터의 네 가지 핵심 부품들이 서로 정보를 주고받는 통로
    : 컴퓨터 네 가지 핵심 부품(CPU, 메모리, 보조기억장치, 입출력장치)을 연결하는 가장 주요한 버스(주소 버스, 데이터 버스, 제어 버스)
    

# 02장 데이터

## 이진수로 숫자표현

- **비트**
: 0과 1로 표현할 수 있는 가장 작은 정보 단위
    - CPU가 한 번에 처리할 수 있는 데이터 크기. CPU가 처리할 수 있는 비트 수에 따라 1워드 크기 달라질 수 있음
- **바이트**
: 킬로바이트, 메가바이트, 기가바이트, 테라바이트는 비트보다 더 큰 정보단위
- **이진법**
: 1을 넘어가는 싲머에 자리 올림을 하여 0과 1만으로 수를 표현하는 방법
- 이진법 음수: **2의 보수**로 표현
    - 2의 보수는 모든 0과 1을 뒤집고 여기에 1을 더함으로써 얻을 수 있다.
- **십육진법**
: 15를 넘어가는 시점에 자리를 올림하여 수를 표현하는 방법(이진수-십육진수간 변환 용이)
    - 십육진수를 이진수로 변환할 때 십육진수 한 글자를 네 개의 이진수로 간주하면 편하다.

## 이진수로 문자표현

- **문자집합**
: 컴퓨터가 인식할 수 있는 문자의모음. 문자 집합에 속한 문자를 인코딩하여 0과 1로 표현 가능
    - 문자 인코딩: 문자 집합에 속한 문자를 컴퓨터가 이해할 수 있는 0과 1로 변환하는 것
    - 문자 디코딩: 인코딩의 반대. 0과 1로 이루어진 문자 코드를 사람이 이해할 수 있는 문자로 변환하는 것
- 아스키 문자 집합에 0부터 127까지 수가 할당되어 **아스키 코드**로 인코딩 됨
- **EUC-KR**
: 한글을 2바이트(16비트→4자리 16진수표현 가능) 크기로 인코딩할 수 있는 완성형 인코딩 방식
    
    2,350개 한글 단어 표현 가능
    
    - 표현 불가한 조합해결을 위해 EUC-KR확장버전인 **CP949 등장**

![Untitled](CS%20%E1%84%89%E1%85%B3%E1%84%90%E1%85%A5%E1%84%83%E1%85%B5%201%E1%84%8C%E1%85%AE%E1%84%8E%E1%85%A1%205f361e9dfcea45f091ddddec27906961/Untitled%201.png)

- **유니코드**
: 여러 나라의 문자들을 광범위하게 표현할 수 있는 통일된 문자 집합
    - UTF-8,  UTF-16, UTF-32는 유니코드 문자의 인코딩 방식(아스키, EUC-KR과 달리 부여된 값으로 인코딩X)
    - 모든 언어를 아우르는 문자 집합과 통일된 표준 인코딩방식
    - 특수문자, 이모티콘, 화살표 표현 가능
    - 현대 문자를 표현할 때 가장 많이사용되는 문자 집합

### 아스키코드

- 아스키코드는 7비트 → 2**7 = 128 이므로 128개의 문자 표현 가능
- 실제로는 하나의 아스키 문자를 나타내기 위해 8비트(1바이트)를 사용한다. 하지만 8비트 중 1비트는 패리티 비트라고 불리는, 오류 검출을 위해 사용되는 비트이기 때문에 실질적으로 문자 표현을 위해 사용되는 비트는 7비트.

![Untitled](CS%20%E1%84%89%E1%85%B3%E1%84%90%E1%85%A5%E1%84%83%E1%85%B5%201%E1%84%8C%E1%85%AE%E1%84%8E%E1%85%A1%205f361e9dfcea45f091ddddec27906961/Untitled%202.png)