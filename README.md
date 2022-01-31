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

Настройка ssh ключей для каждого аккаунта в гитхабе
Multiple SSH Keys settings for different github account
=================================================================


create different public key
---------------------------------

create different ssh key according the article [Mac Set-Up Git](http://help.github.com/mac-set-up-git/)

	$ ssh-keygen -t rsa -C "your_email@youremail.com"

Please refer to [github ssh issues](http://help.github.com/ssh-issues/) for common problems.

for example, 2 keys created at:

	~/.ssh/id_rsa_activehacker
	~/.ssh/id_rsa_jexchan

then, add these two keys as following

	$ ssh-add ~/.ssh/id_rsa_activehacker
	$ ssh-add ~/.ssh/id_rsa_jexchan

you can delete all cached keys before

	$ ssh-add -D

finally, you can check your saved keys

	$ ssh-add -l


Modify the ssh config
---------------------------------

	$ cd ~/.ssh/
	$ touch config
	$ subl -a config

Then added

	#activehacker account
	Host github.com-activehacker
		HostName github.com
		User git
		IdentityFile ~/.ssh/id_rsa_activehacker

	#jexchan account
	Host github.com-jexchan
		HostName github.com
		User git
		IdentityFile ~/.ssh/id_rsa_jexchan


Clone you repo and modify your Git config
---------------------------------------------

clone your repo
	git clone git@github.com:activehacker/gfs.git gfs_jexchan

cd gfs_jexchan and modify git config

	$ git config user.name "jexchan"
	$ git config user.email "jexchan@gmail.com" 
 
	$ git config user.name "activehacker"
	$ git config user.email "jexlab@gmail.com" 

or you can have global git config
	$ git config --global user.name "jexchan"
	$ git config --global user.email "jexchan@gmail.com"


then use normal flow to push your code

	$ git add .
	$ git commit -m "your comments"
	$ git push


Another related article in Chinese

1. http://4simple.github.com/docs/multipleSSHkeys/

