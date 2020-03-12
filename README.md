# comandosLinux
Ejercicios comandos Linux

   1 Listar todos los archivos del directorio bin
   
	ls /bin

   2 Listar todos los archivos del directorio tmp.
   
	ls /tmp

   3 Listar todos los archivos del directorio etc que empiecen por t en orden inverso.
   
	ls -r /etc/t* 

   4 Listar todos los archivos del directorio dev que empiecen por tty y tengan 5 caracteres.
   
	ls /dev/tty??

   5 Listar todos los archivos del directorio dev que empiecen por tty y acaben en 1,2,3 ó 4.
   
	ls /dev/tty*[1-4]

   6 Listar todos los archivos del directorio dev que empiecen por t y acaben en C1.
   
	ls /dev/t*C1

   7 Listar todos los archivos, incluidos los ocultos, del directorio raíz.
   
	ls -la /

   8 Listar todos los archivos del directorio etc que no empiecen por t.
   
	ls -d /etc/[^t]*

   9 Listar todos los archivos del directorio usr y sus subdirectorios.
   
	ls -R /usr

   10 Cambiarse al directorio tmp, crear directorio PRUEBA.
   
	cd /tmp
	mkdir PRUEBA

   11 Verificar que el directorio actual ha cambiado.
   
	pwd

   12 Mostrar el día y la hora actual.
   
	date

   13 Con un solo comando posicionarse en el directorio $HOME.
   
	cd $HOME

   14 Verificar que se está en él.
   
	pwd

   15 Listar todos los ficheros del directorio HOME mostrando su número de inodo.
   
	ls -i $HOME

   16 Borrar todos los archivos y directorios visibles de vuestro directorio PRUEBA.
   
	rm -rf /tmp/prueba/*

   17 Crear los directorios dir1, dir2 y dir3 en el directorio PRUEBA. Dentro de dir1 crear el directorio dir11. Dentro del directorio dir3 crear el directorio dir31. Dentro del directorio dir31, crear los directorios dir311 y dir312.
   
    mkdir PRUEBA/dir1
	mkdir PRUEBA/dir2
	mkdir PRUEBA/dir3
	mkdir PRUEBA/dir1/dir11
	mkdir PRUEBA/dir3/dir31
	mkdir PRUEBA/dir3/dir31/dir311
	mkdir PRUEBA/dir3/dir31/dir312

   18 Copiar el archivo /etc/motd a un archivo llamado mensaje de vuestro directorio PRUEBA.
   
	cp /etc/motd /tmp/prueba/mensaje

   19 Copiar mensaje en dir1, dir2 y dir3.
   
	cd /tmp/prueba
	cp mensaje dir1/mensaje
	cp mensaje dir2/mensaje
	cp mensaje dir3/mensaje

   20 Comprobar el ejercicio anterior mediante un solo comando.
   
	ls -R /tmp/prueba

   21 Copiar los archivos del directorio rc.d que se encuentra en /etc al directorio dir31.
   
	cp /etc/rc.d /tmp/prueba/dir3/dir31

   22 Copiar en el directorio dir311 los archivos de /bin que tengan una a como segunda letra y su nombre tenga cuatro letras.
   
	cp /bin/?a?? /tmp/PRUEBA/dir3/dir31/dir311

   23 Copiar el directorio de otro usuario y sus subdirectorios debajo de dir11 (incluido el propio directorio).
   
	sudo cp -r ../nombre /tmp/PRUEBA/dir1/dir11

   24 Mover el directorio dir31 y sus subdirectorios debajo de dir2.
   
	mv /tmp/PRUEBA/dir3/dir31 /tmp/PRUEBA/dir2

   25 Mostrar por pantalla los archivos ordinarios del directorio HOME y sus subdirectorios.
   
	ls -R $HOME

   26 Ocultar el archivo mensaje del directorio dir3.
   
	mv /tmp/PRUEBA/dir3/mensaje /tmp/PRUEBA/dir3/.mensaje

   27 Borrar los archivos y directorios de dir1, incluido el propio directorio.
   
	rm -r /tmp/PRUEBA/dir1

   28 Copiar al directorio dir312 los ficheros del directorio /dev que empiecen por t, acaben en una letra que vaya de la a a la b y tengan cinco letras en su nombre.
   
	cp /dev/t???[a*b] /tmp/prueba/dir3/dir31/dir312

   29 Borrar los archivos de dir312 que no acaben en b y tengan una q como cuarta letra.
   
	rm -r /tmp/PRUEBA/dir2/dir31/dir312/???q[^b]

   30 Mover el directorio dir312 debajo de dir3.
   
	mv /tmp/prueba/dir3/dir31/dir312 /tmp/prueba/dir3

   31 Crear un enlace simbólico al directorio dir1 dentro del directorio dir3 llamado enlacedir1.
   
	ln -s /home/ubuntu/PRUEBA/dir1 /tmp/PRUEBA/dir3/enlacedir1

   32 Posicionarse en dir3 y, empleando el enlace creado en el ejercicio anterior, crear el directorio nuevo1 dentro de dir1.
   
	cd /tmp/PRUEBA/dir3
	mkdir enlacedir1/nuevo1

   33 Utilizando el enlace creado copiar los archivos que empiecen por u del directorio /bin en directorio nuevo1.
   
	cp -r /bin/u* enlacedir1/nuevo1/

   34 Crear dos enlaces duros del fichero fich1, llamarlo enlace, en los directorios dir1 y dir2.
   
	ln fich1 dir1/enlace 
	ln fich1 dir2/enlace

   35 Borrar el archivo fich1 y copiar enlace en dir3.
   
	rm fich1 
	cp dir1/enlace dir3/

   36 Crear un enlace simbólico (llamado enlafich1) al fichero enlace de dir2 en dir1.
   
	ln -s /tmp/prueba/dir2 prueba/dir1/enlafich1

   37 Posicionarse en dir1 y, mediante el enlace creado, copiar el archivo fichl dentro de dir311.
   
	cd dir1 
	cp enlafich1 ../dir2/dir31/dir311/fich1

   38 Seguir en dir1 y, mediante el enlace creado, sacar por pantalla las líneas que tiene el archivo fich1.
   
	cat enlafich1

   39 Borrar el fichero fich1 de dir2.
   
	rm dir2/fich1

   40 Borrar todos los archivos y directorios creados durante los ejercicios.
   
	rm -r prueba

   41 Crear el directorio dir2 y dir3 en el directorio PRUEBA ¿Cuáles son los actuales permisos del directorio dir2?
   
	mkdir dir1 
	mkdir dir2 
	ls -l

   42 Utilizando la notación simbólica, eliminar todos los permisos de escritura (propietario, grupo, otros) del directorio dir2.
   
	chmod a-w dir2

   43 Utilizando la notación octal, eliminar el permiso de lectura del directorio dir2, al resto de los usuarios.
   
	chmod 551 dir2

   44 ¿Cuáles son ahora los permisos asociados a dir2?
   
	ls -l

   45 Crear bajo dir2, un directorio llamado dir2l.
   
	mkdir dir2/dir21
	permiso denegado

   46 Concederse a sí mismo permiso de escritura en el directorio dir2 e intentar de nuevo el paso anterior.
   
	chmod 751 dir2
	mkdir dir2/dir21

   47 ¿Cuáles son los valores por omisión asignados a los archivos?
   
	ls -l dir2

   48 Cambiar el directorio actual al directorio dir3. Imprimir su trayectoria completa para verificar el cambio.
   
	cd prueba/dir3
	pwd

   49 ¿Cuáles son los permisos asignados en su momento a este directorio?
   
	ls -lr

   50 Reiniciar el ordenador.
   
	reboot

   51 Crear cuatro nuevos directorios llamados dira, dirb, dirc, y dird bajo el directorio actual.
     
	mkdir dira 
	mkdir dirb 
	mkdir dirc 
	mkdir dird

   52 Comprobar los permisos de acceso de los directorios recién creados para comprobar el funcionamiento del comando umask.
   
	ls -l

   53 Crear el fichero uno . Quitarle todos los permisos de lectura. Comprobarlo. Intentar borrar dicho fichero.
   
	touch uno 
	chmod a-r
	uno ls -l 
	rm uno

   54 Quitarle todos los permisos de paso al directorio dir2 y otorgarle todos los demás.
   
	chmod = dir2 
	chmod o=rwx dir2

   55 Crear en el directorio propio:
	

   56 El directorio carpeta1 con los tres permisos para el propietario, dentro de él fich1 con lectura y escritura para todos y fich2 con lectura y escritura para el propietario y solo lectura para el resto. El directorio carpeta2 con todos los permisos para el propietario y lectura y ejecución para los del mismo grupo. Dentro file1 con lectura y escritura para el propietario y los del grupo y file2 con los mismos para el propietario y solo lectura para el grupo.
   
	mkdir carpeta1
	chmod 755 carpeta1
	touch carpeta1/fich1 
	chmod 777 carpeta1/fich1
	touch carpeta1/fich2
	chmod 755 carpeta1/fich2

	mkdir carpeta2
	chmod 750 carpeta2
	touch carpeta1/file1 
	chmod 770 carpeta1/file1
	touch carpeta1/file2
	chmod 750 carpeta1/file2

   57 Desde otro usuario probar todas las operaciones que se pueden hacer en los ficheros y directorios creados.
   
	ls -lR

   58 Visualizar la trayectoria completa del directorio actual. Crear dos directorios llamados correo y fuentes debajo del directorio actual.
   
	pwd
	mkdir correo
	mkdir fuentes

   59 Posicionarse en el directorio fuentes y crear los directorios dir1, dir2, dir3.
   
	cd fuentes 
	mkdir dir1 
	mkdir dir2

   60 Crear el directorio menus bajo correo sin moverse del directorio actual.
   
	mkdir ../correo/menus

   61 Posicionarse en el directorio HOME. Borrar los directorios que cuelgan de fuentes que acaben en un número que no sea el 1.
   
	cd $HOME
	rm -r /correo/fuentes/*[^1]

   62 Ver si existe el archivo tty2 en el directorio dev. En caso de que exista, ver su fecha de creación o actualización.
   63 Ver los permisos que tienen los archivos que empiecen por tt del directorio /dev.
   64 Visualizar la lista de los archivos ordinarios que están en el directorio /usr/bin.
