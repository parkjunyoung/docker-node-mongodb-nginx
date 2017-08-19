# node 컨테이너 기반
FROM node

# node_modules를 설치하게 소스 폴더로 옴긴다
# 잠시 tmp 캐시 폴더에 저장한다
ADD package.json /tmp/package.json
RUN cd /tmp && npm install
RUN mkdir -p /src && cp -a /tmp/node_modules /src/

# 작업디렉토리를 생성하고 현 소스파일들을 전체를 붙여 넣는다.
WORKDIR /src
ADD . /src

# Expose port
EXPOSE  3000

# Run app using nodemon
CMD ["node", "/src/index.js"]


