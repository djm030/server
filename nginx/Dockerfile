# 공식 Nginx 이미지를 부모 이미지로 사용합니다.
FROM nginx:latest

# 기본 Nginx 설정 파일을 삭제합니다.
RUN rm /etc/nginx/conf.d/default.conf

# Nginx 설정 파일을 복사합니다.
COPY ./nginx.conf /etc/nginx/conf.d/nginx.conf