FROM openjdk:11-jre
ARG DOCKERIZE_VERSION=v0.6.1
ARG EXPOSED_PORT=9090
ENV SPRING_PROFILES_ACTIVE docker,mysql
ADD https://github.com/jwilder/dockerize/releases/download/${DOCKERIZE_VERSION}/dockerize-alpine-linux-amd64-${DOCKERIZE_VERSION}.tar.gz dockerize.tar.gz
RUN tar -xzf dockerize.tar.gz
RUN chmod +x dockerize
ADD ./target/*.jar /app.jar
EXPOSE ${EXPOSED_PORT}
ENTRYPOINT ["java", "-Djava.security.egd=file:/dev/./urandom","-jar","/app.jar"]

#COPY ile base imaj alarak başlıyoruz.  openjdk-jre seçildi. kod compile edildiği için jdkya gerek yok, jdk gereksiz bir büyüklük olurdu

#ARG : build ederken versionlama için kullanılır toplu versonlamalar için idealdir. 
#örnek: ```bash 
# docker build --build-arg VERSION=2 -t  arg4 .
# ```

# ENV imajın koteynerında çalışır, ARG sadece build edilirken alışır.

#ENV leri developer bizlere verir

#add url adresinden alabilir, add copy url alamaz sadece lokalden alabilir

#expose: output verir

#entrypoint=cmd içerisindeki komutu çalıştırır. 