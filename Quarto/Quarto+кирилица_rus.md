Quarto

Тут намного всё проще, никаких костылей с header.tex не нужно, шрифты прописываются прям в YAML, кириллица на графике лечится тем же showtext:

---
title: "Cyrillic markdown"
lang: ru
format: pdf
pdf-engine: lualatex
mainfont: Segoe UI
sansfont: Segoe UI
monofont: Cascadia Mono PL Light
editor: visual
---

```{r include = F}
library(showtext)
showtext_auto()
```

----------------------------------------

Локализация

В Quarto достаточно указать в YAML-части документа нужный язык, и документ будет локализован должным образом, например, “Figure” будет заменено на “Рисунок” и т.д. Локализацию можно отнести к преимуществам Quarto, например, в blogdown уже нет такого простого подхода для перевода названия рисунков.

---
title: "Документ"
lang: ru
---

--------------------------------------

R Markdown

Если вы не любитель описывать labs в графиках, а уж тем более кириллицей, то тут можно ограничиться сменой локали прям в markdown-файле, добавив куда-нибудь в начало такую строку:

Sys.setlocale("LC_TIME", "en_US.UTF-8")

Второй вариант — использовать библиотеку showtext:

install.packages("showtext")
library(showtext)

# после загрузки библиотеки, отдаём распознавание на откуп движку
showtext_auto()

Предупреждения ушли, график видит кириллицу как в лабсах, так и в датах

В целом готово. Но мне вообще не нравится как выглядят блоки с кодом. Я люблю для этого использовать шрифты Cascadia Mono PL Light или Cascadia Code Light. Но если шрифт кастомный, просто переписать header.tex не поможет. Я перепробовал разные варианты, и переустановить шрифты, и прописать полное название, и скормить ему весь путь к файлу шрифта — безрезультатно.

В итоге помогла смена движка на lualatex, который тоже поддерживает fontscpec.

---
title: "Cyrillic markdown"
date: "`r Sys.Date()`"
output:
  pdf_document:
    latex_engine: lualatex
    includes:
      in_header: header.tex
---

Сам файл header.tex лежит в папке с нашим markdown-файлом и выглядит примерно так:

\usepackage{fontspec}
\setmainfont{Segoe UI}
\setsansfont{Segoe UI}
\setmonofont{Segoe UI}
\usepackage{polyglossia}
\setmainlanguage{russian}
\setotherlanguage{english}

Ну другое дело же)

-------------------------------

Решается она, например, таким способом:

    В YAML-заголовке указываем движок и включаем дополнения в виде файла header.tex:

---
title: "Cyrillic markdown"
date: "`r Sys.Date()`"
output:
  pdf_document:
    latex_engine: xelatex
    includes:
      in_header: header.tex
---

Сам файл header.tex лежит в папке с нашим markdown-файлом и выглядит примерно так

\usepackage{fontspec}
\setmainfont{Segoe UI}
\setsansfont{Segoe UI}
\setmonofont{Segoe UI}
\usepackage{polyglossia}
\setmainlanguage{russian}
\setotherlanguage{english}

Теперь LaTeX перестанет ругаться и кое-как, но PDF-ку соберёт.


---
title: "Какими программами я пользуюсь в Windows"
lang: ru
format: 
  pdf:
    mainfont: Arial
    sansfont: Arial
    self-contained: true
    toc: true
    toc_depth: 
    theme: cosmo
knitr: 
  opts_chunk: 
    warning: false
    message: false
editor: visual
---
