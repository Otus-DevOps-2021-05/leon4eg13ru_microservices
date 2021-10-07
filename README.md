# leon4eg13ru_microservices
leon4eg13ru microservices repository

## HW_12-13

 - Создан docker host
 - Создан своq образ и конфигурация для него
 - Образ опубликован в публичном Docker hub под именем leon4eg/otus-reddit:1.0

## HW_14

 - приложение разбито на несколько компонентов
 - образы comment и ui оптимизированы под alpine-версии

## HW_15

 - в docker-compose.yml добавлены сети для бекэнда и фронтэнда
 - параметризованы параметры USERNAME, PORT, COMPOSE_PROJECT_NAME и создан отдельный файл .env для них
 - базовое имя проекта задается через переменную COMPOSE_PROJECT_NAME
 - создан docker-compose.override.yml, в котором вынесены файлы для изменения кода каждого из приложений, не выполняя сборку образа

## HW_16

 - Подготовлена инсталляция Gitlab CI
 - Подготовлен репозиторий с кодом приложения
 - Описаны этапы пайплайна
 - Определены окружения

## HW_17

- запущен и настроен prometheus
- настроен мониторинг состояния микросервисов
- настроен сбор метрик с использованием mongodb-exporter, node-exporter, cloudprober
- собранные образы доступны по ссылке https://hub.docker.com/u/leon4eg

## HW_18

 - настроено логгирование docker-контейнеров
 - запущен и настроен стек для сборки логов ElasticSearch/Fluentd/Kibana
 - Fluentd настроен для сборки структурированных и неструктурированных логов
 - подключен распределенный трейсинг приложения с помощью Zipkin

## HW_19

 - запущен и настроен Kubernetes средствами kubeadm

 kubeadm init --pod-network-cidr=10.244.0.0/16 --control-plane-endpoint=node-01.ru-central1.internal --apiserver-advertise-address=10.10.0.19

 - настроена сеть между нодами и мастером с помощью сетевого плагина calico

 NAME      STATUS   ROLES                         AGE   VERSION
node-01   Ready    control-plane,master,worker   34m   v1.22.2
node-02   Ready    worker                        31m   v1.22.2

 - проверен деплой созданых манифестов

NAME                              READY   STATUS    RESTARTS   AGE
post-deployment-799c77ffb-46nmc   1/1     Running   0          9m52s
