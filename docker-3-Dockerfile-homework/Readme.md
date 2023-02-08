# docker 3주차 과제
- 기존 2주차 과제 - 자신이 작성한 소스코드가 작동하는 도커파일 작성 실습 전, 특정 기능을 하는 소스코드 작성하기
- 3주차 과제 - 도커 파일을 구동하여 작동이 이루어지게 도커파일을 작성하고 **Github** 에 업로드 할 것. 
-----
# 2주차 - 도커를 사용하여 로컬 호스트 localhost:8000에 띄우기
php 레이아웃은 구글에서 참조하였습니다.

- 기존 설치 이미지
```Bash
    docker run hello-world
```

- 실행방법

```Bash
    cd docker-2-pratice-homework && docker-compose up
```  

이후, 주소 
**localhost:8000 접속하기**

---
# 3주차 도커파일 작성하기
2주차에 실습 후 진행한 과제에 대하여 **Dockerfile** 를 작성 해보았다.

우선 docker-week2의 과제는 php 기반으로 작동하고, 80번 포트를 연결 시켜야하는 전제 조건이 있다.

**작성한 코드는 아래와 같다.**

```dockerfile
FROM php:7.3-apache

LABEL maintainer="Bochan"

COPY ./php /var/www/html/

EXPOSE 80

CMD ["apache2-foreground"]
```
 - **FROM**을 통하여 이미지의 기반을 php의 7.3-apache로 설정하였다
 - **LABLE** 에서는 작성자 즉 필자를 표시 해주었다
 - **COPY** 를 통하여 도커 파일의 디렉토리에서 이미지에 저장될 파일 경로를 설정 해두었다
 - **EXPOSE**를 통해 호스트와 80번 포트를 연결시켜줬다
 - **CMD**에서는 Docker에게 Apache 웹 서버를 시작하고 컨테이너가 **stop** 될 때 까지 forground에서 실행하도록 명령하였다.





