# win10-virtualbox-kubenates
윈도우10에 virtualbox에 kubenates 설치하기

# virtualbox 머신 생성
```
종류: linux 
버전: ubuntu 64bit
메모리크기: 2GB이상
하드디스크 파일종류: vdi선택
파일 위치 및 크기: 20gb
```

# virtualbox 머신 설정
```
시스템 > 프로세서: cpu 2개 이상
저장소 > 컨트롤러: ubuntu-18.04.3-desktop-amd64.iso
네트워크 > 어댑터1에서 이름을 어댑터 브리지 선택/ Host 네트워크 설정을 위해 어댑터 2 > 네트워크 어댑터 사용하기 체크 > 호스트 전용 어댑터를 선택 
```

# master 머신 시작
터미널 접속
```
root 계정으로 작업하기 위해 sudo -i 실행
apt update 실행
apt install openssh-server 실행
apt install net-tools 실행
방화벽해제: ufw disable 실행
방화벽확인: ufw status verbose 실행
apt-get install vim 실행
```
네트워크 설정(터미널)
```
vi /etc/hosts 실행
 (아래내용 저장)
 192.168.72.101 master
 192.168.72.102 node01
 192.168.72.103 node02

hostname 변경: hostnamectl set-hostname master
```
Host Only Ethernet 설정
```
cd /etc/netplan/ 실행
vi 01-network-manager-all.yaml 실행
 (아래내용 저장)
 
```

# 참고
https://cla9.tistory.com/90?category=814452
