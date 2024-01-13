Задание 1
Что нужно сделать:

Установите себе jenkins по инструкции из лекции или любым другим способом из официальной документации. Использовать Docker в этом задании нежелательно.
Установите на машину с jenkins golang.
Используя свой аккаунт на GitHub, сделайте себе форк репозитория. В этом же репозитории находится дополнительный материал для выполнения ДЗ.
Создайте в jenkins Freestyle Project, подключите получившийся репозиторий к нему и произведите запуск тестов и сборку проекта go test . и docker build ..
В качестве ответа пришлите скриншоты с настройками проекта и результатами выполнения сборки.
![Image alt](https://github.com/sibrael/git/blob/d00b3d5156d41b7f59a8bf5acce3a9b5cb29405f/1.1.png)
![Image alt](https://github.com/sibrael/git/blob/d00b3d5156d41b7f59a8bf5acce3a9b5cb29405f/1.2.png)
Started by user Udebkin Maksim
Running as SYSTEM
Building in workspace /var/lib/jenkins/workspace/Netology1
The recommended git tool is: NONE
No credentials specified
 > git rev-parse --resolve-git-dir /var/lib/jenkins/workspace/Netology1/.git # timeout=10
Fetching changes from the remote Git repository
 > git config remote.origin.url https://github.com/sibrael/sdvps-materials.git # timeout=10
Fetching upstream changes from https://github.com/sibrael/sdvps-materials.git
 > git --version # timeout=10
 > git --version # 'git version 2.34.1'
 > git fetch --tags --force --progress -- https://github.com/sibrael/sdvps-materials.git +refs/heads/*:refs/remotes/origin/* # timeout=10
 > git rev-parse refs/remotes/origin/main^{commit} # timeout=10
Checking out Revision 223dbc3f489784448004e020f2ef224f17a7b06d (refs/remotes/origin/main)
 > git config core.sparsecheckout # timeout=10
 > git checkout -f 223dbc3f489784448004e020f2ef224f17a7b06d # timeout=10
Commit message: "Update README.md"
 > git rev-list --no-walk 223dbc3f489784448004e020f2ef224f17a7b06d # timeout=10
[Netology1] $ /bin/sh -xe /tmp/jenkins16386452760312674724.sh
+ go test .
ok  	github.com/netology-code/sdvps-materials	(cached)
+ docker build . -t ubuntu-bionic:8082/hello-world:v10
DEPRECATED: The legacy builder is deprecated and will be removed in a future release.
            Install the buildx component to build images with BuildKit:
            https://docs.docker.com/go/buildx/

Sending build context to Docker daemon  250.9kB

Step 1/8 : FROM golang:1.16 AS builder
 ---> 972d8c0bc0fc
Step 2/8 : WORKDIR $GOPATH/src/github.com/netology-code/sdvps-materials
 ---> Using cache
 ---> bfb6dd5ae781
Step 3/8 : COPY . ./
 ---> Using cache
 ---> 38a20fcd733b
Step 4/8 : RUN CGO_ENABLED=0 GOOS=linux go build -a -installsuffix nocgo -o /app .
 ---> Using cache
 ---> f3ef1f480be6
Step 5/8 : FROM alpine:latest
 ---> f8c20f8bbcb6
Step 6/8 : RUN apk -U add ca-certificates
 ---> Using cache
 ---> 4b3c3d9cf4cb
Step 7/8 : COPY --from=builder /app /app
 ---> Using cache
 ---> 18ddbe3f5332
Step 8/8 : CMD ["/app"]
 ---> Using cache
 ---> 558c63ed90d1
Successfully built 558c63ed90d1
Successfully tagged ubuntu-bionic:8082/hello-world:v10
Finished: SUCCESS



---
Задание 2
Что нужно сделать:

Создайте новый проект pipeline.
Перепишите сборку из задания 1 на declarative в виде кода.
В качестве ответа пришлите скриншоты с настройками проекта и результатами выполнения сборки.

![Image alt](https://github.com/sibrael/git/blob/d00b3d5156d41b7f59a8bf5acce3a9b5cb29405f/2.png)

Started by user Udebkin Maksim
[Pipeline] Start of Pipeline
[Pipeline] node
Running on Jenkins in /var/lib/jenkins/workspace/Netology2
[Pipeline] {
[Pipeline] stage
[Pipeline] { (Git)
[Pipeline] git
The recommended git tool is: NONE
No credentials specified
 > git rev-parse --resolve-git-dir /var/lib/jenkins/workspace/Netology2/.git # timeout=10
Fetching changes from the remote Git repository
 > git config remote.origin.url https://github.com/netology-code/sdvps-materials.git # timeout=10
Fetching upstream changes from https://github.com/netology-code/sdvps-materials.git
 > git --version # timeout=10
 > git --version # 'git version 2.34.1'
 > git fetch --tags --force --progress -- https://github.com/netology-code/sdvps-materials.git +refs/heads/*:refs/remotes/origin/* # timeout=10
 > git rev-parse refs/remotes/origin/master^{commit} # timeout=10
Checking out Revision da5acf7bcb7f437637adf06fbd03a24dc2c8f13e (refs/remotes/origin/master)
 > git config core.sparsecheckout # timeout=10
 > git checkout -f da5acf7bcb7f437637adf06fbd03a24dc2c8f13e # timeout=10
 > git branch -a -v --no-abbrev # timeout=10
 > git checkout -b master da5acf7bcb7f437637adf06fbd03a24dc2c8f13e # timeout=10
Commit message: "branch main, add creds for vagrant box"
First time build. Skipping changelog.
[Pipeline] }
[Pipeline] // stage
[Pipeline] stage
[Pipeline] { (Test)
[Pipeline] sh
+ go test .
ok  	github.com/netology-code/sdvps-materials	0.001s
[Pipeline] }
[Pipeline] // stage
[Pipeline] stage
[Pipeline] { (Build)
[Pipeline] sh
+ docker build . -t ubuntu-bionic:8082/hello-world:v5
DEPRECATED: The legacy builder is deprecated and will be removed in a future release.
            Install the buildx component to build images with BuildKit:
            https://docs.docker.com/go/buildx/

Sending build context to Docker daemon  242.2kB

Step 1/8 : FROM golang:1.16 AS builder
 ---> 972d8c0bc0fc
Step 2/8 : WORKDIR $GOPATH/src/github.com/netology-code/sdvps-materials
 ---> Using cache
 ---> bfb6dd5ae781
Step 3/8 : COPY . ./
 ---> 01858e705251
Step 4/8 : RUN CGO_ENABLED=0 GOOS=linux go build -a -installsuffix nocgo -o /app .
 ---> Running in 8589d4d2fbf3
Removing intermediate container 8589d4d2fbf3
 ---> 9dd1e7f8ba51
Step 5/8 : FROM alpine:latest
 ---> f8c20f8bbcb6
Step 6/8 : RUN apk -U add ca-certificates
 ---> Using cache
 ---> 4b3c3d9cf4cb
Step 7/8 : COPY --from=builder /app /app
 ---> Using cache
 ---> 18ddbe3f5332
Step 8/8 : CMD ["/app"]
 ---> Using cache
 ---> 558c63ed90d1
Successfully built 558c63ed90d1
Successfully tagged ubuntu-bionic:8082/hello-world:v5
[Pipeline] }
[Pipeline] // stage
[Pipeline] }
[Pipeline] // node
[Pipeline] End of Pipeline
Finished: SUCCESS

---
Задание 3
Что нужно сделать:

Установите на машину Nexus.
Создайте raw-hosted репозиторий.
Измените pipeline так, чтобы вместо Docker-образа собирался бинарный go-файл. Команду можно скопировать из Dockerfile.
Загрузите файл в репозиторий с помощью jenkins.
В качестве ответа пришлите скриншоты с настройками проекта и результатами выполнения сборки.

---
Задание 4*
Придумайте способ версионировать приложение, чтобы каждый следующий запуск сборки присваивал имени файла новую версию. Таким образом, в репозитории Nexus будет храниться история релизов.

Подсказка: используйте переменную BUILD_NUMBER.

В качестве ответа пришлите скриншоты с настройками проекта и результатами выполнения сборки.
