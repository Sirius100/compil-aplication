# compil-aplication
установка приложений из бинарников (например emacs)

1 - установить в систему пакет build-essential
2 - ./configure (Возможно команда отработает без ошибок не с первого раза, нужно будет внимательно читать вывод команды и доустановить требуемые libs)
3 - make
4 - sudo make install
Все приложение установилось!!!

autogen.sh

configure 

aclocal.m4

5 - Если таких скриптов в архиве не оказалось, то можно выполнить последовательно следующие команды: 
  aclocal
  autoheader
  automake --gnu --add-missing --copy --foreign
  autoconf -f -Wall
  
 И после ./.configure
