1. 캐시의 적중률을 높이기 위해서 고려해야할 지역성의 원리에는 무엇이 있는가?

- 공간적 지역성: 참조한 주소와 인접한 주소를 참조할 가능성이 높은 특성. 순차적 프로그램 수행 시, 메모리 상 인접한 곳에 위치한 다음 명령어를 수행한다.
- 시간적 지역성: 한 번 참조한 주소를 곧 다시 참조하는 특성. for문 실행 시, 같은 명령어를 반복해서 수행한다.

2. 프로세스와 프로그램의 차이는 무엇인가?

- 프로그램: 아직 시스템에 실행 요청이 이루어지지 않은 상태의 실행 파일(명령어 집합)
- 프로세스: 실행을 위해 시스템(커널)에 등록되거나 실행되고 있는 프로그램
