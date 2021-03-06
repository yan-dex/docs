# Создать Docker-образ

В инструкции описано как создать [Docker-образ](../../concepts/docker-image.md) на основе Dockerfile и собрать его.  

---

**[!TAB CLI]**

1. Создайте файл Dockerfile и добавьте туда следующие строки:
    
    ```
    FROM ubuntu:latest
    CMD echo "Hi, I'm inside"
    ```
    
    Описанный Docker-образ основан на Ubuntu и будет выполнять одну простую команду.  

1. Соберите Docker-образ. В качестве `<ID реестра>` используется `ID`, полученный при 
[создании реестра](../registry/registry-create.md).

    ```
    $ docker build . \
    -t container-registry.cloud.yandex.net/<ID реестра>/ubuntu:hello
    ```

    Флаг `-t` необязательный — можно собрать Docker-образ без указания тега. В таком случае Docker CLI присвоит метку 
    по умолчанию: `latest`.
    
--- 

После выполнения данных команд будет создан Docker-образ со следующими параметрами:
- Полный адрес репозитория, состоящий из: 
    - Адрес сервиса Yandex Container Registry `container-registry.cloud.yandex.net`.
    - Идентификатор вашего реестра `<ID реестра>`.
    - Имя вашего репозитория `ubuntu`.
- Тег Docker-образа в вашем репозитории: `hello`.
