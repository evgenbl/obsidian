RStudio для ALT p10 ставится и работает из rpm-пакета для OpenSuSe 15 с помощью epm.

Сначала нужно поставить зависимости

apt-get install -y eepm libpq5 libsqlite sqlite R-base R-devel R-doc-html rpm-build-python3 rpm-build-python

потом поставить сам RStudio

cd ~/Downloads

wget -c https://s3.amazonaws.com/rstudio-ide-build/desktop/opensuse15/x86_64/rstudio-2021.09.3-396-x86_64.rpm

epm install --repack rstudio-2021.09.3-396-x86_64.rpm

И в результате RStudio полноценно зарегистрируется в системе вместе с ярлыками и будет работать.

Нужно подождать когда эта версия появится в репозитории p10, тогда вы сможете обновлять RStudio одной командой:

epm play rstudio

Уже обновляется.Проверил 23-03-2024.


https://www.youtube.com/watch?v=4rKWIJXe3mA&list=PLEzw67WWDg80-fT1hq2IZf7D62tRmKy8f
