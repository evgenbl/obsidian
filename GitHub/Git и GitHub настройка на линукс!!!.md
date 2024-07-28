Шаг 1: Убедитесь, что у вас установлен Git на вашем Linux-устройстве. Если нет, выполните следующую команду:  
sudo apt-get install git  
  
Шаг 2: Когда Git установлен, следующим шагом является настройка вашего имени пользователя и адреса электронной почты. Выполните следующие команды, заменив "Your Name" и "[your@email.com](mailto:your@email.com)":  
git config —global [user.name](https://vk.com/away.php?to=http%3A%2F%2Fuser.name&post=816080364_53&cc_key=) "Your Name"  
git config —global [user.email](https://vk.com/away.php?to=http%3A%2F%2Fuser.email&post=816080364_53&cc_key=) "[your@email.com](mailto:your@email.com)"  
  
Шаг 3: Прежде чем мы начнем использовать Git, нам нужно создать новый репозиторий на GitHub. Зайдите на сайт GitHub, войдите в свою учетную запись и нажмите кнопку "New repository".  
  
Шаг 4: Теперь, когда есть репозиторий на GitHub, свяжем его с нашим локальным Git-репозиторием. Перейдите в каталог вашего проекта и выполните следующие команды:  
git init  
git remote add origin [https://github.com/username/repository.git](https://vk.com/away.php?to=https%3A%2F%2Fgithub.com%2Fusername%2Frepository.git&post=816080364_53&cc_key=)  
  
Здесь "username" - ваше имя пользователя на GitHub, а "repository" - название вашего репозитория.

---
**Зарегистрироваться на сайте GitHub:** [https://github.com/](https://github.com/)

После того как зарегистрируетесь на GitHub создайте репозиторий. Нажмите на главной странице кнопку **Start a project**. Далее необходимо ввести название репозитория в следующем формате!:

> вашлогин.github.io

Если назвать репозиторий по-другому, то он не будет доступен как домен. Т.е. _вашлогин.github.io_ вы сможете открыть в любого устройства как сайт.

После того как создали репозиторий скопируйте на его главной странице в самом верху ссылку формата:

> https://github.com/вашлогин/название репозитория.git

#### **Отправляем файлы сайта Jekyll на GitHub**

Перейдите в любой удобный каталог, где будете создавать локальный репозиторий. Нажмите в нем правой кнопкой мыши и выберите в контекстном меню _Git Bash Here_(_открыть терминал_). В открывшемся терминале введите команду:

`git clone https://github.com/вашлогин/название репозитория.git`

В папке будет создана локальная копия вашего репозитория с именем _вашлогин.github.io_. Пока пустая. Скопируйте в эту папку файлы своего сайта. Вернитесь в терминал и перейдите в данную папку:


`git config --global user.name "My name"`

`git config --global user.email "myname@mail.ru"`

`git add .`

`git commit -m "comment"`

`git push -u origin master(main)`
`

При выполнении последней команды терминал спросит ваш логин и пароль от учетной записи на GitHub. Введите их и подождите когда сайт скопируется на хостинг.

[Перенос сайта Jekyll на GitHub](https://www.youtube.com/watch?v=PXKPI2e1zZY)


[![](https://markdown-videos.vercel.app/youtube/PXKPI2e1zZY)](https://www.youtube.com/watch?v=PXKPI2e1zZY)

---


