В качестве UNIX я выбрал самый популярный дистрибутив UNIX: FreeBSD. В этом руководстве я использую FreeBSD 13 со средой рабочего стола GNOME, но та же процедура установки применима и к другим средам рабочего стола или менеджерам Windows.

1. Установите язык R, открыв терминал, переключившись на пользователя root (su -) и набрав:

```
pkg install r
```

Бам! Язык R установлен во FreeBSD!

**2. Установите RStudio IDE во FreeBSD.** Чтобы установить RStudio, в терминале введите от имени пользователя root:

```
pkg install RStudio
```

Альтернативно вы можете собрать пакет RStudio из [**_Freshports_**](https://www.freshports.org/devel/RStudio) , выполнив следующую команду от имени пользователя root:

```
cd /usr/ports/devel/RStudio/ && make install clean
```

[Необязательно] RStudio требует, **чтобы /proc** был смонтирован в **/etc/fstab** . Чтобы отредактировать **/etc/fstab** , используйте текстовый редактор ee или установите _nano_ , выполнив следующую команду от имени пользователя root:

```
pkg install nano
```

3. Затем отредактируйте файл **/etc/fstab** :

```
nano /etc/fstab
```

4. Добавьте следующую строку в **файл /etc/fstab** :

```
proc /proc procfs rw 0 0
```
ваш **файл /etc/fstab должен выглядеть следующим образом:** После добавления приведенной выше строки

![Процедура монтирования FreeBSD в fstab.  Источник: uedufy.com](https://lh3.googleusercontent.com/KY4Og0OKUMGlfLKtxz2Uzst2W3qtQKn6b6GVwFbWUo_QUHk9NEDBArXBj6QbPal7ehg-k8SBquNITMmU23bhq-msKDdnkCjoIWqhSnwbigDDKv-aQMeK6DK0Er_4Hxe44h5Du9M)

**Сохраните** и **закройте** файл _fstab_ (нажмите **Ctrl+X,** затем введите **Y** , чтобы сохранить).

5. Смонтируйте **/proc** , выполнив следующую команду:

```
mount /proc
```

6. Вы можете запустить RStudio, запустив приложение или набрав в терминале:

```
Rstudio
```

Теперь вы готовы писать код на **_R_** в **FreeBSD** **операционной системе** .


