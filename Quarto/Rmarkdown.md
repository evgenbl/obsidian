 
### Монтаж

Как и остальная часть R, R Markdown бесплатен и имеет открытый исходный код. Вы можете установить пакет R Markdown из CRAN с помощью:

- R

- install.packages("rmarkdown")

Если вы хотите использовать разрабатываемую версию пакета rmarkdown (с RStudio или без него), вы можете установить пакет с GitHub через Remotes пакет :

- \# install.packages("pak")

- pak::pak('rstudio/rmarkdown')

[Сайт:](https://rmarkdown.rstudio.com/lesson-1.html)

---

вы всегда можете указать зеркало, откуда загружать пакеты самостоятельно, используя параметр `repos` . При этом R больше не будет спрашивать вас о репозитории. Пример:

```r
install.packages('rmarkdown', repos='http://cran.us.r-project.org')
```

Здесь у вас есть [список зеркал](https://translated.turbopages.org/proxy_u/en-ru.ru.f14d6fba-66aedd67-f1682b8f-74722d776562/cran.r-project.org/mirrors.html) для R.

---


