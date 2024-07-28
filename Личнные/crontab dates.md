\#minute (0-59),
#|	hour (0-23),
#|	|	day of the month (1-31),
#|	|	|	month of the year (1-12),
#|	|	|	|	day of the week (0-6 with 0=Sunday).
#|	|	|	|	|	commands

00 06 16 * * echo 'date' > /home/jenit/'Рабочий стол'/date.txt  

00 08 05 03 * echo 'Birthday Slava 05.03.1989' > /home/jenit/'Рабочий стол'/date-Slava.txt 

00 08 15 11 * echo 'Birthday Nika 15.11.1990' > /home/jenit/'Рабочий стол'/date-Nika.txt   

00 08 16 06 * echo 'Birthday Ura 16.06.1993' > /home/jenit/'Рабочий стол'/date-Ura.txt  

00 08 21 01 * echo 'Birthday Dasha 21.01.2017' > /home/jenit/'Рабочий стол'/date-Dasha.txt  


