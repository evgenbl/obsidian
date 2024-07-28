### Для пользователей R

Установка и поддержка TinyTeX проста для пользователей R, поскольку пакет Tinytex R предоставляет функции-оболочки (обратите внимание: строчные буквы и жирный шрифт tinytex означают пакет R , а TinyTeX в верблюжьем регистре означает дистрибутив LaTeX ). Вы можете использовать tinytex для установки TinyTeX:

install.packages('tinytex')

tinytex::install_tinytex()

\# to uninstall TinyTeX, run tinytex::uninstall_tinytex()

Чтобы скомпилировать документ R Markdown в PDF, вам больше ничего не нужно знать.

### Монтаж

Бинарные пакеты TinyTeX выпускаются ежемесячно в репозитории Github github.com/rstudio/tinytex-releases

Для пользователей Linux TinyTeX будет установлен на $HOME/.TinyTeX и символические ссылки исполняемых файлов (например, pdflatex) создаются под

- $HOME/bin

(или $HOME/.local/binесли он существует)

который должен быть на PATH переменная среды:

\# make sure perl is properly installed (e.g., apt install -y perl)

- perl -mFile::Find /dev/null

\# then install TinyTeX

- wget -qO- "https://yihui.org/tinytex/install-bin-unix.sh" | sh

Чтобы удалить TinyTeX, просто удалите папку из файлового менеджера/браузера или используйте командную строку:

\# Linux

tlmgr path remove

rm -r "~/.TinyTeX"


\# Windows

tlmgr path remove

rd /s /q "%APPDATA%\TinyTeX"

----
### Монтаж

Бинарные пакеты TinyTeX выпускаются ежемесячно в репозитории Github [github.com/rstudio/tinytex-releases](https://github.com/rstudio/tinytex-releases "https://github.com/rstudio/tinytex-releases") .

Для пользователей Linux TinyTeX будет установлен на `$HOME/.TinyTeX`и символические ссылки исполняемых файлов (например, `pdflatex`) создаются под `$HOME/bin`(или `$HOME/.local/bin`если он существует), который должен быть на `PATH`переменная среды:

\# make sure perl is properly installed (e.g., apt install -y perl)
perl -mFile::Find /dev/null
\# then install TinyTeX
wget -qO- "https://yihui.org/tinytex/install-bin-unix.sh" | sh

---

