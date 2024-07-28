Установить Git:

$ sudo apt-get install git

*Добавить имя пользователя и адрес электронной почты*

$ git config --global user.name "username" ()

$ git config --global user.email "email" ()

Зайдите на сайт GitHub, войдите в свою учетную запись и нажмите кнопку "New repository".

Теперь, когда есть репозиторий на GitHub, свяжем его с нашим локальным Git-репозиторием. Перейдите в каталог вашего проекта и выполните следующие команды:

$ git init

$ git remote add origin https://github.com/username/repository.git

Здесь "username" - ваше имя пользователя на GitHub, а "repository" - название вашего репозитория.

Клонировать с git-а:

$ git clone https://github.com/evgenbl/evgenbl.github.io

Отправить на git:

$ git add .

$ git status

$ git commit -m "new"

($ git push -u origin master(или main)) - иногда просит

$ git push

$ username: 

$ pass(token): 

The token will expire on Wed, Apr 20 2024

blog:

https://evgenbl.github.io/

https://evgenbl.github.io/Resume/

new blog:

https://evgenbl.github.io/blog/

