# 미션1 : 내 컴퓨터에 개발자용 '작업실' 꾸미기

## 4. Docker 설치 및 기본 점검
### 4-1. Docker 버전 확인 결과를 기록한다.(docker --version)
```
C:\Users\🙌> docker --version ↩
Docker version 29.9.2, build a82e528
```
### 4-2. Docker 데몬 동작 여부 확인 결과를 기록한다. (docker info 또는 동등 점검)
데몬이 **정상동작**일 경우 Client와 Server 정보가 모두 출력된다.
```
C:\Users\🙌>docker info ↩
Client:
 Version:    29.9.2
 Context:    desktop-linux
 Debug Mode: false
 Plugins:
  agent: Docker AI Agent Runner (Docker Inc.)
    Version:  v1.152.0
    Path:     C:\Program Files\Docker\cli-plugins\docker-agent.exe
  ai: Docker AI Agent - Ask Gordon (Docker Inc.)
    Version:  v1.33.0
    Path:     C:\Program Files\Docker\cli-plugins\docker-ai.exe
  buildx: Docker Buildx (Docker Inc.)
    Version:  v0.38.1
    Path:     C:\Program Files\Docker\cli-plugins\docker-buildx.exe
  compose: Docker Compose (Docker Inc.)
    Version:  v5.6.1
    Path:     C:\Program Files\Docker\cli-plugins\docker-compose.exe
  debug: Get a shell into any image or container (Docker Inc.)
    Version:  0.49.0
    Path:     C:\Program Files\Docker\cli-plugins\docker-debug.exe
  desktop: Docker Desktop commands (Docker Inc.)
    Version:  4.97.0
    Path:     C:\Program Files\Docker\cli-plugins\docker-desktop.exe
  dhi: CLI for managing Docker Hardened Images (Docker Inc.)
    Version:  v0.0.9
    Path:     C:\Program Files\Docker\cli-plugins\docker-dhi.exe
  extension: Manages Docker extensions (Docker Inc.)
    Version:  v0.2.32
    Path:     C:\Program Files\Docker\cli-plugins\docker-extension.exe
  init: Creates Docker-related starter files for your project (Docker Inc.)
    Version:  v1.4.1
    Path:     C:\Program Files\Docker\cli-plugins\docker-init.exe
  mcp: Docker MCP Plugin (Docker Inc.)
    Version:  v0.44.2
    Path:     C:\Program Files\Docker\cli-plugins\docker-mcp.exe
  model: Docker Model Runner (Docker Inc.)
    Version:  v1.2.9
    Path:     C:\Program Files\Docker\cli-plugins\docker-model.exe
  offload: Docker Offload (Docker Inc.)
    Version:  v0.7.21
    Path:     C:\Program Files\Docker\cli-plugins\docker-offload.exe
  pass: Docker Pass Secrets Manager Plugin (beta) (Docker Inc.)
    Version:  v0.3.2
    Path:     C:\Program Files\Docker\cli-plugins\docker-pass.exe
  sandbox: "docker sandbox" is deprecated, use Docker Sandboxes instead (Docker Inc.)
    Version:  v0.13.0
    Path:     C:\Program Files\Docker\cli-plugins\docker-sandbox.exe
  scout: Docker Scout (Docker Inc.)
    Version:  v1.27.0
    Path:     C:\Program Files\Docker\cli-plugins\docker-scout.exe

Server:
 Containers: 1
  Running: 1
  Paused: 0
  Stopped: 0
 Images: 1
 Server Version: 29.9.2
 Storage Driver: overlayfs
  driver-type: io.containerd.snapshotter.v1
 Logging Driver: local
 Cgroup Driver: cgroupfs
 Cgroup Version: 2
 Plugins:
  Volume: local
  Network: bridge host ipvlan macvlan null overlay
  Log: awslogs fluentd gcplogs gelf journald json-file local splunk syslog
 CDI spec directories:
  /etc/cdi
  /var/run/cdi
 Discovered Devices:
  cdi: docker.com/gpu=webgpu
 Swarm: inactive
 Runtimes: io.containerd.runc.v2 nvidia runc
 Default Runtime: runc
 Init Binary: docker-init
 containerd version: b7a25261e029d68978bbf290df0a62fc819b3c51
 runc version: v1.5.2-0-g29dd3dc2
 init version: de40ad0
 Security Options:
  seccomp
   Profile: builtin
  cgroupns
 Kernel Version: 6.18.54.1-microsoft-standard-WSL2
 Operating System: Docker Desktop
 OSType: linux
 Architecture: x86_64
 CPUs: 24
 Total Memory: 15.25GiB
 Name: docker-desktop
 ID: 14c562e7-f906-486b-a8de-52dfae07ffc6
 Docker Root Dir: /var/lib/docker
 Debug Mode: false
 HTTP Proxy: http.docker.internal:3128
 HTTPS Proxy: http.docker.internal:3128
 No Proxy: hubproxy.docker.internal
 Labels:
  com.docker.desktop.address=npipe://\\.\pipe\docker_cli
 Experimental: false
 Insecure Registries:
  hubproxy.docker.internal:5555
  127.0.0.0/8
  ::1/128
 Live Restore Enabled: false
 Firewall Backend: iptables
```

## 5. Docker 기본 운영 명령 수행
수행명령과 출력 결과를 기술 문서에 남긴다.  

### 5-1. 이미지 : 다운로드/목록 확인(예: docker images)
```
① 이미지 다운로드
C:\Users\🙌>docker pull ubuntu ↩
Using default tag: latest
latest: Pulling from library/ubuntu
f3f25b84a7d7: Pull complete
edafa32f5d9e: Pull complete
21594acc2d8b: Download complete
Digest: sha256:6a06111c3b0a8600feadb270aec771dc239bf407b25625f93f44ab00e11f4d3c
Status: Downloaded newer image for ubuntu:latest
docker.io/library/ubuntu:latest
```
```
② 이미지 목록확인
C:\Users\🙌>docker images ↩
                                                                                                   i Info →   U  In Use
IMAGE                             ID             DISK USAGE   CONTENT SIZE   EXTRA
docker/welcome-to-docker:latest   c4d56c24da4f       22.2MB         6.03MB    U
ubuntu:latest                     6a06111c3b0a        163MB         45.9MB
```

### 5-2. 컨테이너 : 실행/중지/목록 확인(예: docker ps, docker ps -a)
① 컨테이너 실행
docker run -d -p 8080:80
② 컨테이너 중지
```
C:\Users\🙌>docker stop be269efb98d5 ↩
be269efb98d5
```
③ 컨테이너 중지전 목록 확인
```C:\Users\🙌>docker ps -a ↩
CONTAINER ID   IMAGE                             COMMAND                   CREATED       STATUS       PORTS                                     NAMES
be269efb98d5   docker/welcome-to-docker:latest   "/docker-entrypoint.…"   2 hours ago   Up 2 hours   0.0.0.0:8088->80/tcp, [::]:8088->80/tcp   welcome-to-docker
```
④ 컨테이너 중지후 목록 확인
```
C:\Users\lucidts1102>docker ps -a
CONTAINER ID   IMAGE                             COMMAND                   CREATED       STATUS                      PORTS     NAMES
be269efb98d5   docker/welcome-to-docker:latest   "/docker-entrypoint.…"   2 hours ago   Exited (0) 16 seconds ago             welcome-to-docker
```
⑤ 컨테이너 중지후 실행중인 컨테이너 확인
C:\Users\🙌>docker ps ↩
CONTAINER ID   IMAGE     COMMAND   CREATED   STATUS    PORTS     NAMES

```
### 5-3. 운영 : 로그 확인(예: docker logs), 리소스 확인(예: docker stats)
① 로그 확인

② 리소스 확인

## 6. 컨테이너 실행 실습
### 6-1. hello-world 실행 성공을 기록한다.
```
🙌@GNIA-C202-J06:/mnt/c/Users/🙌$ echo hello-world ↩
hello-world
```
### 6-2. Ubuntu 컨테이너를 실행하고 내부 진입 후 간단 명령(예: ls, echo) 수행 결과를 기록한다.
```
• Ubuntu 컨테이너를 실행하고 내부 진입명령 C:\Users\🙌> wsl -d Ubuntu-22.04 ↩
```
```
PS C:\Users\🙌> wsl -d Ubuntu-22.04 ↩
To run a command as administrator (user "root"), use "sudo <command>".
See "man sudo_root" for details.

Welcome to Ubuntu 22.04.5 LTS (GNU/Linux 6.18.54.1-microsoft-standard-WSL2 x86_64)

 * Documentation:  https://help.ubuntu.com
 * Management:     https://landscape.canonical.com
 * Support:        https://ubuntu.com/pro

 System information as of Sat Nov  7 20:18:19 KST 2026

  System load:  0.0                 Processes:             76
  Usage of /:   0.1% of 1006.85GB   Users logged in:       0
  Memory usage: 4%                  IPv4 address for eth0: 192.168.81.207
  Swap usage:   0%

  => /usr/lib/linux-tools/6.18.54.1-microsoft-standard-WSL2 is using 100.0% of
     96MB
```

```
• ls 명령실행 결과 기록 🙌@GNIA-C202-J06:/mnt/c/Users/🙌$ ls ↩
```
<img width="785" height="232" alt="image" src="https://github.com/user-attachments/assets/a451cb6a-d8d0-4486-8d2e-a64cc53c4e01" />

```
• echo 명령실행 결과 기록 🙌@GNIA-C202-J06:/mnt/c/Users/🙌$ echo hello-world ↩
```
```
hello-world
```

### 6-3. 컨테이너 종료/유지(attach/exec 등)의 차이를 스스로 관찰하고 간단히 정리한다.
```

