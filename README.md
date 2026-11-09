# 미션1 : 내 컴퓨터에 개발자용 '작업실' 꾸미기

## 1. 실행환경
- OS : Ubuntu
- Shell : bash
- Docker : 29.9.2
- Git : 2.56.0.windows.4

## 2. 수행 항목 체크LIST

- [x] Terminal 기본 명령어 실습
- [x] 권한 확인 및 변경 실습
- [x] Docker 설치 및 기본 점검
- [x] Dockerfile 기본 운영 명령 수행
- [x] 포트 매핑 접속
- [x] 바인드 마운트 반영
- [x] 볼륨 영속성
- [x] Git 설정
- [x] VSCode GitHub 연동

## 3. 터미널 조작 로그
### 리눅스 터미널(Ubuntu)로 명령어를 수행한 출력결과 정리

### 3-1. 현재 위치 확인
```
🙌@GNIA-C202-J06:/mnt/c/Users/🙌$ pwd ↩
/mnt/c/Users/🙌
```

### 3-2. 목록확인(숨김 파일 포함)
```
🙌@GNIA-C202-J06:/mnt/c/Users/🙌$ ls -a ↩
 .                    NTUSER.DAT
 ..                   NTUSER.DAT{1f84748c-b1a2-11f1-8248-b082e2ec90c3}.TM.blf
 .config              NTUSER.DAT{1f84748c-b1a2-11f1-8248-b082e2ec90c3}.TMContainer00000000000000000001.regtrans-ms
 .copilot             NTUSER.DAT{1f84748c-b1a2-11f1-8248-b082e2ec90c3}.TMContainer00000000000000000002.regtrans-ms
 .docker              NetHood
 .git                 Pictures
 .lesshst             PrintHood
 .vscode              Recent
 .vscode-shared       'Saved Games'
 AppData              Searches
 'Application Data'   SendTo
 Contacts             Templates
 Cookies              Test261104
 Desktop              Videos
 Documents            ntuser.dat.LOG1
 Downloads            ntuser.dat.LOG2
 Favorites            ntuser.ini
 Links                practice
 'Local Settings'     test1.txt
 Music                vscode-remote-wsl
 'My Documents'       ''$'\354\213\234\354\236\221'' '$'\353\251\224\353\211\264'
```

### 3-3. 이동(폴더)
```
🙌@GNIA-C202-J06:/mnt/c/Users/🙌$ cd .. ↩ 🙌$의 상위폴더로 이동
🙌@GNIA-C202-J06:/mnt/c/Users$ cd ~ ↩ 현사용자의 홈 디렉토리로 이동
🙌@GNIA-C202-J06:~$ cd /mnt/c/Users/🙌 ↩ /mnt/c/Users/🙌$로 이동
🙌@GNIA-C202-J06:/mnt/c/Users/🙌$
```

### 3-4. 생성(폴더)
```
🙌@GNIA-C202-J06:/mnt/c/Users/🙌$ mkdir AllinONE ↩ 현재 폴더에 AllinONE 폴더 생성
🙌@GNIA-C202-J06:/mnt/c/Users/🙌$ ls ↩ 현재 폴더 목록을 조회해서 mkdir 결과 확인
 AllinONE
 AppData
 'Application Data'
 Contacts
 Cookies
 Desktop
 Documents
 Downloads
 Favorites
 Links
 'Local Settings'
 Music
 'My Documents'
 NTUSER.DAT
 NTUSER.DAT{1f84748c-b1a2-11f1-8248-b082e2ec90c3}.TM.blf
 NTUSER.DAT{1f84748c-b1a2-11f1-8248-b082e2ec90c3}.TMContainer00000000000000000001.regtrans-ms
 NTUSER.DAT{1f84748c-b1a2-11f1-8248-b082e2ec90c3}.TMContainer00000000000000000002.regtrans-ms
(생략)
```

### 3-5. 복사
```
🙌@GNIA-C202-J06:/mnt/c/Users/🙌$ cp test1.txt test2.txt ↩
🙌@GNIA-C202-J06:/mnt/c/Users/🙌$ ls ↩
(생략)
 test1.txt
 test2.txt
 vscode-remote-wsl
 ''$'\354\213\234\354\236\221'' '$'\353\251\224\353\211\264'
복사된 파일과 원본 파일의 내용확인
🙌@GNIA-C202-J06:/mnt/c/Users/🙌$ cat test1.txt
��Welcome AllinOne!

🙌@GNIA-C202-J06:/mnt/c/Users/🙌$ cat test2.txt
��Welcome AllinOne!

```

### 3-6. 파일 이동/이름변경
```
파일 원본 조회
🙌@GNIA-C202-J06:/mnt/c/Users/🙌$ ls ↩
 AllinONE
 AppData
(생략)
 practice
 test1.txt
 test2.txt
 vscode-remote-wsl
 ''$'\354\213\234\354\236\221'' '$'\353\251\224\353\211\264'
파일 이동/이름변경(test1.txt 파일을 test3.txt로 내용 이동 및 파일명 변경)
🙌@GNIA-C202-J06:/mnt/c/Users/🙌$ mv test3.txt test1.txt ↩
파일 이동/이름변경 상황 조회
🙌@GNIA-C202-J06:/mnt/c/Users/🙌$ ls ↩
 AllinONE
 AppData
(생략)
 practice
 test2.txt
 test3.txt
 vscode-remote-wsl
 ''$'\354\213\234\354\236\221'' '$'\353\251\224\353\211\264'
```

### 3-7. 삭제
```
🙌@GNIA-C202-J06:/mnt/c/Users/🙌$ rm test2.txt ↩
🙌@GNIA-C202-J06:/mnt/c/Users🙌$ ls ↩
 AllinONE
 AppData
(생략)
 practice
 test1.txt
 vscode-remote-wsl
 ''$'\354\213\234\354\236\221'' '$'\353\251\224\353\211\264'
```

### 3-8. 파일내용확인
```
🙌@GNIA-C202-J06:/mnt/c/Users/🙌$ cat test1.txt ↩
��Welcome AllinOne!
```

### 3-9. 빈 파일 생성
```
🙌@GNIA-C202-J06:/mnt/c/Users/🙌$ touch test.txt ↩
🙌@GNIA-C202-J06:/mnt/c/Users/🙌$ ls ↩
 AllinONE
 AppData
(생략)
 practice
 test.txt
 test1.txt
 vscode-remote-wsl
 ''$'\354\213\234\354\236\221'' '$'\353\251\224\353\211\264'
🙌@GNIA-C202-J06:/mnt/c/Users/🙌$ cat test.txt ↩
🙌@GNIA-C202-J06:/mnt/c/Users/🙌$
```
## 4. 권한 실습 및 증거 기록
최소 요구 : 파일 1개(test.txt), 디렉토리 1개(AllinONE)에 대해 권한 변경 실험을 수행
### 4-1. 권한을 확인/변경하는 명령을 수행
```
• 권한 확인
🙌@GNIA-C202-J06:~$ pwd ↩
/home/🙌
🙌@GNIA-C202-J06:~$ ls -al ↩
total 32
drwxr-x--- 4 🙌 🙌 4096 Nov  8 02:31 .
drwxr-xr-x 3 root        root        4096 Nov  8 01:58 ..
-rw------- 1 🙌 🙌  775 Nov  8 05:08 .bash_history
-rw-r--r-- 1 🙌 🙌  220 Nov  8 01:58 .bash_logout
-rw-r--r-- 1 🙌 🙌 3771 Nov  8 01:58 .bashrc
drwxr-x--- 4 🙌 🙌 4096 Nov  8 01:59 .cache
drwxr-x--- 3 🙌 🙌 4096 Nov  8 01:59 .config
-rw-rw-r-- 1 🙌 🙌    0 Nov  9 20:32 .motd_shown
-rw-r--r-- 1 🙌 🙌  807 Nov  8 01:58 .profile
🙌@GNIA-C202-J06:~$ mkdir AllinONE ↩
🙌@GNIA-C202-J06:~$ ls -l ↩
total 4
drwxr-xr-x 2 🙌2 🙌 4096 Nov  9 20:50 AllinONE
🙌@GNIA-C202-J06:~$ cd AllinONE ↩ 폴더 만들고
🙌@GNIA-C202-J06:~/AllinONE$ ls ↩ 빈 폴더에
🙌@GNIA-C202-J06:~/AllinONE$ touch test.txt ↩ test.txt 빈 파일 생성
🙌@GNIA-C202-J06:~/AllinONE$ ls -l ↩ 폴더내 파일 조회
total 0
-rw-r--r-- 1 🙌 🙌 0 Nov  9 20:52 test.txt

• 권한 변경(디렉토리AllinONE 권한을 755에서 765로 변경해 보기)
🙌@GNIA-C202-J06:~$ ls ↩
AllinONE
🙌@GNIA-C202-J06:~$ ls -l ↩
total 4
drwxr-xr-x 2 🙌 🙌 4096 Nov  9 20:52 AllinONE
🙌@GNIA-C202-J06:~$ chmod 765 AllinONE ↩ AllinONE 폴더의 권한 모드를 765로 변경
🙌@GNIA-C202-J06:~$ ls -l ↩
total 4
drwxrw-r-x 2 🙌 🙌 4096 Nov  9 20:52 AllinONE

• 권한 변경(test.txt 파일에 대한 권한을 644에서 744로 변경해 보기)
🙌@GNIA-C202-J06:~$ cd AllinONE ↩
🙌@GNIA-C202-J06:~/AllinONE$ ls -l ↩
total 0
-rw-r--r-- 1 🙌 🙌 0 Nov  9 20:52 test.txt
🙌@GNIA-C202-J06:~/AllinONE$ chmod 744 test.txt ↩
🙌@GNIA-C202-J06:~/AllinONE$ ls -l ↩
total 0
-rwxr--r-- 1 🙌 🙌 0 Nov  9 20:52 test.txt

• 권한 변경(빈 파일test1.txt 생성하여 test.txt와 test1.txt를 같은 권한으로 변경해 보기)
🙌@GNIA-C202-J06:~/AllinONE$ ls ↩
test.txt
🙌@GNIA-C202-J06:~/AllinONE$ touch test1.txt ↩ test1.txt 빈파일 생성
🙌@GNIA-C202-J06:~/AllinONE$ ls -l ↩
total 0
-rwxr--r-- 1 🙌 🙌 0 Nov  9 20:52 test.txt
-rw-r--r-- 1 🙌 🙌 0 Nov  9 23:14 test1.txt
🙌@GNIA-C202-J06:~/AllinONE$ chmod --reference=test.txt test1.txt ↩ test.txt와 test1.txt를 같은 권한으로 변경
🙌@GNIA-C202-J06:~/AllinONE$ ls -l ↩
total 0
-rwxr--r-- 1 🙌 🙌 0 Nov  9 20:52 test.txt
-rwxr--r-- 1 🙌 🙌 0 Nov  9 23:14 test1.txt
```
### 4-2. 권한변경 전/후 비교하기
```
• chmod -v옵션으로 test.txt 파일에 대한 변경전 권한과 변경후 권한을 메시지로 확인
🙌@GNIA-C202-J06:~/AllinONE$  chmod -v 751 test.txt ↩ 권한모드를 751로 바꾸면서 변경 전/후 나타냄
mode of 'test.txt' changed from 0744 (rwxr--r--) to 0751 (rwxr-x--x)
```

## 5. Docker 설치 및 기본 점검
### 5-1. Docker 버전 확인 결과를 기록한다.(docker --version)
```
C:\Users\🙌>docker version ↩
Client:
 Version:           29.9.2
 API version:       1.56
 Go version:        go1.26.10
 Git commit:        a82e528
 Built:             Tue Oct 20 19:44:07 2026
 OS/Arch:           windows/amd64
 Context:           desktop-linux

Server: Docker Desktop 4.97.0 (244584)
 Engine:
  Version:          29.9.2
  API version:      1.56 (minimum version 1.40)
  Go version:       go1.26.10
  Git commit:       0367cbe
  Built:            Tue Oct 20 18:45:02 2026
  OS/Arch:          linux/amd64
  Experimental:     false
 containerd:
  Version:          v2.4.2
  GitCommit:        b7a25261e029d68978bbf290df0a62fc819b3c51
 runc:
  Version:          1.5.2
  GitCommit:        v1.5.2-0-g29dd3dc2
 docker-init:
  Version:          0.19.0
  GitCommit:        de40ad0
```
### 5-2. Docker 데몬 동작 여부 확인 결과를 기록한다. (docker info 또는 동등 점검)
데몬이 **정상동작**일 경우 Client와 Server 정보가 모두 출력된다.
```
C:\Users\🙌>docker version ↩
Client:
 Version:           29.9.2
 API version:       1.56
 Go version:        go1.26.10
 Git commit:        a82e528
 Built:             Tue Oct 20 19:44:07 2026
 OS/Arch:           windows/amd64
 Context:           desktop-linux

Server: Docker Desktop 4.97.0 (244584)
 Engine:
  Version:          29.9.2
  API version:      1.56 (minimum version 1.40)
  Go version:       go1.26.10
  Git commit:       0367cbe
  Built:            Tue Oct 20 18:45:02 2026
  OS/Arch:          linux/amd64
  Experimental:     false
 containerd:
  Version:          v2.4.2
  GitCommit:        b7a25261e029d68978bbf290df0a62fc819b3c51
 runc:
  Version:          1.5.2
  GitCommit:        v1.5.2-0-g29dd3dc2
 docker-init:
  Version:          0.19.0
  GitCommit:        de40ad0

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
 Containers: 6
  Running: 0
  Paused: 0
  Stopped: 6
 Images: 5
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

## 6. Docker 기본 운영 명령 수행
수행명령과 출력 결과를 기술 문서에 남긴다.  

### 6-1. 이미지 : 다운로드/목록 확인(예: docker images)

① 이미지 다운로드

```
C:\Users\🙌>docker pull ubuntu ↩
Using default tag: latest
latest: Pulling from library/ubuntu
Digest: sha256:6a06111c3b0a8600feadb270aec771dc239bf407b25625f93f44ab00e11f4d3c
Status: Image is up to date for ubuntu:latest
docker.io/library/ubuntu:latest
```

② 이미지 목록확인
```
C:\Users\🙌>docker images ↩
                                                                                                   i Info →   U  In Use
IMAGE                             ID             DISK USAGE   CONTENT SIZE   EXTRA
docker/welcome-to-docker:latest   c4d56c24da4f       22.2MB         6.03MB    U
hello-world:latest                c567b231f656       25.9kB         9.49kB    U
nginx:latest                      165ddde8751e        243MB         66.8MB    U
python:latest                     8c9a3bf2d6de       1.65GB          437MB    U
ubuntu:latest                     6a06111c3b0a        163MB         45.9MB    U
```
### 6-2. 컨테이너 : 실행/중지/목록 확인(예: docker ps, docker ps -a)
```
① 컨테이너 실행
🙌2@GNIA-C202-J06:~$ docker run -d --name welcome-to-docker -p 8088:80 nginx ↩
b73b20e8498ed0e7e278e506306f0b84908a375c798f17be52643bfcd9ecbcc5

② 컨테이너 중지전 목록 확인
🙌@GNIA-C202-J06:~$ docker ps -a ↩ 모든 목록 확인중b73b20e8498e의 status가 Up상태임을 확인
CONTAINER ID   IMAGE     COMMAND                  CREATED         STATUS                      PORTS                                     NAMES
b73b20e8498e   nginx     "/docker-entrypoint.…"   7 minutes ago   Up 7 minutes                0.0.0.0:8088->80/tcp, [::]:8088->80/tcp   welcome-to-docker
e38c12e8bc33   nginx     "/docker-entrypoint.…"   2 hours ago     Exited (0) 10 seconds ago                                             test-container
③ 컨테이너 중지
🙌@GNIA-C202-J06:~$ docker stop welcome-to-docker ↩ welcome-to-docker라는 명칭의 컨테이너 중지
welcome-to-docker

④ 컨테이너 중지후 목록 확인
🙌@GNIA-C202-J06:~$ docker ps -a ↩ status가 Exited (0)인 중지컨테이너를 포함한 모든 목록 확인
CONTAINER ID   IMAGE     COMMAND                  CREATED          STATUS                      PORTS     NAMES
b73b20e8498e   nginx     "/docker-entrypoint.…"   10 minutes ago   Exited (0) 21 seconds ago             welcome-to-docker
e38c12e8bc33   nginx     "/docker-entrypoint.…"   2 hours ago      Exited (0) 3 minutes ago              test-container

⑤ 컨테이너 중지후 실행중인 컨테이너 확인  
🙌@GNIA-C202-J06:~$ docker ps ↩ 현재 실행중인 컨테어너 목록 확인
CONTAINER ID   IMAGE     COMMAND   CREATED   STATUS    PORTS     NAMES
```

### 6-3. 운영 : 로그 확인(예: docker logs), 리소스 확인(예: docker stats)
```
① 로그 확인
🙌@GNIA-C202-J06:~$ docker logs test-container ↩
/docker-entrypoint.sh: /docker-entrypoint.d/ is not empty, will attempt to perform configuration
/docker-entrypoint.sh: Looking for shell scripts in /docker-entrypoint.d/
/docker-entrypoint.sh: Launching /docker-entrypoint.d/10-listen-on-ipv6-by-default.sh
10-listen-on-ipv6-by-default.sh: info: Getting the checksum of /etc/nginx/conf.d/default.conf
10-listen-on-ipv6-by-default.sh: info: Enabled listen on IPv6 in /etc/nginx/conf.d/default.conf
/docker-entrypoint.sh: Sourcing /docker-entrypoint.d/15-local-resolvers.envsh
/docker-entrypoint.sh: Launching /docker-entrypoint.d/20-envsubst-on-templates.sh
/docker-entrypoint.sh: Launching /docker-entrypoint.d/30-tune-worker-processes.sh
/docker-entrypoint.sh: Configuration complete; ready for start up
2026/11/09 18:25:54 [notice] 1#1: using the "epoll" event method
2026/11/09 18:25:54 [notice] 1#1: nginx/1.31.8
2026/11/09 18:25:54 [notice] 1#1: built by gcc 14.2.0 (Debian 14.2.0-19)
2026/11/09 18:25:54 [notice] 1#1: OS: Linux 6.18.54.1-microsoft-standard-WSL2
2026/11/09 18:25:54 [notice] 1#1: getrlimit(RLIMIT_NOFILE): 1048576:1048576
2026/11/09 18:25:54 [notice] 1#1: start worker processes
2026/11/09 18:25:54 [notice] 1#1: start worker process 29
2026/11/09 18:25:54 [notice] 1#1: start worker process 30
2026/11/09 18:25:54 [notice] 1#1: start worker process 31
2026/11/09 18:25:54 [notice] 1#1: start worker process 32
2026/11/09 18:25:54 [notice] 1#1: start worker process 33
2026/11/09 18:25:54 [notice] 1#1: start worker process 34
2026/11/09 18:25:54 [notice] 1#1: start worker process 35
2026/11/09 18:25:54 [notice] 1#1: start worker process 36
2026/11/09 18:25:54 [notice] 1#1: start worker process 37
2026/11/09 18:25:54 [notice] 1#1: start worker process 38
2026/11/09 18:25:54 [notice] 1#1: start worker process 39
2026/11/09 18:25:54 [notice] 1#1: start worker process 40
2026/11/09 18:25:54 [notice] 1#1: start worker process 41
2026/11/09 18:25:54 [notice] 1#1: start worker process 42
2026/11/09 18:25:54 [notice] 1#1: start worker process 43
2026/11/09 18:25:54 [notice] 1#1: start worker process 44
2026/11/09 18:25:54 [notice] 1#1: start worker process 45
2026/11/09 18:25:54 [notice] 1#1: start worker process 46
2026/11/09 18:25:54 [notice] 1#1: start worker process 47
2026/11/09 18:25:54 [notice] 1#1: start worker process 48
2026/11/09 18:25:54 [notice] 1#1: start worker process 49
2026/11/09 18:25:54 [notice] 1#1: start worker process 50
2026/11/09 18:25:54 [notice] 1#1: start worker process 51
2026/11/09 18:25:54 [notice] 1#1: start worker process 52

② 리소스 확인
🙌@GNIA-C202-J06:~$ docker stats ↩
CONTAINER ID   NAME             CPU %     MEM USAGE / LIMIT     MEM %     NET I/O        BLOCK I/O       PIDS
e38c12e8bc33   test-container   0.00%     28.18MiB / 15.25GiB   0.18%     1.3kB / 126B   19MB / 16.4kB   26
Ctrl+C ↩ test-container에서 빠져나오기
```

## 7. 컨테이너 실행 실습
### 7-1. hello-world 실행 성공을 기록한다.
```
🙌@GNIA-C202-J06:/mnt/c/Users/🙌$ echo hello-world ↩
hello-world
```
### 7-2. Ubuntu 컨테이너를 실행하고 내부 진입 후 간단 명령(예: ls, echo) 수행 결과를 기록한다.

• Ubuntu 컨테이너를 실행하고 내부 진입명령C:\Users\🙌> wsl -d Ubuntu ↩
```
PS C:\Users\🙌> wsl -d Ubuntu ↩
To run a command as administrator (user "root"), use "sudo <command>".
See "man sudo_root" for details.

Welcome to Ubuntu LTS (GNU/Linux 6.18.54.1-microsoft-standard-WSL2 x86_64)

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

• ls 명령실행 결과 기록
```
🙌@GNIA-C202-J06:/mnt/c/Users/🙌$ ls ↩
<img width="785" height="232" alt="image" src="https://github.com/user-attachments/assets/a451cb6a-d8d0-4486-8d2e-a64cc53c4e01" />

```
• echo 명령실행 결과 기록
```
🙌@GNIA-C202-J06:/mnt/c/Users/🙌$ echo hello-world ↩
hello-world
```

### 7-3. 컨테이너 종료/유지(attach/exec 등)의 차이를 스스로 관찰하고 간단히 정리한다.
컨테이너 docker exec 실행시 컨테이너 목록을 조회해 보면 STATUS가 Up 상태임.
```
C:\Users\🙌>docker exec -it temp-container bash ↩
root@b0bb823b1b27:/# exit ↩
C:\Users\🙌>docker ps ↩
CONTAINER ID   IMAGE     COMMAND                   CREATED          STATUS          PORTS                                     NAMES
b0bb823b1b27   ubuntu    "bash"                    40 minutes ago   Up 40 minutes                                             temp-container
```
컨테이너 docker attach 실행시 컨테이너 목록을 조회해 보면 STATUS가 Exited상태임.
```
C:\Users\🙌>docker attach temp-container ↩
root@b0bb823b1b27:/# exit ↩
exit

C:\Users\🙌>docker ps -a ↩
CONTAINER ID   IMAGE                             COMMAND                   CREATED          STATUS                          PORTS                                     NAMES
b0bb823b1b27   ubuntu                            "bash"                    51 minutes ago   Exited (0) About a minute ago                                             temp-container
```
## 8. 기존 Dockerfile 기반 커스텀 이미지 제작


## 9. 포트 매핑 및 접속 증거

```
🙌@GNIA-C202-J06:~$ docker ps -a ↩
CONTAINER ID   IMAGE     COMMAND                  CREATED       STATUS         PORTS                                     NAMES
b73b20e8498e   nginx     "/docker-entrypoint.…"   2 hours ago   Up 8 minutes   0.0.0.0:8088->80/tcp, [::]:8088->80/tcp   welcome-to-docker
e38c12e8bc33   nginx     "/docker-entrypoint.…"   4 hours ago   Up 8 minutes   0.0.0.0:8080->80/tcp, [::]:8080->80/tcp   test-container
🙌@GNIA-C202-J06:~$ curl -v http://localhost:8080 ↩ -v 옵션을 사용하면 요청(Request)과 응답(Response) 과정을 모두 볼 수 있어 포트 매핑이 성공했다는 강력한 증거
* Host localhost:8080 was resolved.
* IPv6: ::1
* IPv4: 127.0.0.1
*   Trying [::1]:8080...
* Established connection to localhost (::1 port 8080) from ::1 port 44130
* using HTTP/1.x
> GET / HTTP/1.1
> Host: localhost:8080
> User-Agent: curl/8.18.0
> Accept: */*
>
* Request completely sent off
< HTTP/1.1 200 OK   <-- 연결 성공 확인!
< Server: nginx/1.31.8
< Date: Mon, 09 Nov 2026 22:08:20 GMT
< Content-Type: text/html
< Content-Length: 896
< Last-Modified: Wed, 21 Oct 2026 14:24:51 GMT
< Connection: keep-alive
< ETag: "6ad8cb33-380"
< Accept-Ranges: bytes
<
<!DOCTYPE html>
<html>
<head>
<title>Welcome to nginx!</title>
<style>
html { color-scheme: light dark; }
body { width: 35em; margin: 0 auto;
font-family: Tahoma, Verdana, Arial, sans-serif; }
</style>
</head>
<body>
<h1>Welcome to nginx!</h1>
<p>If you see this page, nginx is successfully installed and working.
Further configuration is required for the web server, reverse proxy,
API gateway, load balancer, content cache, or other features.</p>

<p>For online documentation and support please refer to
<a href="https://nginx.org/">nginx.org</a>.<br/>
To engage with the community please visit
<a href="https://community.nginx.org/">community.nginx.org</a>.<br/>
For enterprise grade support, professional services, additional
security features and capabilities please refer to
<a href="https://f5.com/nginx">f5.com/nginx</a>.</p>

<p><em>Thank you for using nginx.</em></p>
</body>
</html>
* Connection #0 to host localhost:8080 left intact
```
<img width="498" height="300" alt="image" src="https://github.com/user-attachments/assets/aa7afc07-5a74-4869-996b-3d6288992009" />

## 10. Docker 볼륨 영속성 검증

## 11. Git 설정 및 GitHub 연동

## 12. 보안 및 개인정보 보호


