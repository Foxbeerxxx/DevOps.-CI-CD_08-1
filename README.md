# Домашнее задание к занятию "`Что такое DevOps. CI/CD`" - `Татаринцев Алексей`


### Инструкция по выполнению домашнего задания

   1. Сделайте `fork` данного репозитория к себе в Github и переименуйте его по названию или номеру занятия, например, https://github.com/имя-вашего-репозитория/git-hw или  https://github.com/имя-вашего-репозитория/7-1-ansible-hw).
   2. Выполните клонирование данного репозитория к себе на ПК с помощью команды `git clone`.
   3. Выполните домашнее задание и заполните у себя локально этот файл README.md:
      - впишите вверху название занятия и вашу фамилию и имя
      - в каждом задании добавьте решение в требуемом виде (текст/код/скриншоты/ссылка)
      - для корректного добавления скриншотов воспользуйтесь [инструкцией "Как вставить скриншот в шаблон с решением](https://github.com/netology-code/sys-pattern-homework/blob/main/screen-instruction.md)
      - при оформлении используйте возможности языка разметки md (коротко об этом можно посмотреть в [инструкции  по MarkDown](https://github.com/netology-code/sys-pattern-homework/blob/main/md-instruction.md))
   4. После завершения работы над домашним заданием сделайте коммит (`git commit -m "comment"`) и отправьте его на Github (`git push origin`);
   5. Для проверки домашнего задания преподавателем в личном кабинете прикрепите и отправьте ссылку на решение в виде md-файла в вашем Github.
   6. Любые вопросы по выполнению заданий спрашивайте в чате учебной группы и/или в разделе “Вопросы по заданию” в личном кабинете.
   
Желаем успехов в выполнении домашнего задания!
   
### Дополнительные материалы, которые могут быть полезны для выполнения задания

1. [Руководство по оформлению Markdown файлов](https://gist.github.com/Jekins/2bf2d0638163f1294637#Code)

---

### Задание 1



1. `Установите себе jenkins по инструкции из лекции или любым другим способом из официальной документации. Использовать Docker в этом задании нежелательно.`
`Ответ: Устанавливаем java`
```
sudo apt install openjdk-11-jdk 
```
![Установка java](https://github.com/Foxbeerxxx/DevOps.-CI-CD_08-1/blob/main/img/img1.png)`

`Импортируем ключ репозитория для jenkins.`
```
wget -q -O - https://pkg.jenkins.io/debian/jenkins.io.key | sudo apt-key add -
```
![ключ репозитория для jenkins](https://github.com/Foxbeerxxx/DevOps.-CI-CD_08-1/blob/main/img/img2.png)`

`Затем устанавливаем Jenkins из пакета для debian/ubuntu:`
```
sudo apt-get update
sudo apt-get install jenkins
```
`Сразу сервис не заработал, пришлось выполнить траблшутинг , в результате jenkins не устроила версия Java,но после запустил и все заработало`
```
sudo -u jenkins /usr/bin/jenkins
```
![ключ репозитория для jenkins](https://github.com/Foxbeerxxx/DevOps.-CI-CD_08-1/blob/main/img/img3.png)`

`Проверяем результат в браузере и видим:`
![jenkins](https://github.com/Foxbeerxxx/DevOps.-CI-CD_08-1/blob/main/img/img4.png)`
`Готово`
2. `Установите на машину с jenkins golang`
`Ответ:`
`Установим необходимые утилиты
```
   sudo apt update
   sudo apt install wget tar`
```
`Приступаем к установке`
`Скачиваем последнюю версию Go` 
```
wget https://golang.org/dl/go1.20.5.linux-amd64.tar.gz
```
`Распаковывем` 
```
sudo tar -C /usr/local -xzvf go1.20.5.linux-amd64.tar.gz
```
`Устанавливаем переменную окружения` 
```
echo "export PATH=$PATH:/usr/local/go/bin" >> ~/.bashrc
   source ~/.bashrc
```
`Проверяем версию GO`
```
go version
```
`Затем заходим в jenkins и в настройках устанавливаем GO`
![Установка](https://github.com/Foxbeerxxx/DevOps.-CI-CD_08-1/blob/main/img/img5.png)`

![Установка](https://github.com/Foxbeerxxx/DevOps.-CI-CD_08-1/blob/main/img/img6.png)`

`После установки лучше перезагрузить jenkins`
![Перезагрузка](https://github.com/Foxbeerxxx/DevOps.-CI-CD_08-1/blob/main/img/img7.png)`
3. `Скопировал репозиторий`
![копирование](https://github.com/Foxbeerxxx/DevOps.-CI-CD_08-1/blob/main/img/img8.png)`
4. `Создал в Jenkins новую джобу по условию 1.4 как итог, он не запустится так как  сервер не подготовлен не по докеру не по Nexys, выполнится лишь` 
`первое  условие это копирование репозитория`

![<Джоба>](https://github.com/Foxbeerxxx/DevOps.-CI-CD_08-1/blob/polomka/img/img9.png)`

5. ` Делаем траблшутинг , поднимаем nexus, ставим докер как итог ` 
`Джоба уже прогружается гараздо дальше`

![<Джоба1>](https://github.com/Foxbeerxxx/DevOps.-CI-CD_08-1/blob/polomka/img/img10.png)`


6. ` Поднятый nexus c настройками ` 

![<Джоба1>](https://github.com/Foxbeerxxx/DevOps.-CI-CD_08-1/blob/polomka/img/img11.png)`

7. ` Первое задание закрыл`
![<Джоба2>](https://github.com/Foxbeerxxx/DevOps.-CI-CD_08-1/blob/polomka/img/img12.png)`

![<Джоба3>](https://github.com/Foxbeerxxx/DevOps.-CI-CD_08-1/blob/polomka/img/img13.png)`




---

### Задание 2

`Создайте новый проект pipeline.`

1. `Заходим в Jenkins и создаем новый pipline`
`С кодом:`
```
pipeline {
    agent any

    stages {
        stage('Git') {
            steps {
                // Клонируем репозиторий
                git 'https://github.com/Foxbeerxxx/sdvps-materials-test.git'
            }
        }
        
        stage('Test') {
            steps {
                // Запускаем тесты с использованием правильного пути к Go
                sh '/usr/local/go/bin/go test ./...'
            }
        }
        
        stage('Build') {
            steps {
                // Строим образ Docker
                sh "docker build . -t ubuntu-bionic:8082/hello-world:v${env.BUILD_NUMBER}"
            }
        }
    }
}
```
`Запускаем сборку`
![<Джоба5>](https://github.com/Foxbeerxxx/DevOps.-CI-CD_08-1/blob/polomka/img/img14.png)

`Видим`
![<Джоба6>](https://github.com/Foxbeerxxx/DevOps.-CI-CD_08-1/blob/polomka/img/img15.png)

![<Джоба6>](https://github.com/Foxbeerxxx/DevOps.-CI-CD_08-1/blob/polomka/img/img16.png)


---

### Задание 3



1. `Устанавливаем на машину Nexus`

![<1>](https://github.com/Foxbeerxxx/DevOps.-CI-CD_08-1/blob/polomka/img/1.png)
2. `Создаём raw-hosted репозиторий`

![<2>](https://github.com/Foxbeerxxx/DevOps.-CI-CD_08-1/blob/polomka/img/2.png)
3. `Изменяем pipeline так, чтобы вместо Docker-образа собирался бинарный go-файл`
```
pipeline {
    agent any
    stages {
        stage('Git') {
            steps {
                git url: 'https://github.com/Foxbeerxxx/sdvps-materials-test.git', branch: 'main'
            }
        }
        stage('Test') {
            steps {
                sh '/usr/local/go/bin/go test ./...'
            }
        }
        stage('Build') {
            steps {
                // Сохраняем исполняемый файл в рабочую директорию Jenkins
                sh 'CGO_ENABLED=0 GOOS=linux /usr/local/go/bin/go build -a -installsuffix nocgo -o ./app'
            }
        }
    }
}
```

![<3>](https://github.com/Foxbeerxxx/DevOps.-CI-CD_08-1/blob/polomka/img/3.png)
![<4>](https://github.com/Foxbeerxxx/DevOps.-CI-CD_08-1/blob/polomka/img/4.png)
![<5>](https://github.com/Foxbeerxxx/DevOps.-CI-CD_08-1/blob/polomka/img/5.png)

4. `Загружаем файл в репозиторий с помощью jenkins`
`Создал новый pipline на основе предыдущего с загрузкой репозитория в nexus`
```
pipeline {
    agent any
    stages {
        stage('Git') {
            steps {
                git url: 'https://github.com/Foxbeerxxx/sdvps-materials-test.git', branch: 'main'
            }
        }
        stage('Test') {
            steps {
                sh '/usr/local/go/bin/go test ./...'
            }
        }
        stage('Build') {
            steps {
                // Сохраняем исполняемый файл в рабочую директорию Jenkins
                sh 'CGO_ENABLED=0 GOOS=linux /usr/local/go/bin/go build -a -installsuffix nocgo -o ./app'
            }
        }
        stage('Upload to Nexus') {
            steps {
                // Замените FILE на ваш действительный файл
                sh '''
                   FILE=app
                   curl -u "admin:Cnews220" \
                        --upload-file $FILE \
                        http://localhost:8081/repository/my_raw/$FILE
                   '''
            }
        }
    }
}
```

![<6>](https://github.com/Foxbeerxxx/DevOps.-CI-CD_08-1/blob/polomka/img/6.png)
![<7>](https://github.com/Foxbeerxxx/DevOps.-CI-CD_08-1/blob/polomka/img/7.png)
