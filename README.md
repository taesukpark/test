# 미션1 : 내 컴퓨터에 개발자용 '작업실' 꾸미기

## 6. 컨테이너 실행 실습
###    hello-world 실행 성공을 기록한다.


###    Ubuntu 컨테이너를 실행하고 내부 진입 후 간단 명령(예: ls, echo) 수행 결과를 기록한다.
```
• Ubuntu 컨테이너를 실행하고 내부 진입명령 C:\Users\🙌> wsl -d Ubuntu-22.04
```
```
PS C:\Users\🙌> wsl -d Ubuntu-22.04
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

• ls 명령실행 결과 기록 🙌@GNIA-C202-J06:/mnt/c/Users/🙌$ ls
<img width="785" height="232" alt="image" src="https://github.com/user-attachments/assets/a451cb6a-d8d0-4486-8d2e-a64cc53c4e01" />

###   컨테이너 종료/유지(attach/exec 등)의 차이를 스스로 관찰하고 간단히 정리한다.
