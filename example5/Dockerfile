ARG BASE_IMAGE=alpine:3.15
FROM $BASE_IMAGE

# ARG - argumenty, ktoré sa dajú použiť pri vytváraní image
# je možné měnit pri vytváraní image
ARG ARG_VAR=b

# ENV - environment variables, ktoré sa dajú použiť pri vytváraní image
# přežije a je možné ji použít i v kontejneru
ENV ENV_VAR=a

# je možné nastavit i ENV var pri vyrábaní image pomocí ARG
ENV ENV_VAR2=${ARG_VAR} 

RUN echo "ARG_VAR = ${ARG_VAR}", "ENV_VAR = ${ENV_VAR}" > /tmp/test.txt
CMD ["/bin/sh", "-c", "cat /tmp/test.txt; echo ARG_VAR=${ARG_VAR}, ENV_VAR=${ENV_VAR}"]

# "/bin/sh", "-c" - spustí sub shell a vykoná príkaz
# pokud by nebylo -c, tak by se spustil jako json form a ne shell form a příkaz cat by se spustil zvlast a přikaz echo by se spustil zvlast



# $docker build --help
# $docker build --build-arg=BASE_IMAGE=alpine:3.14 -t env_test:2 example5
# $docker build --build-arg=BASE_IMAGE=alpine:3.14 --build-arg=ARG_VAR=c -t env_test:3 example5