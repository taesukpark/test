# [미션1 : 내 컴퓨터에 개발자용 '작업실' 꾸미기]

## 1. 실행환경
- OS : Ubuntu
- Shell : b a s h 
- Docker : 2
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
PC로그인ID@GNIA-C202-J06:/mnt/c/Users/PC로그인ID$ pwd ↩
/mnt/c/Users/PC로그인ID
```

### 3-2. 목록확인(숨김 파일 포함)
```
PC로그인ID@GNIA-C202-J06:/mnt/c/Users/PC로그인ID$ ls -a ↩
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
PC로그인ID@GNIA-C202-J06:/mnt/c/Users/PC로그인ID$ cd .. ↩ PC로그인ID$의 상위폴더로 이동
PC로그인ID@GNIA-C202-J06:/mnt/c/Users$ cd ~ ↩ 현사용자의 홈 디렉토리로 이동
PC로그인ID@GNIA-C202-J06:~$ cd /mnt/c/Users/PC로그인ID ↩ /mnt/c/Users/PC로그인ID$로 이동
PC로그인ID@GNIA-C202-J06:/mnt/c/Users/PC로그인ID$
```

### 3-4. 생성(폴더)
```
PC로그인ID@GNIA-C202-J06:/mnt/c/Users/PC로그인ID$ mkdir AllinONE ↩ 현재 폴더에 AllinONE 폴더 생성
PC로그인ID@GNIA-C202-J06:/mnt/c/Users/PC로그인ID$ ls ↩ 현재 폴더 목록을 조회해서 mkdir 결과 확인
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
PC로그인ID@GNIA-C202-J06:/mnt/c/Users/PC로그인ID$ cp test1.txt test2.txt ↩
PC로그인ID@GNIA-C202-J06:/mnt/c/Users/PC로그인ID$ ls ↩
(생략)
 test1.txt
 test2.txt
 vscode-remote-wsl
 ''$'\354\213\234\354\236\221'' '$'\353\251\224\353\211\264'
복사된 파일과 원본 파일의 내용확인
PC로그인ID@GNIA-C202-J06:/mnt/c/Users/PC로그인ID$ cat test1.txt
Welcome AllinOne!

PC로그인ID@GNIA-C202-J06:/mnt/c/Users/PC로그인ID$ cat test2.txt
Welcome AllinOne!

```

### 3-6. 파일 이동/이름변경
```
파일 원본 조회
PC로그인ID@GNIA-C202-J06:/mnt/c/Users/PC로그인ID$ ls ↩
 AllinONE
 AppData
(생략)
 practice
 test1.txt
 test2.txt
 vscode-remote-wsl
 ''$'\354\213\234\354\236\221'' '$'\353\251\224\353\211\264'
파일 이동/이름변경(test1.txt 파일을 test3.txt로 내용 이동 및 파일명 변경)
PC로그인ID@GNIA-C202-J06:/mnt/c/Users/PC로그인ID$ mv test1.txt test3.txt ↩
파일 이동/이름변경 상황 조회
PC로그인ID@GNIA-C202-J06:/mnt/c/Users/PC로그인ID$ ls ↩
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
PC로그인ID@GNIA-C202-J06:/mnt/c/Users/PC로그인ID$ rm test2.txt ↩
PC로그인ID@GNIA-C202-J06:/mnt/c/UsersPC로그인ID$ ls ↩
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
PC로그인ID@GNIA-C202-J06:/mnt/c/Users/PC로그인ID$ cat test1.txt ↩
��Welcome AllinOne!
```

### 3-9. 빈 파일 생성
```
PC로그인ID@GNIA-C202-J06:/mnt/c/Users/PC로그인ID$ touch test.txt ↩
PC로그인ID@GNIA-C202-J06:/mnt/c/Users/PC로그인ID$ ls ↩
 AllinONE
 AppData
(생략)
 practice
 test.txt
 test1.txt
 vscode-remote-wsl
 ''$'\354\213\234\354\236\221'' '$'\353\251\224\353\211\264'
PC로그인ID@GNIA-C202-J06:/mnt/c/Users/PC로그인ID$ cat test.txt ↩
PC로그인ID@GNIA-C202-J06:/mnt/c/Users/PC로그인ID$
```

## 4. 권한 실습 및 증거 기록
최소 요구 : 파일 1개(test.txt), 디렉토리 1개(AllinONE)에 대해 권한 변경 실험을 수행

### 4-1. 권한을 확인/변경하는 명령을 수행
```
• 권한 확인
PC로그인ID@GNIA-C202-J06:~$ pwd ↩
/home/PC로그인ID
PC로그인ID@GNIA-C202-J06:~$ ls -al ↩
total 32
drwxr-x--- 4 PC로그인ID PC로그인ID 4096 Nov  8 02:31 .
drwxr-xr-x 3 root        root        4096 Nov  8 01:58 ..
-rw------- 1 PC로그인ID PC로그인ID  775 Nov  8 05:08 .bash_history
-rw-r--r-- 1 PC로그인ID PC로그인ID  220 Nov  8 01:58 .bash_logout
-rw-r--r-- 1 PC로그인ID PC로그인ID 3771 Nov  8 01:58 .bashrc
drwxr-x--- 4 PC로그인ID PC로그인ID 4096 Nov  8 01:59 .cache
drwxr-x--- 3 PC로그인ID PC로그인ID 4096 Nov  8 01:59 .config
-rw-rw-r-- 1 PC로그인ID PC로그인ID    0 Nov  9 20:32 .motd_shown
-rw-r--r-- 1 PC로그인ID PC로그인ID  807 Nov  8 01:58 .profile
PC로그인ID@GNIA-C202-J06:~$ mkdir AllinONE ↩
PC로그인ID@GNIA-C202-J06:~$ ls -l ↩
total 4
drwxr-xr-x 2 PC로그인ID2 PC로그인ID 4096 Nov  9 20:50 AllinONE
PC로그인ID@GNIA-C202-J06:~$ cd AllinONE ↩ 폴더 만들고
PC로그인ID@GNIA-C202-J06:~/AllinONE$ ls ↩ 빈 폴더에
PC로그인ID@GNIA-C202-J06:~/AllinONE$ touch test.txt ↩ test.txt 빈 파일 생성
PC로그인ID@GNIA-C202-J06:~/AllinONE$ ls -l ↩ 폴더내 파일 조회
total 0
-rw-r--r-- 1 PC로그인ID PC로그인ID 0 Nov  9 20:52 test.txt

• 권한 변경(디렉토리AllinONE 권한을 755에서 765로 변경해 보기)
PC로그인ID@GNIA-C202-J06:~$ ls ↩
AllinONE
PC로그인ID@GNIA-C202-J06:~$ ls -l ↩
total 4
drwxr-xr-x 2 PC로그인ID PC로그인ID 4096 Nov  9 20:52 AllinONE
PC로그인ID@GNIA-C202-J06:~$ chmod 765 AllinONE ↩ AllinONE 폴더의 권한 모드를 765로 변경
PC로그인ID@GNIA-C202-J06:~$ ls -l ↩
total 4
drwxrw-r-x 2 PC로그인ID PC로그인ID 4096 Nov  9 20:52 AllinONE

• 권한 변경(test.txt 파일에 대한 권한을 644에서 744로 변경해 보기)
PC로그인ID@GNIA-C202-J06:~$ cd AllinONE ↩
PC로그인ID@GNIA-C202-J06:~/AllinONE$ ls -l ↩
total 0
-rw-r--r-- 1 PC로그인ID PC로그인ID 0 Nov  9 20:52 test.txt
PC로그인ID@GNIA-C202-J06:~/AllinONE$ chmod 744 test.txt ↩
PC로그인ID@GNIA-C202-J06:~/AllinONE$ ls -l ↩
total 0
-rwxr--r-- 1 PC로그인ID PC로그인ID 0 Nov  9 20:52 test.txt

• 권한 변경(빈 파일test1.txt 생성하여 test.txt와 test1.txt를 같은 권한으로 변경해 보기)
PC로그인ID@GNIA-C202-J06:~/AllinONE$ ls ↩
test.txt
PC로그인ID@GNIA-C202-J06:~/AllinONE$ touch test1.txt ↩ test1.txt 빈파일 생성
PC로그인ID@GNIA-C202-J06:~/AllinONE$ ls -l ↩
total 0
-rwxr--r-- 1 PC로그인ID PC로그인ID 0 Nov  9 20:52 test.txt
-rw-r--r-- 1 PC로그인ID PC로그인ID 0 Nov  9 23:14 test1.txt
PC로그인ID@GNIA-C202-J06:~/AllinONE$ chmod --reference=test.txt test1.txt ↩ test.txt와 test1.txt를 같은 권한으로 변경
PC로그인ID@GNIA-C202-J06:~/AllinONE$ ls -l ↩
total 0
-rwxr--r-- 1 PC로그인ID PC로그인ID 0 Nov  9 20:52 test.txt
-rwxr--r-- 1 PC로그인ID PC로그인ID 0 Nov  9 23:14 test1.txt
```
### 4-2. 권한변경 전/후 비교하기
```
• chmod -v옵션으로 test.txt 파일에 대한 변경전 권한과 변경후 권한을 메시지로 확인
PC로그인ID@GNIA-C202-J06:~/AllinONE$  chmod -v 751 test.txt ↩ 권한모드를 751로 바꾸면서 변경 전/후 나타냄
mode of 'test.txt' changed from 0744 (rwxr--r--) to 0751 (rwxr-x--x)
```

## 5. Docker 설치 및 기본 점검
### 5-1. Docker 버전 확인 결과를 기록한다.(docker --version)
```
C:\Users\PC로그인ID>docker version ↩
Client:
 Version:           2
 API version:       1.56
 Go version:        go1.26.10
 Git commit:        a82e528
 Built:             Tue Oct 20 19:44:07 2026
 OS/Arch:           windows/amd64
 Context:           desktop-linux

Server: Docker Desktop 4.97.0 (244584)
 Engine:
  Version:          2
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
C:\Users\PC로그인ID>docker version ↩ 클라이언트와 서버의 버전 정보를 함께 보여줌.
Client:
 Version:           2
 API version:       1.56
 Go version:        go1.26.10
 Git commit:        a82e528
 Built:             Tue Oct 20 19:44:07 2026
 OS/Arch:           windows/amd64
 Context:           desktop-linux

Server: Docker Desktop 4.97.0 (244584)
 Engine:
  Version:          2
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

C:\Users\PC로그인ID>docker info ↩  엔진 상태와 컨테이너·이미지 개수, 저장소 드라이버 등 시스템 정보를 확인할 때 유용
Client:
 Version:    2
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
 Server Version: 2
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

## 6. Docker 기본 운영 명령 수행 및 출력결과
 

### 6-1. 이미지 : 다운로드/목록 확인(예: docker images)

① 이미지 다운로드

```
C:\Users\PC로그인ID>docker pull ubuntu ↩ 
Using default tag: latest
latest: Pulling from library/ubuntu
Digest: sha256:6a06111c3b0a8600feadb270aec771dc239bf407b25625f93f44ab00e11f4d3c
Status: Image is up to date for ubuntu:latest
docker.io/library/ubuntu:latest
```

② 이미지 목록확인
```
C:\Users\PC로그인ID>docker images ↩
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
C:\Users\PC로그인ID> docker run -d --name welcome-to-docker -p 8088:80 nginx ↩
b73b20e8498ed0e7e278e506306f0b84908a375c798f17be52643bfcd9ecbcc5

② 컨테이너 중지전 목록 확인(옵션 -a : 실행중인 컨테이너와 종료된 컨테이너 모두 포함한 목록 확인 가능)
C:\Users\PC로그인ID> docker ps -a ↩ 모든 목록 확인중b73b20e8498e의 status가 Up상태임을 확인
CONTAINER ID   IMAGE     COMMAND                  CREATED         STATUS                      PORTS                                     NAMES
b73b20e8498e   nginx     "/docker-entrypoint.…"   7 minutes ago   Up 7 minutes                0.0.0.0:8088->80/tcp, [::]:8088->80/tcp   welcome-to-docker
e38c12e8bc33   nginx     "/docker-entrypoint.…"   2 hours ago     Exited (0) 10 seconds ago                                             test-container
③ 컨테이너 중지
C:\Users\PC로그인ID> docker stop welcome-to-docker ↩ welcome-to-docker라는 명칭의 컨테이너 중지
welcome-to-docker

④ 컨테이너 중지후 목록 확인
C:\Users\PC로그인ID> docker ps -a ↩ status가 Exited (0)인 중지컨테이너를 포함한 모든 목록 확인
CONTAINER ID   IMAGE     COMMAND                  CREATED          STATUS                      PORTS     NAMES
b73b20e8498e   nginx     "/docker-entrypoint.…"   10 minutes ago   Exited (0) 21 seconds ago             welcome-to-docker
e38c12e8bc33   nginx     "/docker-entrypoint.…"   2 hours ago      Exited (0) 3 minutes ago              test-container

⑤ 컨테이너 중지후 실행중인 컨테이너 확인  
C:\Users\PC로그인ID> docker ps ↩ 현재 실행중인 컨테어너 목록 확인
CONTAINER ID   IMAGE     COMMAND   CREATED   STATUS    PORTS     NAMES
```

### 6-3. 운영 : 로그 확인(예: docker logs), 리소스 확인(예: docker stats)
```
① 로그 확인
C:\Users\PC로그인ID> docker logs test-container ↩
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
C:\Users\PC로그인ID> docker stats ↩
CONTAINER ID   NAME             CPU %     MEM USAGE / LIMIT     MEM %     NET I/O        BLOCK I/O       PIDS
e38c12e8bc33   test-container   0.00%     28.18MiB / 15.25GiB   0.18%     1.3kB / 126B   19MB / 16.4kB   26
Ctrl+C ↩ test-container에서 빠져나오기
```
### 6-4. docker 설치 및 실행 단계 오류 해결

<img width="729" height="516" alt="image" src="https://github.com/user-attachments/assets/11447c79-a688-4569-8a7d-5f0799c77d8a" />

### 6-5. docker 네트워크 및 연결문제(트러블슈팅 2건 문제->원인가설->확인->해결/대안)

<img width="728" height="209" alt="image" src="https://github.com/user-attachments/assets/bbdbf043-b1dc-41de-8b1c-7e470fe8e958" />


## 7. 컨테이너 실행 실습

 < 명령어 동작 원리 >
docker run hello-world는 내부적으로 다음 순서로 동작합니다.
- Docker 클라이언트가 데몬에 요청을 보냅니다.
- 로컬에 hello-world 이미지가 없으면 Docker Hub에서 pull 합니다.
- 이미지로부터 컨테이너를 생성합니다.
- 컨테이너가 메시지를 출력하고 곧바로 종료됩니다.

### 7-1. hello-world 실행 성공을 기록한다.
```
① 
PS C:\Users\PC로그인ID> docker run hello-world ↩ 
Unable to find image 'hello-world:latest' locally
latest: Pulling from library/hello-world
4f55086f7dd0: Pull complete
Digest: sha256:1e4c05b897a751332ce85c7e9449da2d93514ea2dea6dbb0e2753c9e949b2bfa
Status: Downloaded newer image for hello-world:latest

Hello from Docker!
This message shows that your installation appears to be working correctly.

To generate this message, Docker took the following steps:
 1. The Docker client contacted the Docker daemon.
 2. The Docker daemon pulled the "hello-world" image from the Docker Hub.
    (amd64)
 3. The Docker daemon created a new container from that image which runs the
    executable that produces the output you are currently reading.
 4. The Docker daemon streamed that output to the Docker client, which sent it
    to your terminal.

To try something more ambitious, you can run an Ubuntu container with:
 $ docker run -it ubuntu bash

Share images, automate workflows, and more with a free Docker ID:
 https://hub.docker.com/

For more examples and ideas, visit:
 https://docs.docker.com/get-started/

② 컨테이너 실행 증거 추가 확인
PS C:\Users\PC로그인ID> docker ps -a
CONTAINER ID   IMAGE         COMMAND    CREATED         STATUS                     PORTS     NAMES
26ac572150c6   hello-world   "/hello"   3 minutes ago   Exited (0) 3 minutes ago             nervous_kalam

③ 로컬에 내려받은 이미지 확인
PS C:\Users\PC로그인ID> docker images hello-world
                                                                                                    i Info →   U  In Use
IMAGE                ID             DISK USAGE   CONTENT SIZE   EXTRA
hello-world:latest   e2ac70e7319a       10.1kB             0B    U

```
### 7-2. Ubuntu 컨테이너를 실행하고 내부 진입 후 간단 명령(예: ls, echo) 수행 결과를 기록한다.

① Ubuntu 컨테이너를 실행하고 내부 진입명령
```
PS C:\Users\PC로그인ID> wsl -d Ubuntu ↩
PC로그인ID@GNIA-C202-A06:/mnt/c/Users/PC로그인ID$
```

② ls 명령실행 결과 기록

<img width="831" height="585" alt="image" src="https://github.com/user-attachments/assets/8506bf6c-6470-4c80-bd13-653f0b2e0b8d" />


③ echo 명령실행 결과 기록
```
PC로그인ID@GNIA-C202-A06:/mnt/c/Users/PC로그인ID$ echo hello-world ↩
hello-world
```

### 7-3. 컨테이너 종료/유지(attach/exec 등)의 차이를 스스로 관찰하고 간단히 정리
① 컨테이너 docker exec 실행시 컨테이너 목록을 조회해 보면 STATUS가 Up 상태임.
```
PC로그인ID@GNIA-C202-A06:/mnt/c/Users/PC로그인ID$ docker exec -it test-container bash ↩
root@f7c79801c81b:/#
PC로그인ID@GNIA-C202-A06:/mnt/c/Users/PC로그인ID$ docker ps ↩
CONTAINER ID   IMAGE     COMMAND                  CREATED          STATUS          PORTS                                     NAMES
f7c79801c81b   nginx     "/docker-entrypoint.…"   18 minutes ago   Up 18 minutes   0.0.0.0:8080->80/tcp, [::]:8080->80/tcp   test-container
```
② 컨테이너 docker attach 실행시 컨테이너 목록을 조회해 보면 STATUS가 Exited상태임.
```
PC로그인ID@GNIA-C202-A06:/mnt/c/Users/PC로그인ID$ docker attach test-container ↩
ctrl + c
ucidts1102@GNIA-C202-A06:/mnt/c/Users/PC로그인ID$ docker ps -a ↩
CONTAINER ID   IMAGE     COMMAND                  CREATED          STATUS                          PORTS     NAMES
f7c79801c81b   nginx     "/docker-entrypoint.…"   9 minutes ago    Exited (0) About a minute ago             test-container
```

## 8. 기존 Dockerfile 기반 커스텀 이미지 제작

```
PS C:\Users\PC로그인ID> mkdir docker-web ↩


    디렉터리: C:\Users\PC로그인ID


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-----      2026-11-23   오전 5:44                docker-web


PS C:\Users\PC로그인ID> cd docker-web ↩
PS C:\Users\PC로그인ID\docker-web> echo "Hi! This is my first image." > index.html ↩ Redirection 기호 >, >>
PS C:\Users\PC로그인ID\my-web> cat index.html ↩
Hi! This is my first image.
PS C:\Users\PC로그인ID\docker-web> New-Item Dockerfile ↩


    디렉터리: C:\Users\PC로그인ID\docker-web


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----      2026-11-23   오전 5:47              0 Dockerfile
PS C:\Users\PC로그인ID\docker-web> ls ↩


    디렉터리: C:\Users\PC로그인ID\docker-web


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----      2026-11-23   오전 5:47              0 Dockerfile
-a----      2026-11-23   오전 5:45             60 index.html
```

```
PS C:\Users\PC로그인ID\docker-web> docker build -t my-web . ↩
[+] Building 5.2s (8/8) FINISHED                                                                       docker:desktop-linux
 => [internal] load build definition from Dockerfile                                                                   0.0s
 => => transferring dockerfile: 73B                                                                                    0.0s
 => [internal] load metadata for docker.io/library/nginx:alpine                                                        2.2s
 => [auth] library/nginx:pull token for registry-1.docker.io                                                           0.0s
 => [internal] load .dockerignore                                                                                      0.0s
 => => transferring context: 2B                                                                                        0.0s
 => [internal] load build context                                                                                      0.0s
 => => transferring context: 97B                                                                                       0.0s
 => [1/2] FROM docker.io/library/nginx:alpine@sha256:fb4658584bd9a916ffb6f6e365f97c25cfdb2923801f551ea08356e695f14ff7  2.8s
 => => resolve docker.io/library/nginx:alpine@sha256:fb4658584bd9a916ffb6f6e365f97c25cfdb2923801f551ea08356e695f14ff7  0.0s
 => => sha256:e68702efeaad0be9ced2b4d1cedb62cd15f5d51865d913955a883f653cd9e117 2.50kB / 2.50kB                         0.0s
 => => sha256:62d1c420c34ae91f7bffd349903cd6846806b835129c8b7ba2da28b3be323cd1 12.32kB / 12.32kB                       0.0s
 => => sha256:04c3905a997c5ada93c8e4ad6c8d593e04c5ad4efa87a648a72f34138ea47117 627B / 627B                             0.2s
 => => sha256:881fc932939efef04ca120ad44bbd2c0917851eb247aa4995428afb1e80ede17 3.85MB / 3.85MB                         0.9s
 => => sha256:77a3bfea78f562fc46a238affde2e413f44ebe98eb6accd78acc9aade0711eed 1.94MB / 1.94MB                         0.6s
 => => sha256:fb4658584bd9a916ffb6f6e365f97c25cfdb2923801f551ea08356e695f14ff7 10.33kB / 10.33kB                       0.0s
 => => sha256:7cb374baf96870045ef10fb2275d30d893e2010d5fb12d2e8f949babcb3de6bf 965B / 965B                             0.7s
 => => sha256:4c8c172c658661b7927fad4ab766c7e6c597d83400a3ed3f2e484c5940b4c56a 404B / 404B                             0.8s
 => => sha256:1dc588c89da10830dde2a359d1b421e384caaae52458be045dcf6770ae7d624a 1.21kB / 1.21kB                         0.9s
 => => extracting sha256:881fc932939efef04ca120ad44bbd2c0917851eb247aa4995428afb1e80ede17                              0.1s
 => => sha256:61d8f4c85a745813b78f7b3ea04d0268fd196753e0964ac6cd3f55fe161c865b 1.40kB / 1.40kB                         1.1s
 => => sha256:c4f3d97811f679e18a790555496d98de98efbd4a61f8741c1aeedd86317c5f6c 20.54MB / 20.54MB                       2.3s
 => => extracting sha256:77a3bfea78f562fc46a238affde2e413f44ebe98eb6accd78acc9aade0711eed                              0.0s
 => => extracting sha256:04c3905a997c5ada93c8e4ad6c8d593e04c5ad4efa87a648a72f34138ea47117                              0.0s
 => => extracting sha256:7cb374baf96870045ef10fb2275d30d893e2010d5fb12d2e8f949babcb3de6bf                              0.0s
 => => extracting sha256:4c8c172c658661b7927fad4ab766c7e6c597d83400a3ed3f2e484c5940b4c56a                              0.0s
 => => extracting sha256:1dc588c89da10830dde2a359d1b421e384caaae52458be045dcf6770ae7d624a                              0.0s
 => => extracting sha256:61d8f4c85a745813b78f7b3ea04d0268fd196753e0964ac6cd3f55fe161c865b                              0.0s
 => => extracting sha256:c4f3d97811f679e18a790555496d98de98efbd4a61f8741c1aeedd86317c5f6c                              0.2s
 => [2/2] COPY index.html .                                                                                            0.0s
 => exporting to image                                                                                                 0.0s
 => => exporting layers                                                                                                0.0s
 => => writing image sha256:45728d00dd5db32ae2017bec1f2b91008ec4f93ca04384e3a74be2f948c0fac2                           0.0s
 => => naming to docker.io/library/my-web

<img width="512" height="278" alt="image" src="https://github.com/user-attachments/assets/1387d5b7-4496-4559-90f0-006999f1a0b9" />


```


## 9. 포트 매핑 및 접속 증거

> 컨테이너는 호스트와 분리된 네트워크 네임스페이스를 사용하므로, `-p 호스트포트:컨테이너포트` 포트 포워딩이 있어야 호스트의 localhost에서 접속할 수 있다.

```
PC로그인ID@GNIA-C202-J06:~$ docker ps -a ↩
CONTAINER ID   IMAGE     COMMAND                  CREATED       STATUS         PORTS                                     NAMES
b73b20e8498e   nginx     "/docker-entrypoint.…"   2 hours ago   Up 8 minutes   0.0.0.0:8088->80/tcp, [::]:8088->80/tcp   welcome-to-docker
e38c12e8bc33   nginx     "/docker-entrypoint.…"   4 hours ago   Up 8 minutes   0.0.0.0:8080->80/tcp, [::]:8080->80/tcp   test-container

PC로그인ID@GNIA-C202-J06:~$ curl -v http://localhost:8080 ↩ -v 옵션을 사용하면 요청(Request)과 응답(Response) 과정을 모두 볼 수 있어 포트 매핑이 성공했다는 강력한 증거
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

### 10-1. 바인드 마운트 : 실행명령 + 호스트 변경 전/후 비교

<img width="974" height="414" alt="image" src="https://github.com/user-attachments/assets/b7621c6c-4812-45a5-84c5-e97fbc5567fa" />


① 내 컴퓨터에 폴더와 파일 생성
```
PS C:\Users\PC로그인ID> mkdir -p /my-folder ↩


    디렉터리: C:\Users\PC로그인ID


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-----      2026-11-12  오전 12:07                my-folder

PS C:\Users\PC로그인ID> echo "bind_mount" > ~/my-folder/index.html ↩
PS C:\Users\PC로그인ID> ls ~/my-folder ↩


    디렉터리: C:\Users\PC로그인ID\my-folder


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----      2026-11-12  오전 12:17             26 index.html


PS C:\Users\PC로그인ID> cat ~/my-folder/index.html ↩
bind_mount
```
```
docker run -v /호스트/절대경로:/컨테이너/경로 이미지명 또는 
--mount type=bind,source=/호스트/절대경로,target=/컨테이너/경로
```

### 10-2. Docker 볼륨

① 볼륨생성
```
PS C:\Users\PC로그인ID> docker volume create my_data ↩
my_data
```

② 볼륨연결
```
PS C:\Users\PC로그인ID>  docker run -dit --name my-web-test -p 80:80 -v my_data:/usr/share/nginx/html nginx ↩
b18c608496d8a6a818be92eb5ce13f07557ca1109742db2d3af116b22eb50834
```

③ 검증명령
```
PS C:\Users\PC로그인ID> docker volume ls ↩
DRIVER    VOLUME NAME
local     my_data
local     my_shared_data

PS C:\Users\PC로그인ID> docker volume inspect my_data ↩
[
    {
        "CreatedAt": "2026-11-11T13:43:51Z",
        "Driver": "local",
        "Labels": null,
        "Mountpoint": "/var/lib/docker/volumes/my_data/_data",
        "Name": "my_data",
        "Options": null,
        "Scope": "local"
    }
]
```

④ 컨테이너 삭제 전/후 비교

```
• 컨테이너 내부파일 확인
PS C:\Users\PC로그인ID> docker exec my-web-test ls /usr/share/nginx/html ↩
50x.html
index.html

• 컨테이너 내부에 영속성을 증명하기 위한 테스트용 파일 생성
PS C:\Users\PC로그인ID> docker exec my-web-test sh -c "echo 'Hello, Docker Volume!' > /usr/share/nginx/html/test.txt" ↩

• 컨테이너 -f옵션으로 강제 종료후 삭제 (docker stop 컨테이너명--> docker rm 컨테이너명)
PS C:\Users\PC로그인ID> docker rm -f my-web-test ↩
my-web-test

• my-web-test 컨테이너 삭제 확인
PS C:\Users\PC로그인ID> docker ps -a ↩
CONTAINER ID   IMAGE     COMMAND   CREATED   STATUS    PORTS     NAMES

• 컨테이너 삭제후 볼륨목록 확인
PS C:\Users\PC로그인ID> docker volume ls ↩
DRIVER    VOLUME NAME
local     my_data
local     my_shared_data
PS C:\Users\PC로그인ID> docker volume inspect my_data ↩
[
    {
        "CreatedAt": "2026-11-11T13:43:51Z",
        "Driver": "local",
        "Labels": null,
        "Mountpoint": "/var/lib/docker/volumes/my_data/_data",
        "Name": "my_data",
        "Options": null,
        "Scope": "local"
    }
]

• 영속성 확인을 위한 새컨터이너 생성하여 동일 볼륨에 연결하기
PS C:\Users\PC로그인ID> docker run -d --name new-web -v my_data:/usr/share/nginx/html nginx ↩
20a317d80b4d3fcfb9f71f3c6a2cfd7753a66397d8c174e6b178ffd3438debf6

• new-web 컨테이너에 연결된 my-data 파일내용 확인
PS C:\Users\PC로그인ID> docker exec new-web cat /usr/share/nginx/html/test.txt ↩
Hello, Docker Volume!
```


## 11. Git 설정 및 GitHub 연동

11-1. Git 사용자 정보/기본 브랜치 설정을 완료하고 git config --list
```
PS C:\Users\PC로그인ID> git --version ↩ git 설치 확인
git version 2.56.0.windows.4
PS C:\Users\PC로그인ID> git config --global user.name "사용자명" ↩
PS C:\Users\PC로그인ID> git config --global user.email "사용자email" ↩
PS C:\Users\PC로그인ID> git config --global init.defaultBranch main ↩
PS C:\Users\PC로그인ID> git config --list
diff.astextplain.textconv=astextplain
filter.lfs.clean=git-lfs clean -- %f
filter.lfs.smudge=git-lfs smudge -- %f
filter.lfs.process=git-lfs filter-process
filter.lfs.required=true
http.sslbackend=schannel
core.autocrlf=true
core.fscache=true
core.symlinks=false
core.quotepath=false
pull.rebase=false
credential.helper=manager
credential.https://dev.azure.com.usehttppath=true
init.defaultbranch=main
safe.directory=*
safe.directory=*
safe.directory=*
safe.directory=*
safe.directory=*
safe.directory=*
safe.directory=*
safe.directory=*
safe.directory=*
user.name=사용자명
user.email=사용자email
init.defaultbranch=main
core.repositoryformatversion=0
core.filemode=false
core.bare=false
:

```
11-2. 원격(remote) 저장소 추가 및 연결 확인 (`git remote -v`)

① 로컬 저장소 초기화 및 첫 커밋 (이미 저장소가 있으면 생략)
```
PS C:\Users\PC로그인ID\docker-web> git init ↩
PS C:\Users\PC로그인ID\docker-web> git add . ↩
PS C:\Users\PC로그인ID\docker-web> git commit -m "first commit" ↩
PS C:\Users\PC로그인ID\docker-web> git branch -M main ↩ 기본 브랜치명을 main으로 통일
```

② 원격 저장소 추가 (GitHub에서 빈 저장소를 먼저 생성한 뒤 그 주소를 등록)
```
PS C:\Users\PC로그인ID\docker-web> git remote add origin https://github.com/사용자명/저장소명.git ↩
```
- `origin` : 원격 저장소에 붙이는 관례적인 별칭(이름)
- 주소에는 토큰/비밀번호를 포함하지 않는다. 인증은 Git Credential Manager(`credential.helper=manager`)가 브라우저 로그인으로 처리한다.

③ 원격 등록 확인 : `git remote -v`
```
PS C:\Users\PC로그인ID\docker-web> git remote -v ↩
origin  https://github.com/사용자명/저장소명.git (fetch)
origin  https://github.com/사용자명/저장소명.git (push)
```
- fetch(내려받기)용, push(올리기)용 주소가 각각 한 줄씩 출력되면 등록이 정상이다.
- 아무것도 출력되지 않으면 원격이 등록되지 않은 것이므로 ②를 다시 수행한다.

④ 연결 성공 확인 방법 (아래 3가지 중 하나 이상으로 증거를 남긴다)
```
(방법 1) 원격 서버에 실제로 접속되는지 확인
PS C:\Users\PC로그인ID\docker-web> git ls-remote origin ↩
(빈 저장소이면 출력이 없어도 오류 없이 끝나면 연결 성공, 인증/주소 오류이면 fatal 메시지 출력)

(방법 2) 최초 push 후 추적 브랜치 연결 확인
PS C:\Users\PC로그인ID\docker-web> git push -u origin main ↩
branch 'main' set up to track 'origin/main'.

(방법 3) 로컬 브랜치와 원격 브랜치의 연결 상태 확인
PS C:\Users\PC로그인ID\docker-web> git status -sb ↩
## main...origin/main
PS C:\Users\PC로그인ID\docker-web> git branch -vv ↩
* main 1a2b3c4 [origin/main] first commit
```
- `git push` 성공 후 GitHub 저장소 웹페이지에서 커밋이 보이면 최종 연동 성공이다.

⑤ 자주 발생하는 오류와 조치
| 오류 메시지 | 원인 | 조치 |
|---|---|---|
| `remote origin already exists` | 이미 origin이 등록됨 | `git remote set-url origin <새 주소>` 로 주소 수정 |
| `repository not found` | 주소 오타 또는 접근 권한 없음 | `git remote -v`로 주소 재확인, 저장소 권한 확인 |
| `Authentication failed` | 인증 정보 만료/오류 | 자격 증명 관리자에서 GitHub 항목 삭제 후 다시 로그인 |


## 12. 보안 및 개인정보 보호

```
기술문서/로그/스크린샷에 토큰, 비밀번호, 개인키, 인증 코드 등이 미포함되게 할 것
```


## 13. 작업 디렉토리 구조 설계 기준 및 폴더 역할

### 13-1. 설계 기준
```
1. **목적별 분리** : 터미널 실습 / Docker 이미지 빌드 / 바인드 마운트 / 증거 자료를 서로 다른 폴더로 나눠, 한 실습의 파일이 다른 실습에 섞이지 않게 한다.
2. **빌드 컨텍스트 최소화** : `docker build .` 는 현재 폴더 전체를 Docker 데몬에 전달한다. 이미지에 필요한 파일(Dockerfile, index.html)만 전용 폴더에 두어 빌드 속도와 의도치 않은 파일 포함을 막는다.
3. **실행 환경에 맞는 위치 선택** : 일반적으로 WSL에서 Windows 드라이브(`/mnt/c/...`)에 있는 파일은 `chmod` 권한 변경이 리눅스처럼 반영되지 않는다. 그래서 권한 실습(4번)은 WSL 홈(`~`, 리눅스 파일시스템)에서 수행했다.
4. **증거와 실습물의 분리** : 스크린샷·로그는 `docs/logs/`에 모아 README에서 상대경로로 참조한다. 저장소를 어디로 옮겨도 링크가 깨지지 않는다.
5. **이름만 보고 역할을 알 수 있게** : 폴더명을 `docker-web`, `my-folder`처럼 용도가 드러나게 짓는다.
```

### 13-2. 폴더 구조와 역할(설계 근거)
```
C:\Users\PC로그인ID\                (Windows 홈 - Docker Desktop, Git, VSCode 작업 위치)
├─ docker-web\       Dockerfile + index.html  → 커스텀 이미지 빌드 전용 (8번)
├─ my-folder\        index.html               → 바인드 마운트용 호스트 폴더 (10-1)
├─ AllinONE\         test1.txt 등             → 터미널 기본 명령 실습 (3번)
└─ practice\                                  → 자유 연습 공간 (실습 결과와 분리)

/home/PC로그인ID/ (WSL Ubuntu 홈)
└─ AllinONE/         test.txt, test1.txt      → chmod 권한 실습 (4번)

(저장소 루트)
├─ README.md                                   → 과제 보고서(실습 로그·설명)
└─ docs/logs/                                  → 스크린샷·로그 증거 파일
```
| 폴더 | 역할 | 설계 근거 |
|---|---|---|
| `docker-web` | 이미지 빌드 컨텍스트 | 빌드에 필요한 파일만 두어 `COPY index.html .` 이 의도한 파일만 복사하게 함 |
| `my-folder` | 바인드 마운트 원본 | 호스트에서 수정한 내용이 컨테이너에 즉시 반영되는지 확인하기 위한 독립 폴더 |
| `AllinONE` (Windows) | 기본 명령 실습 | 생성/복사/삭제 실습이 다른 폴더에 영향을 주지 않도록 격리 |
| `AllinONE` (WSL `~`) | 권한 실습 | 리눅스 파일시스템에서 `chmod`가 정확히 반영됨 |
| `docs/logs` | 증거 보관 | 문서와 증거를 분리하고, README에서 상대경로로 참조 |


## 14. 포트 충돌 진단 및 해제 절차

**증상** : `docker run -p 8080:80 nginx` 실행 시 아래와 같은 오류가 나며 컨테이너가 시작되지 않는다.
```
docker: Error response from daemon: ... Bind for 0.0.0.0:8080 failed: port is already allocated
(Windows에서는 "...bind: Only one usage of each socket address (protocol/network address/port) is normally permitted" 형태로 나오기도 함)
```
**원리** : 하나의 호스트 포트는 한 번에 한 프로세스만 점유(LISTEN)할 수 있다. 다른 컨테이너나 프로그램이 이미 8080을 쓰고 있으면 새 매핑은 실패한다.

### 14-1. 단계별 진단·해제 순서
**STEP 1. 누가 포트를 쓰는지 확인**

① Docker 컨테이너가 점유 중인지 먼저 확인 (가장 흔한 원인)
```
docker ps --filter "publish=8080"
(또는) docker ps -a  → PORTS 열에서 0.0.0.0:8080->80/tcp 를 찾는다
```
② 컨테이너가 아니라면 호스트 프로세스 확인
```
[Windows PowerShell / CMD]
netstat -ano | findstr :8080                       → 맨 오른쪽 숫자가 PID
Get-NetTCPConnection -LocalPort 8080               → OwningProcess 열이 PID
tasklist /FI "PID eq <PID>"                        → PID로 프로그램 이름 확인

[Linux / WSL Ubuntu]
ss -ltnp | grep :8080                              → users:(("프로세스명",pid=<PID>,...))
sudo lsof -i :8080                                 → COMMAND, PID 확인
```
**STEP 2. 점유 주체가 무엇인지 판단**
- 내가 만든 컨테이너/프로그램이면 → STEP 3으로 진행
- 모르는 프로세스(시스템 서비스 등)이면 → 종료하지 않고 STEP 4(다른 포트 사용)를 선택

**STEP 3. 포트 해제**
```
[컨테이너가 점유]
docker stop <컨테이너명>        → 정상 종료 (포트 해제됨)
docker rm <컨테이너명>          → 필요 없으면 삭제

[Windows 프로세스가 점유]
Stop-Process -Id <PID>          (PowerShell)
taskkill /PID <PID>             (CMD, 안 되면 /F 옵션은 마지막 수단)

[Linux/WSL 프로세스가 점유]
kill <PID>                      → 정상 종료 요청
kill -9 <PID>                   → 종료되지 않을 때만 마지막 수단
```
**STEP 4. (대안) 포트를 바꿔서 실행** : 컨테이너 내부 포트(80)는 그대로 두고 호스트 포트만 바꾼다.
```
docker run -d --name test-container -p 8081:80 nginx
```
**STEP 5. 해제·재실행 결과 검증**
```
netstat -ano | findstr :8080        → 출력이 없으면 해제 완료
docker ps                           → PORTS에 0.0.0.0:8080->80/tcp 표시 확인
curl -I http://localhost:8080       → HTTP/1.1 200 OK 확인
```
> 주의 : PID를 확인하지 않고 종료하면 중요한 프로세스를 끌 수 있다. 반드시 STEP 1~2에서 프로세스 이름을 확인한 뒤 종료한다.



## 15. 트러블슈팅 기록 (가설 → 확인 → 조치)

각 문제를 **증상 → 가설 → 검증 명령 → 로그 → 판단 근거 → 조치 → 결과** 순서로 기록한다.
(6-5의 스크린샷 2건을 아래 형식으로 정리한다. ※ 출력의 `<PID>` 등은 실제 값으로 교체해 기록)

### 15-1. 사례 1 : 컨테이너 시작 실패 (포트 충돌)
| 단계 | 내용 |
|---|---|
| 증상 | `docker run -d -p 8080:80 nginx` 실행 시 컨테이너가 생성되지 않음 |
| 가설 | 호스트의 8080 포트를 이미 다른 컨테이너 또는 프로세스가 점유하고 있을 것이다 |
| 검증 명령 | ① `docker ps -a` ② `netstat -ano \| findstr :8080` |
| 로그 | ① `test-container ... 0.0.0.0:8080->80/tcp` 가 Up 상태로 조회됨 ② `TCP 0.0.0.0:8080 ... LISTENING <PID>` |
| 판단 근거 | 8080이 LISTENING 상태이고 PID가 기존 컨테이너(Docker 백엔드)의 것이므로 가설이 맞다. 오류 메시지의 `port is already allocated` 와도 일치 |
| 조치 | 기존 컨테이너 정지 `docker stop test-container` (또는 새 컨테이너를 `-p 8081:80` 으로 실행) |
| 결과 | `docker ps` 에서 새 컨테이너 Up, `curl -I http://localhost:8080` (또는 8081) → `HTTP/1.1 200 OK` |

### 15-2. 사례 2 : 컨테이너는 Up인데 localhost 접속 불가 (포트 매핑 누락)
| 단계 | 내용 |
|---|---|
| 증상 | 컨테이너 상태는 Up인데 `http://localhost:8080` 접속이 거부됨 |
| 가설 | `-p` 옵션 없이 실행해 호스트 포트와 컨테이너 포트가 연결(포워딩)되지 않았을 것이다 |
| 검증 명령 | ① `docker ps` (PORTS 열 확인) ② `docker port <컨테이너명>` ③ `curl -v http://localhost:8080` |
| 로그 | ① PORTS 열이 `80/tcp` 만 표시(호스트 포트 없음) ② 출력 없음 ③ `Connection refused` |
| 판단 근거 | 컨테이너는 별도 네트워크 네임스페이스에 있어 `0.0.0.0:8080->` 형태의 매핑이 없으면 호스트에서 도달할 수 없다 |
| 조치 | `docker rm -f <컨테이너명>` 후 `docker run -d -p 8080:80 --name <컨테이너명> nginx` 로 재실행 |
| 결과 | PORTS 열에 `0.0.0.0:8080->80/tcp` 표시, `curl -v` 에서 `HTTP/1.1 200 OK` 확인 (9번 증거 참조) |

### 15-3. 기록 템플릿 (새 문제 발생 시)
```
1) 증상  : 어떤 명령에서 어떤 오류가 났는가 (오류 메시지 그대로)
2) 가설  : 원인이라고 추정한 것 (한 번에 하나)
3) 검증  : 가설을 확인하는 명령
4) 로그  : 검증 명령의 실제 출력 (토큰·개인정보 제거)
5) 판단  : 출력의 어느 부분이 가설을 지지/반박하는가
6) 조치  : 수행한 해결 명령
7) 결과  : 조치 후 재확인 명령과 정상 출력
```


## ** 과제를 마치면서...


### <절대경로와 상대경로의 차이 : 디렉토리(폴더)나 파일의 위치를 표현하는 방법의 차이>

<img width="899" height="183" alt="image" src="https://github.com/user-attachments/assets/0477a464-0859-444f-bf41-23842994cbdc" />

```
. (점 하나) — 지금 있는 폴더

.. (점 둘) — 한 칸 위 폴더

~ (물결표) — 홈 폴더
```

### <절대경로·상대경로 사용 사례와 선택 기준>
```
절대경로 : 루트(/)나 드라이브(C:\)부터 시작하는 전체 경로  예) /mnt/c/Users/PC로그인ID/my-folder
상대경로 : 현재 위치(.)를 기준으로 하는 경로              예) ./docker-web, ../AllinONE
```
| 구분 | 이럴 때 사용 | 이번 과제의 사례 |
|---|---|---|
| 절대경로 | 실행 위치와 상관없이 항상 같은 대상을 가리켜야 할 때 | `docker run -v /호스트/절대경로:/컨테이너/경로` (바인드 마운트는 호스트 경로를 절대경로로 지정해야 함, 10-1) |
| 절대경로 | 다른 폴더에 있다가 특정 위치로 한 번에 이동할 때 | `cd /mnt/c/Users/PC로그인ID` |
| 절대경로 | 예약 작업·서비스처럼 실행 위치를 보장할 수 없을 때 | cron, 시스템 서비스 설정 |
| 상대경로 | 프로젝트 안에서 폴더를 옮겨도 동작해야 할 때 | `COPY index.html .` (Dockerfile은 빌드 컨텍스트 기준 상대경로), `docker build -t my-web .` |
| 상대경로 | 현재 위치 근처로 짧게 이동할 때 | `cd ..` (상위 폴더), `cd AllinONE` (하위 폴더) |
| 상대경로 | 문서/저장소 안의 파일을 참조할 때 | `![결과](docs/logs/docker-hello-world.png)` (저장소를 clone해도 링크 유지) |

**선택 기준 요약**
1. 위치가 **고정**이고 어디서 실행하든 같은 대상이어야 하면 → **절대경로**
2. 프로젝트/저장소가 **다른 PC·폴더로 옮겨져도** 동작해야 하면 → **상대경로**
3. 홈 기준은 `~`를 쓰면 사용자명이 바뀌어도 이식성이 있다.
4. 절대경로는 환경(사용자명, 드라이브)에 종속되므로 공유하는 문서·스크립트에는 가급적 상대경로를 쓴다.
5. 헷갈리면 `pwd`로 현재 위치를 먼저 확인한다.

### <파일 권한의 의미(r/w/x)와 755, 644 같은 표기가 어떤 규칙으로 해석되는지 설명>
--> 4. 권한 실습 및 증거 기록 참고
```
r : 읽기 권한(4)
W : 쓰기 권한(2)
x : 실행 권한(1)

(소유자 권한)        7 : rwx       6 : rw-
(user그룹 권한)      5 : r-x       4 : r--
(기타 사용자 권한)    5 : r-x       4 : r--
```


### <기존 Dockerfile을 기반으로 '커스텀 이미지'를 만들기>
--> 8. 기존 Dockerfile 기반 커스텀 이미지 제작 참고


### <포트 매핑이 필요한 이유>
--> 9. 포트 매핑 및 접속 증거 참고
```
Docker 컨테이너는 독립된 네트워크에 있어 기본적으로 외부에서 접근할 수 없으므로,
- (네임스페이스 관점) 컨테이너는 리눅스 네트워크 네임스페이스(network namespace)로 호스트와 격리되어 자신만의 IP·네트워크 인터페이스·포트 공간을 가지므로, 컨테이너 안에서 80번 포트를 열어도 호스트의 localhost에서는 보이지 않음. 따라서 `-p 호스트포트:컨테이너포트`로 두 네임스페이스 사이에 포트 포워딩(DNAT)을 설정해야 호스트에서 컨테이너로 접속 가능
- 포트 매핑으로 호스트의 특정 포트와 컨테이너의 포트를 연결해야 외부 접속 가능
- 지정한 포트만 선택적으로 외부와 연결하여 필요한 서비스만 열어 보안성 향상
- 서로 다른 호스트 포트에 같은 컨테이너 포트를 사용하는 서비스도 충돌없이 운영 가능
- 컨테이너 내부 포트를 바꾸지 않고 호스트 포트만 변경할 수 있어 개발 및 테스트, 운영환경에 맞게 포트 분리가능
- 같은 이미지를 바탕으로 여러 컨테이너를 동시에 실행하여 수평적 확장이 이루어져 각 매핑마다 독립적으로 운영가능
```


### <Docker 볼륨(영속 데이터)>
 --> 10. Docker 볼륨 영속성 검증 참고
```
도커 컨테이너는 삭제되면 그 안의 파일도 함께 사라지는 특징이 있어서, 컨테이너라는 '일회용 컴퓨터' 바깥에 데이터를 따로 보관하는
'외장 하드' 같은 공간이 필요한데 그것을 볼륨이라고 함.
컨테이너를 삭제해도 볼륨은 영속적으로 존재하므로 다른 컨테이너를 새로 만들어 다시 연결해서 이전 데이터를 그대로 사용할 수 있음.
```


### <Git(로컬 버전관리)과 GitHub(원격 협업 플랫폼)의 역할 차이>

<img width="707" height="402" alt="image" src="https://github.com/user-attachments/assets/3d7b9c48-f22d-4d9d-b6f5-d62c56a522cf" />

