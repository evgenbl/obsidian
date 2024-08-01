Во второй версии WSL для обеспечения виртуализации используется архитектура Hyper-V. 

 Эта архитектура будет доступна в дополнительном компоненте, который является подмножеством  

 функций  Hyper-V. 

Этот дополнительный компонент будет доступен во всех редакциях ОС. 

С правами Администратора запустить hyper-v.bat. 

Ссылка на файл: [https://disk.yandex.ru/d/jKgFVY-j0QMm5w](https://disk.yandex.ru/d/jKgFVY-j0QMm5w) 


hyper-v.bat 

Содержание файла: 

pushd "%~dp0" 

dir /b %SystemRoot%\servicing\Packages\*Hyper-V*.mum >hv.txt 

for /f %%i in ('findstr /i . hv.txt 2^>nul') do dism /online /norestart /add-package:"%SystemRoot%\servicing\Packages\%%i" 

del hv.txt 

Dism /online /enable-feature /featurename:Microsoft-Hyper-V -All /LimitAccess /ALL 

pause