Если вы используете `pdf_document`, вы можете захотеть добавить оглавление на новой странице, что `toc: true` не позволяет. Оно помещает оглавление сразу после названия документа, автора и даты - потому что оно на yaml.

Если вы хотите разместить его на новой странице, вам придется использовать какой-нибудь язык latex. Вот что я сделал.

```r
---
title: \vspace{3.5in}"Title"
author: "Name"
date: "`r Sys.Date()`"
output:
   pdf_document:
      fig_caption: true
      number_sections: true
---

\newpage # adds new page after title
\tableofcontents # adds table of contents
\listoffigures
\listoftables
\newpage
```

Итак, после yaml (фрагмента между ---) я добавил новую страницу с помощью `\newpage`, затем оглавление с помощью `\tableofcontents`, список рисунков с помощью `\listoffigures`, список таблиц `\listoftables` и новую страницу перед всем остальным.

Обратите внимание, `\vspace{3in}` в заголовке добавляется вертикальный пробел в 3 дюйма сверху перед печатью yaml (title и т.д.).