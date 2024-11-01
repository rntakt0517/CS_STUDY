# CPU와 동작 원리

## CPU의 주요 구성요소

### ALU (산술 논리 장치)

- CPU 내부의 계산 담당 **회로**
- **주요 기능**:
  - 레지스터로부터 피연산자 **수신**
  - 제어장치로부터 제어 신호 **수신**
  - 연산 수행 후 결과를 레지스터에 **저장**
  - 플래그 생성 및 플래그 레지스터에 **저장**

### 제어장치

- CPU 내부의 제어 신호 발생 및 명령어 해석 **담당**
- **주요 기능**:
  - 클럭 신호 **수신**
  - 명령어 레지스터로부터 해석할 명령어 **수신**
  - 플래그 레지스터로부터 플래그 값 **수신**
  - 외부 장치로부터 제어 신호 **수신**
  - CPU 내부 및 외부로 제어 신호 **전송**

---

### 레지스터

- CPU 내부의 임시 저장 **장치**
- **주요 종류**:
  1. **프로그램 카운터 (PC)**: 다음 실행할 명령어 주소 **저장**
  2. **명령어 레지스터 (IR)**: 현재 실행 중인 명령어 **저장**
  3. **메모리 주소 레지스터 (MAR)**: 메모리 접근 주소 **저장**
  4. **메모리 버퍼 레지스터 (MBR)**: 메모리와 주고받을 데이터 **저장**
  5. **플래그 레지스터**: 연산 결과 및 CPU 상태 정보 **저장**
  6. **범용 레지스터**: 다양한 용도로 사용 **가능**
  7. **스택 포인터 (SP)**: 스택의 최상위 주소 **저장**
  8. **베이스 레지스터**: 기준 주소 **저장**

---

## 명령어 사이클

### 기본 구조

1. **인출 사이클**: 메모리에서 명령어 **가져옴**
2. **실행 사이클**: 가져온 명령어 **실행**
3. **간접 사이클**: 추가 메모리 접근이 필요한 경우 **수행**

### 인터럽트 처리

- **인터럽트**: CPU의 정상적인 실행 흐름을 방해하는 **신호**
- 종류:
  1. **동기 인터럽트 (예외)**: CPU가 예기치 못한 상황 접했을 때 **발생**
  2. **비동기 인터럽트 (하드웨어 인터럽트)**: 주로 입출력 장치에 의해 **발생**

### 인터럽트 처리 과정

1. 입출력 장치가 CPU에 인터럽트 요청 신호 **전송**
2. CPU는 실행 사이클 종료 후 인터럽트 여부 **확인**
3. 인터럽트 플래그 확인하여 처리 가능 여부 **판단**
4. 현재 작업 상태 스택에 **백업**
5. 인터럽트 벡터 참조하여 인터럽트 서비스 루틴 **실행**
6. 인터럽트 처리 완료 후 백업된 작업 복구 및 **재개**

### 주요 개념

- **인터럽트 요청 신호**: CPU에 인터럽트 처리 **요청**
- **인터럽트 플래그**: 현재 인터럽트 처리 가능 여부 **표시**
- **인터럽트 벡터**: 인터럽트 서비스 루틴의 시작 주소 정보 **포함**
- **인터럽트 서비스 루틴**: 인터럽트 처리를 위한 **프로그램**
- **넌마스커블 인터럽트 (NMI)**: 인터럽트 플래그와 관계없이 항상 처리되는 **인터럽트**

---


