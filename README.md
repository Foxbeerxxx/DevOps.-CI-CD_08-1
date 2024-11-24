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
![Перезагрузка](https://github.com/Foxbeerxxx/DevOps.-CI-CD_08-1/blob/main/img/img6.png)`










3. `Заполните здесь этапы выполнения, если требуется ....`
4. `Заполните здесь этапы выполнения, если требуется ....`
5. `Заполните здесь этапы выполнения, если требуется ....`
6. 

```
Поле для вставки кода...
....
....
....
....
```

`При необходимости прикрепитe сюда скриншоты
![Название скриншота 1](ссылка на скриншот 1)`


---

### Задание 2

`Приведите ответ в свободной форме........`

1. `Заполните здесь этапы выполнения, если требуется ....`
2. `Заполните здесь этапы выполнения, если требуется ....`
3. `Заполните здесь этапы выполнения, если требуется ....`
4. `Заполните здесь этапы выполнения, если требуется ....`
5. `Заполните здесь этапы выполнения, если требуется ....`
6. 

```
Поле для вставки кода...
....
....
....
....
```

`При необходимости прикрепитe сюда скриншоты
![Название скриншота 2](ссылка на скриншот 2)`


---

### Задание 3

`Приведите ответ в свободной форме........`

1. `Заполните здесь этапы выполнения, если требуется ....`
2. `Заполните здесь этапы выполнения, если требуется ....`
3. `Заполните здесь этапы выполнения, если требуется ....`
4. `Заполните здесь этапы выполнения, если требуется ....`
5. `Заполните здесь этапы выполнения, если требуется ....`
6. 

```
Поле для вставки кода...
....
....
....
....
```

`При необходимости прикрепитe сюда скриншоты
![Название скриншота](ссылка на скриншот)`

### Задание 4

`Приведите ответ в свободной форме........`

1. `Заполните здесь этапы выполнения, если требуется ....`
2. `Заполните здесь этапы выполнения, если требуется ....`
3. `Заполните здесь этапы выполнения, если требуется ....`
4. `Заполните здесь этапы выполнения, если требуется ....`
5. `Заполните здесь этапы выполнения, если требуется ....`
6. 

```
Поле для вставки кода...
....
....
....
....
```

`При необходимости прикрепитe сюда скриншоты
![Название скриншота](ссылка на скриншот)`
