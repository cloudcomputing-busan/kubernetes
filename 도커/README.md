# Docker를 설치 하는 명령어
```
yum install docker -y
systemctl enable --now docker
chmod 666 /var/run/docker.sock
```

# Docker 이미지를 생성 해주는 파일명은 Dockerfile이다!
Dockerfile 예시:
```
FROM amazonlinux:latest

COPY ./app.py .

RUN yum update -y && yum install python3-pip -y

RUN pip3 install flask

EXPOSE 8080

CMD ["python3", "app.py"]
```

# Docker를 빌드하는 명령어는 build이다!
```
cd <Dockerfile 위치>
docker build -t <태그 이름> .
```

# Docker를 실행하는 명령어는 run이다!
```
docker run -d -p8080:8080 <태그 이름>
```
```
docker run는 도커를 실행하는 명령어
-d는 배경에 실행하는 조건 만약 우리가 컨테이너를 접속하고 싶으면 -it로 변경
-p는 포트 맵핑 조건 예를 들면 앱이 8080일 경우 80으로 실행하고 싶으면 80:8080으로 하면 된다
```

# 추가 적인 Docker 명령어
```
docker images #이미지 조회 명령어
docker ps #컨테이너 실행 명령어
docker rmi <이미지 앞에 3 영문 또는 숫자> #이미지 삭제 명령어
docker rmi -f <이미지 앞에 3 영문 또는 숫자> #이미지 강제 삭제
docker kill <컨테이너 앞에 3 영문 또는 숫자> #컨테이너 종료
```