# Docker 설치 및 컨테이너 사용법

## Docker 설치 (CentOS7)

1. 저장소 설정
```
    # yum -y install yum-utils

    # yum-config-manager --add-repo https://download.docker.com/linux/centos/docker-ce.repo
```
2. 도커 엔진 설치
```
    # yum -y install docker-ce docker-ce-cli containerd.io
```
3. 도커 실행
```
    # systemctl start docker
    # systemctl enable docker
```

***

## 컨테이너 사용법
```
# docker container ls
( 실행중인 컨테이너 리스트 )

# docker search centos
( Docker Hub 저장소에서 이미지 검색 - centos )

# docker image pull centos:7
( centos7 이미지 다운로드 )

# docker images
( = docker image ls )
( Docker 이미지 목록 확인 )


# docker run -it --name centos7 centos
( centos 이미지로 컨테이너 실행 )

* exit로 나올수 있음.

# docker ps -a
( 실행중인 컨테이너 상태 모두 확인 )

# docker commit -p centos7 centos7.backup
( 백업 전 이미지 상태 저장 )

# docker save -o centos7.tar centos7.backup
( docker 이미지 백업 )
```


* 관리자 권한이 필요할때 그룹에 권한 부여 하기
```
    # sudo usermod -aG docker $USER
    후 재로그인
```