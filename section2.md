# Section 2

- Images & Containers
- Using Pre-Built & Custom Images
- Creating & Managing Containers

## Images & Containers

- Images
  - Templates/Blueprints for containers
  - Contains code + required tools/runtimes
- Containers
  - The running unit of software

### Pre-built Images

- Docker Hub
  - ex) docker run node
    - docker ps -a
    - container created but not exposed to us
  - ex) docker run -it node
    - container created and exposed to us

- Error: `Cannot connect to the Docker daemon at unix:///var/run/docker.sock.`
  - Solution: Run "Docker Desktop"

- Image instance = Concrete container based on image

### Custom

- Install VSCode Extension "Docker"
- `WORKDIR` 설정시 `COPY` 에서 작성하는 컨테이너 내부 경로 기준이 되고, `RUN` 으로 작성한 명령어가 해당 작업디렉터리 내에서 실행됨
  - 설정하지 않으면 루트디렉터리 내에서 실행됨
- `RUN` 이미지가 생성될때 실행되는 명령어
- `CMD` 이미지를 기반으로 컨테이너가 실행될때 실행되는 명령어
- `CMD` 는 언제나 Dockerfile 맨 마지막줄에 위치해야함
- `docker build .`
- `docker run -p 3000:80 {image-id}`
  - `EXPOSE 80` 은 어떤 역할도 하지 않음
- 도커에서 ID를 사용할 땐, 고유한 식별자라는 조건만 만족하면 한 글자만 써도 됨
- `docker run hello-world`
- `docker run -it ubuntu bash`

- 코드 수정사항을 이미지에 실시간으로 반영할 수 없음
  - 이미지가 빌드되는 시점에 스냅샷이 찍히기 때문
  - 이미지는 read-only(읽기 전용)
- Dockerfile의 한줄한줄이 레이어가 됨
  - 이미지를 재빌드할 때 Dockerfile이 변경되지 않았으면 캐시된 레이어를 사용해서 빌드를 빠르게 함
  - 하나의 레이어가 바뀌면(파일 하나 변경 -> COPY 레이어에 영향을 줌) 그 이후 레이어도 모두 다시 실행됨
    - 도커는 이전 레이어에서 생긴 변경사항이 이후 레이어에 끼치는 영향에 대해 깊은 분석을 하지 않음
  - 따라서 `RUN npm install` -> `COPY . /app` 순서로 재배치해서 최적화가 가능함
