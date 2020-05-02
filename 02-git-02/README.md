# Домашнее задание к занятию «2.2. Основы Git»

## Задание №1 – Знакомимся с gitlab и bitbucket. 

Иногда при работе с git репозиториями надо настроить свой локальный репозиторий так, что бы можно было 
отправлять и принимать изменения из нескольких удалённых репозиториев. 
Например, это может понадобиться при работе над проектом с открытым исходным кодом, если автор проекта не дает права 
на запись в основной репозиторий. Либо некоторые распределенные команды используют такой принцип работы, когда
каждый разработчик имеет свой репозиторий, а в основной репозиторий пушаться только конечные результаты 
работы над задачами. 

Так же у хорошего специалиста должен быть хороший кругозор, поэтому давайте познакомимся с gitlab и bitbucket.

Создадим аккаунт в gitlab, если у вас его еще нет:
1. Gitlab. Страница регистрации https://gitlab.com/users/sign_up, для регистрации можно использовать 
аккаунт google, github и другие. 
1. После регистрации или авторизации в gitlab создайте новый проект нажав на ссылку `Create a projet`. 
Желательно назвать также как и в гитхабе `devops-netology` и `visibility level` выбрать `Public`.
1. Галочку `Initialize repository with a README` луше не ставить, что бы не пришлось разрешать конфликты.
1. Если вы зарегистрировались при помощи аккаунта в другой система и не указали пароль, то увидите сообщение
`You won't be able to pull or push project code via HTTPS until you set a password on your account`. 
Тогда перейдите по ссылке из этого сообщения (https://gitlab.com/profile/password/edit) и задайте пароль. 
Если вы уже умеете пользоваться ssh ключами, то воспользуйтесь этой возможностью (подробнее про ssh мы поговорим в следующем учебном блоке).
1. Перейдите на страницу созданного вами репозитория, url будет примерно такой:
https://gitlab.com/YOUR_LOGIN/devops-netology и изучите предлагаемые варианты для начала работы в репозитории в секции
`Command line instructions`. 
1. Запомните вывод команды `git remote -v`.
1. В связи с тем, что это будет наш дополнительный репозиторий ни один вариант из перечисленные в инструкции на странице 
вновь созданного репозитория нам не подходит. Поэтому добавляем этот репозиторий как дополнительный `remote` к созданному
репозиторию в рамках предыдущего домашнего задания:
`git remote add gitlab https://gitlab.com/YOUR_LOGIN/devops-netology.git`.
1. Отправьте изменнеия в новый удалённый репозиторий `git push -u gitlab master`.
1. Обратите внимание как изменился результат работы команды `git remote -v`.

Теперь необходимо проделать все тоже самое с https://bitbucket.org/. 
1. Обратите внимание, что репозиторий должен быть публичный, то есть отключите галочку `private repository` при создании репозитория.
1. И на вопрос `Include a README?` отвечаем отказом. 
1. В отличии от гитхаба и гитлаба в битбакете репозиторий должен принадлежать проекту, поэтому во время создания репозитория 
надо создать и проект, который можно назвать, например, `netology`.
1. Аналогично gitlab на странице вновь созданного проекта выберите `https` что бы получить ссылку и добавьте этот репозиторий как 
`git remote add bitbucket ...`.
1. Обратите внимание как изменился результат работы команды `git remote -v`.

Если все проделанно правильно, то вывод команды `git remote -v` должен быть следующий:
```bash
$ git remote -v
bitbucket https://andreyborue@bitbucket.org/andreyborue/devops-netology.git (fetch)
bitbucket https://andreyborue@bitbucket.org/andreyborue/devops-netology.git (push)
gitlab	  https://gitlab.com/andrey.borue/devops-netology.git (fetch)
gitlab	  https://gitlab.com/andrey.borue/devops-netology.git (push)
origin	  https://github.com/andrey-borue/devops-netology.git (fetch)
origin	  https://github.com/andrey-borue/devops-netology.git (push)
```

Дополнительно можете так же добавить удалённые репозитории по `ssh`, тогда вывод будет примерно такое:
```bash
git remote -v
bitbucket	git@bitbucket.org:andreyborue/devops-netology.git (fetch)
bitbucket	git@bitbucket.org:andreyborue/devops-netology.git (push)
bitbucket-https	https://andreyborue@bitbucket.org/andreyborue/devops-netology.git (fetch)
bitbucket-https	https://andreyborue@bitbucket.org/andreyborue/devops-netology.git (push)
gitlab	git@gitlab.com:andrey.borue/devops-netology.git (fetch)
gitlab	git@gitlab.com:andrey.borue/devops-netology.git (push)
gitlab-https	https://gitlab.com/andrey.borue/devops-netology.git (fetch)
gitlab-https	https://gitlab.com/andrey.borue/devops-netology.git (push)
origin	git@github.com:andrey-borue/devops-netology.git (fetch)
origin	git@github.com:andrey-borue/devops-netology.git (push)
origin-https	https://github.com/andrey-borue/devops-netology.git (fetch)
origin-https	https://github.com/andrey-borue/devops-netology.git (push)
```

Выполните push локальной ветки `master` в новые репозитории и приложение ссылку на эти репозитории как результат этой задачи. 
