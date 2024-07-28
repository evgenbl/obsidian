### Установка tinytex

#### Июнь 16, 2018

*Если есть возможность, то лучше поставить полный дистрибутив Латеха, например, texlive.*

Однако бывают ситуации, когда тех нужно поставить, а ни времени, ни достаточного объёма жесткого диска нет.

Поехали!

Ставим из Rstudio пакет tinytex.

install.packages('tinytex')

Ставим самую минимальную версию TinyTex:

tinytex::install_tinytex()

Под windows во время инсталляции может появляться окно с предупреждением, что не хватает файла lualatex.dll, ничего страшного. Смело жмём ок и продолжаем.

Перезапускаем Rstudio.

Ставим дополнительные пакеты Latex для русского языка и типичного Rmd-файла

popular_packs <- c('babel-russian', 'cyrillic', 'cm-super',
                    'lh', 'makecmds', 'polyglossia', 'ulem',
                    'siunitx', 'multirow', 'xcolor', 'colortbl')

tinytex::tlmgr_install(popular_packs)

Ставим небольшую подборку русскоязычных Rmd-шаблонов

devtools::install_github('bdemeshev/azbuka')