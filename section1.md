# Section 1

- 도커
  - 컨테이너를 빌드하는 도구
  - 사실상 컨테이너 표준 기술

- 컨테이너
  - 소프트웨어의 표준화된 단위
  - (= 코드 패키지)
  - (= 코드를 실행하는 데 필요한 종속성과 코드)
  - 언제나 똑같은 동작과 결과를 제공함
  - 언제나 똑같은 환경에서 똑같은 애플리케이션을 실행할 수 있음
  - 선박이나 트럭에 싣는 컨테이너 박스와 비교하는 것도 나쁜 비교는 아님
    1. 표준화된 컨테이너가 있고
    2. 다양한 화물을 컨테이너에 실을 수 있고
    3. 분리되어 있어서 다른 컨테이너의 상품과 섞이지 않고
    4. 냉각 같은 기능이 필요한 경우 컨테이너에 내장할 수 있음

- 왜 도커가 필요할까?
  - Different Developement & Production Envs
    - 로컬 환경이나 개발 환경에서 개발을 완료한 애플리케이션이 호스팅되는 프로덕션 환경을 같은 환경으로 맞추면 개발 환경과 프로덕션 환경이 달라서 발생하는 잠재적인 문제를 아예 예방할 수 있음
  - Different Development Envs Within a Team / Company
    - 프로덕션 환경 뿐만 아니라, 개발 환경이 달라서 발생하는 문제도 예방할 수 있음 ex) 같은 회사, 같은 프로젝트에서 일하는 사람들의 개발 환경
  - Clashing Tools / Versions Between Different Projects
    - 프로젝트 A와 프로젝트 B에서 같은 툴의 다른 버전을 사용할 때 발생하는 문제도 예방할 수 있음

- VM vs Docker Container
  - 공간과 리소스(CPU, Memory, HDD) 많이 사용한다 vs 공간과 리소스 적게 사용한다
  - 공유가 (가능하지만) 어렵다 vs 공유가 쉽다
  - 느리다 vs 빠르다
  - 무겁다 vs 가볍다
  - 크다 vs 작다

+) [De facto(데 팍토): 사실상](https://ko.wikipedia.org/wiki/%EB%8D%B0_%ED%8C%8D%ED%86%A0)

- 컨테이너 공유 방법
  - 컨테이너 config 파일
  - 컨테이너 이미지

- Docker on MacOS
  - (= Docker Engine, Desktop on MacOS)
  - Docker Desktop은 Deamon과 CLI를 포함함
  - 요구사항을
    - 만족하면 -> Docker Desktop
    - 만족하지 못하면 -> Docker Toolbox
- Docker Hub
- Docker Compose
- k8s

1. docker build .
2. docker images
3. docker run -p 3000:3000 {docker-image-id}
4. docker ps
5. docker stop {docker-ps-name}

6. Watch the videos at your pace
7. Code along
8. Repeat
9. Google, Stackflow
10. Ask & Answer
