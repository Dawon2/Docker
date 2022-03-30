# Docker 명령어 정리

**# docker version**

> 도커 버전확인

***

**# docker search [image]**

> 도커 이미지 검색하기 ( Docker Hub에서 검색 )

* ex ) docker search centos

***

**# docker pull [image:version]**

> 도커 이미지 가져오기 (다운로드)

* ex ) docker pull centos:7 ( centos7 버전 다운 )
* ex ) docker pull centos:latest ( centos 최신버전 다운 )

***

**# docker build [옵션] [도커파일 경로]**

> 도커 이미지 생성하기

* ex ) docker build -t dw_web:0.2 /root/docker_test/

    ( -t [생성할 이미지명]:[태그명] [도커파일 위치] -> 도커파일을 사용하여 이미지 생성 )
 
***
   
**# docker images**

> 도커 이미지 목록 확인

***

**# docker run [Option] [이미지 이름]**

> 컨테이너 실행

* ex ) docker run -it --name centos7 centos 

    ( 터미널 환경으로 이름을 centos7으로 지정하고 centos 이미지로 컨테이너 실행 )

* ex ) docker run -it -p 8080:80 centos

    ( "HOST Port:Docker Port" - 8080에서 80번 포트로 포트포워딩 )

* exit나 Ctrl+d 로 컨테이너를 정지시키고 종료할 수 있다
* -d 옵션으로 백그라운드로 컨테이너 실행 가능
* Ctrl + p -> Ctrl + q 를 순서대로 입력하면 중지시키지 않고 빠져나올 수 있음

***

**# docker ps**

> 실행중인 컨테이너 확인
* ex ) docker container ls 로도 확인 가능
  
* ex ) docker ps -a
  
    ( -a 옵션을 추가하여 정지된 컨테이너를 포함한 모든 컨테이너 확인 가능 )

***

**# docker start [컨테이너 ID or 이름]**

> 컨테이너 시작

***

**# docker stop [컨테이너 ID or 이름]**

> 컨테이너 중지

***

**# docker restart [컨테이너 ID or 이름]**

> 컨테이너 재시작

***

**# docker attach [컨테이너 ID or 이름]**

> 컨테이너 접속 ( start 상태에만 접속 가능 )

***

**# docker rename [기존이름] [변경이름]**

> 컨테이너 이름 변경

***

**# docker exec [컨테이너 이름] [명령어] [매개변수]**

> 컨테이너 외부에서 컨테이너 내부 명령 실행

* ex ) docker exec centos7 echo "Hello Docker"
  
    ( centos7 컨테이너에서 echo 명령 실행 )

***

**# docker rm [컨테이너 ID or 이름]**

> 컨테이너 삭제

***

**# docker rmi [컨테이너 ID or 이름]**

> 이미지 삭제

***

**# docker cp [컨테이너 이름]:[경로] [호스트파일 생성 경로]**

> 컨테이너에서 파일 꺼내기

* ex ) docker cp centos7:/root/test.txt . 

    ( centos7 컨테이너에 /root/test.txt 파일을 현재 디렉토리로 꺼내기 )

***

**# docker diff [컨테이너 이름]**

> 컨테이너 실행 이후 변경된 파일 확인

***

**# docker logs [option] [컨테이너 이름]**

> 컨테이너 로그 확인

* docker logs -f centos7 ( 실시간 로그 확인 )
* docker logs --tail 10 centos7 ( 마지막 10줄 로그 확인 ) 
  
***
