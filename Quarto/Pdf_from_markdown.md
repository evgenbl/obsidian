#### pandoc+кириллица

%!TeX program = xelatex
---
classoption: a4paper
documentclass: article
fontsize: 6pt
title: Title text
author: "Your name"
date: "22/5/2020"
geometry:
- top=0cm
- bottom=1cm
- left=0.25cm
- right=0.25cm
output:
  pdf_document: default
toc: true
linkcolor: blue
lang: ru
header-includes: |
    \newfontfamily{\cyrillicfont}{Arial}
    \newfontfamily{\cyrillicfontrm}{Arial}
    \newfontfamily{\cyrillicfonttt}{Arial}
    \newfontfamily{\cyrillicfontsf}{Arial}
---
## sec 1

nmcli device wifi connect your_wifi password your_password

вапвпвыпрп margin=0.1in

## sec 2

pandoc+кириллица

__________________________________________________________

pandoc test.md -s -o test.pdf --latex-engine=xelatex
pandoc test.md -s -o test.pdf --pdf-engine=xelatex (convert)
___________________________________________________________

[ya](https://ya.ru/?sso_failed=blocked&uuid=f465ca85-bdee-418a-906f-328623f3c821)
[Основы работы с PDF-файлами ](https://quarto.org/docs/output-formats/pdf-basics.html)

