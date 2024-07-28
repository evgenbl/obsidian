Это руководство нацелено на первое знакомство с LaTeX и предварительных знаний о нем от вас не потребует. К его завершению вы уже напишете свой первый документ и получите представление о ряде базовых возможностей этого инструмента.  
 
 ## Что такое LaTeX?
 
LaTEX (произносится как «лэйтех» или «латех») представляет собой инструмент для создания профессиональных документов. В его основе лежит парадигма редактирования WYSIWYM (что вижу, то и подразумеваю), то есть от пользователя требуется сосредоточиться только на содержимом документа, оставив его форматирование программе. Вместо ручного распределения текста по странице, как это делается в Microsoft Word или LibreOffice Writer, можно просто его вводить, позволив LaTeX заняться остальным.  

## Зачем нужен LaTeX?

Этот инструмент используется повсеместно для создания научных документов, написания книг, а также многих других форм публикаций. Он позволяет не только создавать красиво оформленные документы, но также дает пользователям возможность очень быстро реализовывать такие сложные элементы печатного набора, как математические выражения, таблицы, ссылки и библиографии, получая согласованную разметку по всем разделам.  
  
Благодаря доступности большого числа открытых библиотек (об этом чуть позже) возможности LaTEX становятся практически безграничны. Эти библиотеки расширяют возможности пользователей еще больше, позволяя добавлять сноски, рисовать схемы и пр.  
  
Одна из наиболее веских причин, по которой многие используют LaTeX, заключается в отделении содержания документа от его стиля. Это означает, что после написания содержимого, можно с легкостью изменять его внешний вид. Аналогичным образом, можно создать один стиль документа и использовать его для стандартизации внешнего вида других.  
  
Это позволяет научным журналам создавать шаблоны для предлагаемых на рассмотрение материалов. Такие шаблоны имеют заданную разметку, в результате чего добавить остается лишь содержание. На деле существуют сотни подобных шаблонов, начиная с различных резюме и заканчивая презентациями слайдов.  
 
  ## Пишем первый документ

  
Изначально нам потребуется новый проект, начать который можно либо создав файл `.tex`, либо [через Overleaf](https://www.overleaf.com/learn/latex/Creating_a_document_in_Overleaf). Возьмем простейший пример:  
  

```
\documentclass{article}

\begin{document}
First document. This is a simple example, with no 
extra parameters or packages included.
\end{document}
```

  

![](https://habrastorage.org/r/w1560/webt/oy/hp/tq/oyhptqpq6fw7xtsxaq2glig6yte.png)

  
Здесь мы видим, что LaTeX уже позаботился о первом элементе форматирования, сделав отступ в начальной строке абзаца. Теперь более подробно рассмотрим, за что отвечает каждая часть кода.  
  
[Открыть пример в Overleaf](https://www.sharelatex.com/project/new/template?zipUrl=/project/582dbc33f220531c2d4bda27/download/zip&templateName=Learn%20LaTeX%20in%2020%20minutes:%20Part%201&compiler=pdflatex)  
  
Первая строка объявляет тип документа, называемый классом. Класс определяет общее представление документа. Для разных типов документов требуются разные классы, то есть для CV/резюме будет использоваться свой класс, а для научного труда свой. В данном случае классом является `article`, самый простой и распространенный в LaTeX. Другие типы документов, с которыми вам, возможно, придется работать, могут потребовать использования других классов, например `book` или `report`.  
  
После этого мы пишем содержание документа, заключенное в теги `\begin{document}` и `\end{document}`, представляющие его тело. Можете начать писать здесь текст и при желании вносить в него изменения.  
  
Чтобы увидеть результат этих изменений в PDF, документ нужно скомпилировать. В Overleaf для этого нужно просто нажать **Recompile**. (Также можете настроить проект на автоматическую перекомпиляцию в процессе редактирования файлов, нажав на небольшую стрелку рядом с кнопкой **Recompile** и установив **Auto Compile** как **On**).  
  
Если вы используете базовый текстовый редактор, например _gedit_, _emacs_, _vim_, _sublime_, блокнот и пр., то нужно будет компилировать документ вручную. Для этого просто выполните в терминале `pdflatex <your document>`. Подробнее об этом процессе можете почитать [здесь](https://en.wikibooks.org/wiki/LaTeX/Basics#Compilation).  
  
При использовании [специального редактора LaTeX](https://en.wikibooks.org/wiki/LaTeX/Installation#Editors) вроде _TeXmaker_ или _TeXworks_ нужно просто нажать кнопку **Recompile**. Если не знаете, где она находится, обратитесь к документации.  
  
Теперь, когда вы разобрались, как добавлять в документ содержимое, следующим шагом будет его именование. Для этого необходимо вкратце разобрать преамбулу.  
  

## Преамбула документа

  
В предыдущем примере текст вводился после команды `\begin{document}`. Все, что содержится в файле `.tex` до этого места, называется преамбулой. В ней можно определить тип создаваемого документа, используемый язык, нужные библиотеки (подробнее позже) и ряд других элементов. Вот пример типичной преамбулы:  
  

```
\documentclass[12pt, letterpaper]{article}
\usepackage[utf8]{inputenc}
```

  
А вот подробное разъяснение каждой строки:  
  

```
\documentclass[12pt, letterpaper]{article}
```

  
Как уже говорилось, этой командой определяется тип документа. В нее также можно передавать дополнительные параметры, включенные в квадратные скобки через запятую. В данном примере эти параметры устанавливают размер шрифта (`12pt`) и размер страницы (`letterpaper`). Конечно же, для шрифта можно установить и другие размеры (`9pt`, `11pt`, `12pt`), но если размер не задан, то предустановленным значением будет `10pt`. Что же касается размера страницы, то для него доступны варианты `a4paper`и `legalpaper`. Подробнее об этом можете почитать в статье [Page size and margins](https://www.overleaf.com/learn/latex/Page_size_and_margins).  
  

```
\usepackage[utf8]{inputenc}
```

  
Эта команда задает кодировку документа. Ее можно опустить либо изменить на другой вариант, но рекомендуется использовать именно utf-8. Если вам не требуется конкретно другая кодировка, либо вы просто не уверены, то добавьте эту строку во вступление.  
  

## Добавление заголовка, автора и даты

  
Для добавления в документ заголовка, автора и даты необходимо внести во вступление три строки (только не в основное тело документа):  
  

```
\title{First document}
```

  
Заголовок.  
  

```
\author{Hubert Farnsworth}
```

  
Здесь размещается имя автора. При желании можно также добавить в фигурные скобки следующую команду:  
  

```
\thanks{funded by the Overleaf team}
```

  
Она может идти после имени автора, внутри скобок команды `author`. Эта команда добавляет верхний индекс и сноску с текстом из скобок. Очень полезный элемент, если вам нужно поблагодарить в своей статье какую-либо организацию.  
  

```
\date{February 2014}
```

  
Дату можно ввести вручную или использовать команду `\today`, чтобы она обновлялась автоматически при компиляции документа.  
  
После добавления перечисленных строк преамбула должна выглядеть так:  
  

```
\documentclass[12pt, letterpaper, twoside]{article}
\usepackage[utf8]{inputenc}

\title{First document}
\author{Hubert Farnsworth \thanks{funded by the Overleaf team}}
\date{February 2017}
```

  
Теперь, когда вы присвоили документу заголовок, автора и дату, можно вывести в нем эту информацию с помощью команды `\maketitle`. Ее нужно включить в ту часть тела документа, где вы хотите видеть заголовок.  
  

```
\begin{document}

\maketitle

We have now added a title, author and date to our first \LaTeX{} document!

\end{document}
```

  

![](https://habrastorage.org/r/w1560/webt/j_/2h/_f/j_2h_ffdwuc788dv5y1aazssuki.png)

  
[Открыть пример в Overleaf](https://www.sharelatex.com/project/new/template?zipUrl=/project/582dbeacf220531c2d4bdaaa/download/zip&templateName=Learn%20LaTeX%20in%2020%20minutes:%20Part%202&compiler=pdflatex)  
  

## Добавление комментариев

  
Как и в случае с любым кодом, зачастую будет нелишним добавлять комментарии. Комментарии – это включаемые в документ текстовые элементы, которые в итоге не отображаются и никак не него не влияют. Они помогают организовывать работу, делать пометки или закомментировать (отключать) строки/разделы при отладке. Чтобы создать комментарий в LaTeX, просто наберите символ `%` в начале строки, как показано ниже:  
  

```
\begin{document}

\maketitle

We have now added a title, author and date to our first \LaTeX{} document!

% This line here is a comment. It will not be printed in the document.

\end{document}
```

  

![](https://habrastorage.org/r/w1560/webt/j_/2h/_f/j_2h_ffdwuc788dv5y1aazssuki.png)

  
[Открыть пример в Overleaf](https://www.sharelatex.com/project/new/template?zipUrl=/project/58a308db13712fef4e9deff7/download/zip&templateName=Learn%20LaTeX%20in%2020%20minutes:%20Part%203&compiler=pdflatex)  
  

## Жирный, курсив и подчеркивание

  
Теперь рассмотрим некоторые простые команды форматирования текста.  

- **Жирный** текст в LaTeX пишется внутри команды `\textbf{...}`;
- _Курсив_ пишется с помощью команды `\textit{...}`;
- Подчеркнутый текст оформляется с помощью команды `\underline{...}`.

  
Вот пример этих трех видов форматирования:  
  

```
Some of the \textbf{greatest}
discoveries in \underline{science} 
were made by \textbf{\textit{accident}}.
```

  

![](https://habrastorage.org/r/w1560/webt/fy/pw/jf/fypwjflkpyfvxcxvz0xrynwq-f0.png)

  
А вот еще одна очень простая команда: `\emph{...}`. Выполняемые ей для аргумента действия определяются контекстом – внутри обычного текста его выделенная часть переводится в курсив, а при использовании команды в курсивном тексте происходит обратное.  
  
Пример:  
  

```
Some of the greatest \emph{discoveries} 
in science 
were made by accident.

\textit{Some of the greatest \emph{discoveries} 
in science 
were made by accident.}

\textbf{Some of the greatest \emph{discoveries} 
in science 
were made by accident.}
```

  

![](https://habrastorage.org/r/w1560/webt/pz/ym/-m/pzym-migrg7azaz2xkb7czn3irm.png)

  
Более того, некоторые пакеты, например _[Beamer](https://www.overleaf.com/learn/latex/Beamer)_, изменяют поведение команды `\emph`.  
  
[Открыть пример в Overleaf](https://www.sharelatex.com/project/new/template?zipUrl=/project/58a30a6813712fef4e9df06b/download/zip&templateName=Learn%20LaTeX%20in%2020%20minutes:%20Part%204&compiler=pdflatex)  
  

## Добавление изображений

  
В Overleaf для добавления изображений их сначала нужно будет [загрузить](https://www.overleaf.com/learn/latex/Including_images_in_ShareLaTeX).  
  
Пример:  
  

```
\documentclass{article}
\usepackage{graphicx}
\graphicspath{ {images/} }

\begin{document}
The universe is immense and it seems to be homogeneous, 
in a large scale, everywhere we look at.

\includegraphics{universe}

There's a picture of a galaxy above
\end{document}
```

  

![](https://habrastorage.org/r/w1560/webt/zu/_t/2w/zu_t2wgsgbvgrririv3okmebsd0.png)

  
[Открыть пример в Overleaf](https://www.sharelatex.com/project/new/template?zipUrl=/project/58a30b7413712fef4e9df0a8/download/zip&templateName=Learn%20LaTeX%20in%2020%20minutes:%20Part%205&compiler=pdflatex)  
  
LaTeX не способен обрабатывать изображения самостоятельно, поэтому приходится использовать сторонний пакет. С помощью пакетов можно измерять предустановленный вид документа LaTeX и совершать другие действия. В данном случае нам нужно добавить в документ изображение, для чего потребуется библиотека `graphicx`, которая привнесет новые команды: `\includegraphics{...}` и `\graphicspath{...}`. Для использования graphicx включите во вступление следующую строку: `\usepackage{graphicx}`.  
  
Команда `\graphicspath{ {images/} }` сообщает LaTeX, что изображения находятся в каталоге `images` в текущей директории.  
  
Команда `\includegraphics{universe}`, в свою очередь, уже конкретно добавляет изображение в документ. Здесь `universe` представляет имя файла, содержащего изображение, без его расширения, поэтому `universe.png` стал просто `universe`. Имя файла изображения не должно содержать пробелов и многоточий.  
  
**Примечание:** расширение файла включить можно, но лучше его опустить. В этом случае LaTeX будет искать все поддерживаемые форматы. Также при загрузке файлов обычно рекомендуется указывать расширение в нижнем регистре.  
  

## Подписи, метки и ссылки

  
С помощью окружения `figure` изображения можно подписывать, размечать, а также делать на них ссылки:  
  

```
\begin{figure}[h]
    \centering
    \includegraphics[width=0.25\textwidth]{mesh}
    \caption{a nice plot}
    \label{fig:mesh1}
\end{figure}

As you can see in the figure \ref{fig:mesh1}, the 
function grows near 0. Also, in the page \pageref{fig:mesh1} 
is the same example.
```

  

![](https://habrastorage.org/r/w1560/webt/bt/h0/yt/bth0ytwqslb1uuv5ebbr3r2uxpk.png)

  
[Открыть пример в Overleaf](https://www.sharelatex.com/project/new/template?zipUrl=/project/58a30c5613712fef4e9df0e8/download/zip&templateName=Learn%20LaTeX%20in%2020%20minutes:%20Part%206&compiler=pdflatex)  
  
В примере выше показаны три важные команды:  
  

- `\caption{a nice plot}`: подписывает изображение. При создании списка изображений данная подпись будет в них использована. Поместить ее можно как под, так и над рисунком.
- `\label{fig:mesh1}`: если вам нужно сослаться на изображение внутри документа, установите метку с помощью этой команды. Метка пронумерует изображение и при использовании вместе со следующей командой позволит на него сослаться.
- `\ref{fig:mesh1}`: этот код будет замещен числом, соответствующим изображению, на которое делается ссылка.

  
При добавлении изображений в документ нужно всегда размещать их внутри окружения `figure` или ему подобного, чтобы LaTeX вставлял картинку согласованно с остальной частью текста.  
  
**Примечание:** если вы используете подписи и ссылки на собственном компьютере, то вам потребуется скомпилировать документ дважды, чтобы они сработали. Overleaf делает это автоматически.  
  

## Создание списков

  
Списки в LaTeX создаются очень просто. Делается это с помощью различных окружений списков. Окружения – это разделы, которые требуется представить отличным от остальной части документа образом. Начинаются они с `\begin{...}`, а завершаются на `\end{...}`.  
  
Существует два основных типа списков: упорядоченные и неупорядоченные. Каждый из них реализуется в собственном окружении.  
  

### Неупорядоченные списки

  
Неупорядоченные списки создаются пространством itemize. Каждая запись должна предваряться управляющей последовательностью `\item`, как показано ниже:  
  

```
\begin{itemize}
  \item The individual entries are indicated with a black dot, a so-called bullet.
  \item The text in the entries may be of any length.
\end{itemize}
```

  
По умолчанию отдельные записи обозначаются черной точкой, или буллетом. Текст в записях может иметь неограниченную длину.  
  

![](https://habrastorage.org/r/w1560/webt/ni/yn/e4/niyne4h42kfnvfxafckjfjiycos.png)

  
[Открыть пример в Overleaf](https://www.sharelatex.com/project/new/template?zipUrl=/project/52fe74766a6237452e000088/download/zip&templateName=Lists%20Examples&compiler=pdflatex)  
  

### Упорядоченные списки

  
Для упорядоченных списков используется тот же синтаксис, но в другом окружении. В данном случае этим окружением выступает `enumerate`:  
  

```
\begin{enumerate}
  \item This is the first entry in our list
  \item The list numbers increase with each entry we add
\end{enumerate}
```

  

![](https://habrastorage.org/r/w1560/webt/pn/0a/zi/pn0azi95wnzeippsytw8p5831d0.png)

  
Аналогично неупорядоченным спискам, каждая запись должна предваряться управляющей последовательностью `\item`, которая будет автоматически генерировать число, отмечая им элемент. Метки перечисления состоят из последовательных чисел, начинающихся с единицы.  
  
[Открыть пример в Overleaf](https://www.sharelatex.com/project/new/template?zipUrl=/project/52fe74766a6237452e000088/download/zip&templateName=Lists%20Examples&compiler=pdflatex)  
  

## Добавление математических выражений

  
Одно из главных удобств LaTeX состоит в простоте использования математических выражений. Этот инструмент предоставляет два режима их написания: режим `inline` (встраивание) и режим `display` (отображение). Первый используется для написания формул, являющихся частью текста. Второй позволяет создавать выражения, не входящие в состав текста или абзаца, а размещаемые на отдельных строках. Вот пример режима встраивания:  
  

```
In physics, the mass-energy equivalence is stated 
by the equation $E=mc^2$, discovered in 1905 by Albert Einstein.
```

  

![](https://habrastorage.org/r/w1560/webt/cm/ur/yx/cmuryxp2_tv5iwr1xiv0qt6gvkc.png)

  
Для размещения уравнений в режиме встраивания используйте один из следующих разграничителей: `\( ... \)`, `$ ... $` или `\begin{math} ... \end{math}`. Работают они равнозначно, поэтому выбор определяется лишь собственным предпочтением.  
  
Режим отображения предлагает два варианта: без нумерации и с нумерацией.  
  

```
The mass-energy equivalence is described by the famous equation
\[ E=mc^2 \]
discovered in 1905 by Albert Einstein. 
In natural units ($c = 1$), the formula expresses the identity
\begin{equation}
E=m
\end{equation}
```

  

![](https://habrastorage.org/r/w1560/webt/dx/jx/yn/dxjxynax4ay-bw2awo5hditpxya.png)

  
Для вывода уравнений в режиме отображения используйте один из следующих разграничителей: `\[ ... \]`, `\begin{displaymath} ... \end{displaymath}` или `\begin{equation} ... \end{equation}`. Применять `$$ ... $$` [нежелательно](https://texfaq.org/FAQ-dolldoll), так как он может внести несогласованные интервалы, а также коряво работать с некотороми математическими пакетами.  
  
**Важно:** окружение `equation*` предоставляется в виде стороннего пакета. Подробнее об этом рекомендую почитать [статью по amsmath](https://www.overleaf.com/learn/latex/Aligning_equations).  
  
[Открыть пример в Overleaf](https://www.sharelatex.com/project/new/template?zipUrl=/project/52ec4e44b43917a25a000e96/download/zip&templateName=Math%20Expressions&compiler=pdflatex)  
  
Для использования многих команд при работе с математикой необходим пакет _amsmath_, поэтому не забудьте его добавить. Ниже показан пример некоторых его базовых команд:  
  

```
Subscripts in math mode are written as $a_b$ and superscripts are written as $a^b$. These can be combined an nested to write expressions such as

\[ T^{i_1 i_2 \dots i_p}_{j_1 j_2 \dots j_q} = T(x^{i_1},\dots,x^{i_p},e_{j_1},\dots,e_{j_q}) \]
 
We write integrals using $\int$ and fractions using $\frac{a}{b}$. Limits are placed on integrals using superscripts and subscripts:

\[ \int_0^1 \frac{dx}{e^x} =  \frac{e-1}{e} \]

Lower case Greek letters are written as $\omega$ $\delta$ etc. while upper case Greek letters are written as $\Omega$ $\Delta$.

Mathematical operators are prefixed with a backslash as $\sin(\beta)$, $\cos(\alpha)$, $\log(x)$ etc.
```

  

![](https://habrastorage.org/r/w1560/webt/5k/ad/o3/5kado31qaz4hf5uattlpgxxgp2c.png)

  
[Открыть пример в Overleaf](https://www.sharelatex.com/project/new/template?zipUrl=/project/58a30cfd13712fef4e9df123/download/zip&templateName=Learn%20LaTeX%20in%2020%20minutes:%20Part%207&compiler=pdflatex)  
  
Возможности использования математики в LaTeX безграничны, и перечислить их все здесь просто нереально. Так что рекомендую дополнительно почитать соответствующие материалы по теме:  
  

- [Mathematical expressions](https://www.overleaf.com/learn/latex/Mathematical_expressions) (Математические выражения)
- [Subscripts and superscripts](https://www.overleaf.com/learn/latex/Subscripts_and_superscripts) (Сноски и индексы)
- [Brackets and Parentheses](https://www.overleaf.com/learn/latex/Brackets_and_Parentheses) (Скобки и кавычки)
- [Fractions and Binomials](https://www.overleaf.com/learn/latex/Fractions_and_Binomials) (Дроби и многочлены)
- [Aligning Equations](https://www.overleaf.com/learn/latex/Aligning_equations_with_amsmath) (Выравнивание уравнений)
- [Operators](https://www.overleaf.com/learn/latex/Operators) (Операторы)
- [Spacing in math mode](https://www.overleaf.com/learn/latex/Spacing_in_math_mode) (Интервалы в математическом режиме)
- [Integrals, sums and limits](https://www.overleaf.com/learn/latex/Integrals%2C_sums_and_limits) (Интегралы, суммы и пределы)
- [Display style in math mode](https://www.overleaf.com/learn/latex/Display_style_in_math_mode) (Стиль отображения в математическом режиме)
- [List of Greek letters and math symbols](https://www.overleaf.com/learn/latex/List_of_Greek_letters_and_math_symbols) (Список греческих букв и математических символов)
- [Mathematical fonts](https://www.overleaf.com/learn/latex/Mathematical_fonts) (Математические шрифты)

  

## Базовое форматирование

  
Теперь разберем написание аннотаций, а также форматирование документов LaTeX в разных главах, разделах и абзацах.  
  

### Аннотации

  
В научных трудах принято включать краткий обзор основной темы работы. В LaTeX для этого есть специальное окружение `abstract`. Это окружение помещает текст в специальном формате в начало документа.  
  

```
\begin{document}

\begin{abstract}
This is a simple paragraph at the beginning of the 
document. A brief introduction about the main subject.
\end{abstract}
\end{document}
```

  

![](https://habrastorage.org/r/w1560/webt/wj/re/ia/wjreiag6wrero_q23mu6bokcvnm.png)

  
[Открыть пример в Overleaf](https://www.sharelatex.com/project/new/template?zipUrl=/project/58a30dd713712fef4e9df14e/download/zip&templateName=Learn%20LaTeX%20in%2020%20minutes:%20Part%208&compiler=pdflatex)  
  

### Абзацы и перевод строки

  

```
\begin{document}

\begin{abstract}
This is a simple paragraph at the beginning of the 
document. A brief introduction about the main subject.
\end{abstract}
 
Now that we have written our abstract, we can begin writing our first paragraph.
 
This line will start a second Paragraph.
\end{document}
```

  

![](https://habrastorage.org/r/w1560/webt/iv/yj/ip/ivyjiphd6z_oimfiv47amewx24s.png)

  
[Открыть пример в Overleaf](https://www.sharelatex.com/project/new/template?zipUrl=/project/58a30dd713712fef4e9df14e/download/zip&templateName=Learn%20LaTeX%20in%2020%20minutes:%20Part%208&compiler=pdflatex)  
  
Когда при написании документа вам требуется начать новый абзац, нужно дважды нажать «Ввод», вставив таким образом двойную пустую строку. Имейте ввиду, что отступ абзацев LaTeX делает автоматически.  
  
Чтобы создать новую строку без создания очередного абзаца нужно вставить точку разрыва строки, для чего используется `\\` (двойной обратный слэш, как в примере) или команда \newline.  
При этом не следует использовать несколько `\\` или `\newline` для «имитации» абзацев с увеличенными интервалами между ними, так как это приведет к конфликту с внутренними алгоритмами LaTeX. Для подобного эффекта рекомендуется использовать двойные пустые строки, после чего добавлять во вступление `\usepackage{parskip}`.  
  
Дополнительную информацию по теме можно найти в статье [Paragraphs and new lines](https://www.overleaf.com/learn/latex/Paragraphs_and_new_lines).  
  

### Главы и разделы

  
Команды для организации документа варьируются в зависимости от его типа. Простейшей формой организации выступает деление на разделы, доступное во всех форматах.  
  

```
\chapter{First Chapter}

\section{Introduction}

This is the first section.

Lorem  ipsum  dolor  sit  amet,  consectetuer  adipiscing  
elit.   Etiam  lobortisfacilisis sem.  Nullam nec mi et 
neque pharetra sollicitudin.  Praesent imperdietmi nec ante. 
Donec ullamcorper, felis non sodales...

\section{Second Section}

Lorem ipsum dolor sit amet, consectetuer adipiscing elit.  
Etiam lobortis facilisissem.  Nullam nec mi et neque pharetra 
sollicitudin.  Praesent imperdiet mi necante...

\subsection{First Subsection}
Praesent imperdietmi nec ante. Donec ullamcorper, felis non sodales...

\section*{Unnumbered Section}
Lorem ipsum dolor sit amet, consectetuer adipiscing elit.  
Etiam lobortis facilisissem
```

  

![](https://habrastorage.org/r/w1560/webt/t1/fg/zo/t1fgzombcpttvd-kjzmga90acru.png)

  
[Открыть пример в Overleaf](https://www.sharelatex.com/project/new/template?zipUrl=/project/58a30e7b13712fef4e9df182/download/zip&templateName=Learn%20LaTeX%20in%2020%20minutes:%20Part%209&compiler=pdflatex)  
  
Команда `\section{}` отмечает начало нового раздела, а внутри скобок содержит его имя. Нумерация разделов происходит автоматически и может быть отключена добавлением символа `*` в команду создания раздела: `\section*{}`. Можно также использовать подразделы, `\subsection{}` и даже подподразделы, `\subsubsection{}`. Ниже перечислены основные уровни вложенности:  
  

![](https://habrastorage.org/r/w1560/webt/tv/ju/iu/tvjuiurwc9yhpiqo81gpnay6mkc.png)

  
Обратите внимание, что `\part` и `\chapter` доступны только в классах `report` и `book`.  
  
Более подробный разбор структуры документа описан в статье [Sections and Chapters](https://www.overleaf.com/learn/latex/Sections_and_chapters).  
  

## Создание таблиц

  

### Простые таблицы

  
Вот простейший пример создания таблицы:  
  

```
\begin{center}
\begin{tabular}{ c c c }
 cell1 & cell2 & cell3 \\ 
 cell4 & cell5 & cell6 \\  
 cell7 & cell8 & cell9    
\end{tabular}
\end{center}
```

  

![](https://habrastorage.org/r/w1560/webt/mf/qh/nz/mfqhnz5qasv6jpuaedfelaic9zo.png)

  
По умолчанию для создания таблиц в LaTeX используется окружение `tabular`. В этом окружении нужно указывать параметр, в нашем случае `{c c c}`. В таком виде он сообщит LaTeX, что в таблице будет три столбца, и текст внутри этих столбцов нужно разместить по центру. Можно также использовать `r` для выравнивания текста по правому краю и `l` для выравнивания по левому.  
  
Для указания разрывов в записях таблицы используется символ `&`. Количество символов выравнивания в каждой строке всегда должно быть на один меньше, чем количество столбцов. Чтобы перейти к очередной строке таблицы используется команда создания новой строки, `\\`. Всю таблицу мы заключаем в окружение `center`, чтобы она размещалась по центру страницы.  
  
[Открыть пример в Overleaf](https://www.sharelatex.com/project/new/template?zipUrl=/project/58a3101d13712fef4e9df258/download/zip&templateName=Learn%20LaTeX%20in%2020%20minutes:%20Part%2010&compiler=pdflatex)  
  

### Добавление границ

  
Окружение `tabular` достаточно гибкое и позволяет размещать разделяющие строки между каждым столбцом.  
  

```
\begin{center}
\begin{tabular}{ |c|c|c| } 
 \hline
 cell1 & cell2 & cell3 \\ 
 cell4 & cell5 & cell6 \\ 
 cell7 & cell8 & cell9 \\ 
 \hline
\end{tabular}
\end{center}
```

  

![](https://habrastorage.org/r/w1560/webt/ag/xf/oe/agxfoeiunqunj4jxk8vlwx4e6io.png)

  
Границы можно добавлять при помощи команды рисования горизонтальной линии `\hline` и параметра рисования вертикальной линии `|`.  
  

- `{ |c|c|c| }`: эта команда объявляет, что в таблице будут использованы три столбца, разделенные вертикальными линиями. На необходимость вертикального разделения указывает символ |.
- `\hline`: эта команда вставит горизонтальную линию. В примере выше горизонтальными линиями мы ограничили верх и низ таблицы, но при желании ими можно разделить ее всю.

  
Вот еще один пример:  
  

```
\begin{center}
 \begin{tabular}{||c c c c||} 
 \hline
 Col1 & Col2 & Col2 & Col3 \\ [0.5ex] 
 \hline\hline
 1 & 6 & 87837 & 787 \\ 
 \hline
 2 & 7 & 78 & 5415 \\
 \hline
 3 & 545 & 778 & 7507 \\
 \hline
 4 & 545 & 18744 & 7560 \\
 \hline
 5 & 88 & 788 & 6344 \\ [1ex] 
 \hline
\end{tabular}
\end{center}
```

  

![](https://habrastorage.org/r/w1560/webt/rr/sq/yc/rrsqycbt72nvuahx-vadntjdjtm.png)

  
Порой создание таблиц в LaTeX вызывает затруднения, поэтому вам может потребоваться обратиться к онлайн-инструменту [TablesGenerator.com](https://www.tablesgenerator.com/), чтобы экспортировать код LaTeX для окружения `tabular`. Копировать и вставлять данные из приложений электронных таблиц можно через опцию **File** → **Paste table data**.  
  
[Открыть пример в Overleaf](https://www.sharelatex.com/project/new/template?zipUrl=/project/58a3101d13712fef4e9df258/download/zip&templateName=Learn%20LaTeX%20in%2020%20minutes:%20Part%2010&compiler=pdflatex)  
  

### Подписи, метки и ссылки

  
Как и изображения, таблицы можно пописывать и делать на них ссылки. Единственное отличие – это использование вместо `figure` окружения `table`.  
  

```
Table \ref{table:data} is an example of referenced \LaTeX{} elements.

\begin{table}[h!]
\centering
\begin{tabular}{||c c c c||} 
 \hline
 Col1 & Col2 & Col2 & Col3 \\ [0.5ex] 
 \hline\hline
 1 & 6 & 87837 & 787 \\ 
 2 & 7 & 78 & 5415 \\
 3 & 545 & 778 & 7507 \\
 4 & 545 & 18744 & 7560 \\
 5 & 88 & 788 & 6344 \\ [1ex] 
 \hline
\end{tabular}
\caption{Table to test captions and labels}
\label{table:data}
\end{table}
```

  

![](https://habrastorage.org/r/w1560/webt/3p/7a/ws/3p7awshe5jcd1te_ts8qrs69mp4.png)

  
[Открыть пример в Overleaf](https://www.sharelatex.com/project/new/template?zipUrl=/project/58a3101d13712fef4e9df258/download/zip&templateName=Learn%20LaTeX%20in%2020%20minutes:%20Part%2010&compiler=pdflatex)  
  
**Примечание:** если вы используете подписи и ссылки на своем компьютере, то для работоспособности ссылок нужно будет скомпилировать документ дважды. Overleaf делает это автоматически.  
  

## Добавление содержания

  
Процесс создания содержания очень прост и реализуется командой `\tableofcontents`:  
  

```
\documentclass{article}
\usepackage[utf8]{inputenc}
 
\title{Sections and Chapters}
\author{Gubert Farnsworth}
\date{ }
  
\begin{document}
  
\maketitle
  
\tableofcontents

\section{Introduction}
   
This is the first section.
      
Lorem  ipsum  dolor  sit  amet,  consectetuer  adipiscing  
elit.   Etiam  lobortisfacilisis sem.  Nullam nec mi et 
neque pharetra sollicitudin.  Praesent imperdietmi nec ante. 
Donec ullamcorper, felis non sodales...
       
\section*{Unnumbered Section}
\addcontentsline{toc}{section}{Unnumbered Section}

Lorem ipsum dolor sit amet, consectetuer adipiscing elit.  
Etiam lobortis facilisissem.  Nullam nec mi et neque pharetra 
sollicitudin.  Praesent imperdiet mi necante...

\section{Second Section}
       
Lorem ipsum dolor sit amet, consectetuer adipiscing elit.  
Etiam lobortis facilisissem.  Nullam nec mi et neque pharetra 
sollicitudin.  Praesent imperdiet mi necante...
         
\end{document}
```

  

![](https://habrastorage.org/r/w1560/webt/1z/ky/y7/1zkyy7myqwtxyix--jqomc44_li.png)

  
Разделы, подразделы и главы включаются в содержание автоматически. Чтобы добавить записи вручную, например для указания непронумерованного раздела, используйте команду `\addcontentsline`, как показано в примере.  
  
