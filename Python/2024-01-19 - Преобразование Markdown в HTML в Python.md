Самый простой способ преобразования — использовать строку для ввода и строку для вывода.

```
import markdown

# Simple conversion in memory
md_text = '# Hello\n\n**Text**'
html = markdown.markdown(md_text)
print(html)
```
Чтобы вместо этого использовать файлы для ввода и вывода:
```
import markdown

markdown.markdownFromFile(
    input='input.md',
    output='output.html',
    encoding='utf8',
)
```
#### Преобразование Markdown в HTML с помощью инструмента командной строки

Инструмент [Python-Markdown CLI](https://python-markdown.github.io/cli/) удобен, когда вы просто хотите преобразовать документ, не встраивая код в более крупное приложение.

Самый простой способ вызвать его путем запуска — это модуль с `python -m`. Например:

```
# Convert from a file
python -m markdown input.md

# Convert using STDIN/STDOUT
cat input.md | python -m markdown > output.html

# Load extensions with -x (e.g. Table of contents)
python -m markdown -x toc input.md
```
#### Создать оглавление (TOC)

Чтобы сгенерировать оглавление, нам нужно использовать [расширение toc](https://python-markdown.github.io/extensions/toc/) . Доступен ряд других расширений с пакетом, который вы можете проверить по адресу [https://python-markdown.github.io/extensions/](https://python-markdown.github.io/extensions/) .

Вы конвертируете так же, как и раньше, за исключением того, что на этот раз вы передаете дополнительный параметр, чтобы включить расширение
```
import markdown

md_text = '[TOC]\n# Title\n**text**'
html = markdown.markdown(md_text, extensions=['toc'])
print(html)
```

Чтобы настроить параметры, вам необходимо включить `markdown.extensions.toc.TocExtension`сорт и передайте экземпляр этого объекта в параметр расширений. См. следующий пример. Подробнее читайте на [https://python-markdown.github.io/extensions/toc/#usage.](https://python-markdown.github.io/extensions/toc/#usage)

В свой Markdown добавьте `[TOC]`в Markdown, куда должен идти TOC.

```
import markdown
from markdown.extensions.toc import TocExtension

md_text = '[TOC]\n# Title\n**text**'
# baselevel=2 sets headings to start at `h2`
html = markdown.markdown(md_text, extensions=[TocExtension(baselevel=2, title='Contents')])
print(html)
```