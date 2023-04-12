# cloud-demo
cloud-demo for docker

MAVEN
D:\day\cloud-demo\cloud-demo\login
mvn clean package

java -jar login-0.0.1.jar

cd target
docker build -f .\DockerFile.dockerfile -t login:v1 .
docker build -f .\DockerFile.dockerfile -t gateway:v1 .
docker build -f .\DockerFile.dockerfile -t demo:v1 .

docker run -d -p 1000:1000 --name login login:v1
docker run -d -p 10010:10010 --name gateway gateway:v1
docker run -d -p 8080:8080 --name demo demo:v1

docker run -d -p 10010:10010 --name gateway gateway:v1
docker run -v /tmp:/tmp -d -p 1000:1000 --name login login:v1
docker run -v /tmp:/tmp -d -p 8080:8080 --name demo demo:v1

docker tag login:v1 liqdl/login:v1
docker tag demo:v1 liqdl/demo:v1
docker tag gateway:v1 liqdl/gateway:v1

docker push liqdl/login:v1
docker push liqdl/demo:v1
docker push liqdl/gateway:v1

D:\day\cloud-demo\cloud-demo\gateway
cd target
java -jar gateway-0.0.1.jar

D:\day\cloud-demo\cloud-demo\demo
cd target
java -jar demo-0.0.1.jar


mvn –N io.takari:maven:wrapper
mvn  io.takari:maven:wrapper
D:\day\cloud-demo\cloud-demo的下面 生成 \.mvn\wrapper
mvn -N io.takari:maven:wrapper
