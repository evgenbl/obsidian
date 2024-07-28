#### Рендеринг(перезаписать)

Форматы, указанные в параметрах документа, определяют, что отображается по умолчанию.

Если мы визуализируем документ со всеми приведенными выше параметрами, используя следующее.

#### Терминал

quarto render authoring.qmd authoring.html

quarto render authoring.qmd authoring.pdf

quarto render authoring.qmd authoring.docx

Затем будут созданы следующие файлы.

    authoring.html
    authoring.pdf
    authoring.docx

Мы можем выбрать один или несколько форматов, используя --to вариант.

#### Quarto in Rstudio

Создать документ(в примере html):
---
title: Quarto Basics
author: Norah Jones
date: 'May 22, 2021'
format:
    html:
        self-contained: true    # (только один файл)
toc: true
number-sections: true
editor: visual
---

## Colors

- Red
- Green
- Blue

## Shapes

- Square
- Circle
- Triangle

## Textures

- Smooth
- Bumpy
- Fuzzy

* Сохранить под именем и расширением: authoring.qmd

* Вот как выглядит этот документ при рендеринге в HTML

#### Перезаписать в нужный формат:

quarto render authoring.qmd --to docx
quarto render authoring.qmd --to pdf
quarto render authoring.qmd --to html
quarto render authoring.qmd --to docx,pdf

Обратите внимание, что целевой файл (в данном случае authoring.qmd) всегда должен быть самым первым аргументом командной строки.

При необходимости мы также можем отображать форматы, которые не указаны в параметрах документа.

#### Терминал

quarto render authoring.qmd --to odt

Поскольку odt Формат не включен в параметры документа, будут использоваться параметры формата по умолчанию.

#### Разделы

Вы можете использовать оглавление и/или нумерацию разделов, чтобы читателям было легче ориентироваться в документе.

Сделайте это, добавив toc и/или number-sections варианты документирования вариантов.

Обратите внимание, что эти параметры обычно указываются на корневом уровне, поскольку они используются во всех форматах.

Существует множество опций для управления поведением оглавления и нумерации разделов. см. в документации по выходному формату (например, HTML , PDF , MS Word )

About:

  <hr class="about-sep">
   <div class="about-links">
      <a href="https://vk.com/jenit777" class="about-link" rel="" target="">
      <span class="about-link-text">VK</span></a>
   </div>
