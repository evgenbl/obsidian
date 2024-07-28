pandoc+кириллица

sudo apt install texlive-xetex
sudo apt-get install texlive-lang-all
___________________________________________________________
pandoc test.md -s -o test.pdf --latex-engine=xelatex
pandoc test.md -s -o test.pdf --pdf-engine=xelatex
___________________________________________________________
%!TeX program = xelatex
---
title: Title text
geometry: margin=2cm


header-includes: |
    \newfontfamily{\cyrillicfont}{Arial}
    \newfontfamily{\cyrillicfontrm}{Arial}
    \newfontfamily{\cyrillicfonttt}{Arial}
    \newfontfamily{\cyrillicfontsf}{Arial}
---
