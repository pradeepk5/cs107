Cette page a pour but de vous guider dans le processus d'installation d'un tel environnement de développement pour Java sous Linux.

Merci de suivre scrupuleusement les instructions ci-dessous. Vous pouvez aussi visionner la vidéo qui montre cette installation :


# Installer le JDK 11

Ce cours utilise la version OpenJDK de Java, en version 11.

Commencez par vérifier si elle n'est pas déjà installée sur votre machine:

```
java --version
```

Vous devriez obtenir quelque chose comme `openjdk `**11**`.xxx`

Si tel n'est pas le cas,  vérifiez si le OpenJDK 11 est disponible dans les dépôts de votre distribution:

```
apt update && apt-cache policy openjdk-11-jdk
```

Si vous obtenez autre chose que  `Unable to locate package`, il suffit d'utiliser la commande

```
apt install openjdk-11-jdk
```

Autrement, rendez-vous sur le site https://adoptopenjdk.net/

Puis

* Choisir les options OpenJDK11(LTS) et HotSpot

* Télécharger l'archive en cliquant sur `Latest Release` (typiquement
quelque chose comme `OpenJDK11U-jdk_x64_linux_hotspot_11.0.4_11.tar.gz`)
Cette archive peut être installée dans un répertoire de votre choix, par exemple `~/local/softs`, `local` et `softs` étant des répertoires que vous aurez préalablement créés; alternativement, vous pouvez utiliser un répertoire de plus haut niveau, typiquement `/opt/`, auquel cas vous devrez faire précéder le commandes décrites ci-dessous de `sudo`.

* Dezziper l'archive:

	```
	tar zxvf <nom de l'archive>
	```
(on suppose dans ce qui suit que cela crée un répertoire jdk-11.xxx)

* Informer votre système de l'existence de cette nouvelle alternative pour java

	```
	sudo update-alternatives --install "/usr/bin/javac" "javac" "~/local/softs/jdk-11.xxx/bin/javac" 0
    sudo update-alternatives --install "/usr/bin/java" "java" "~/local/softs/jdk-11.xxx/bin/javac" 0
	sudo update-alternatives --config java
	sudo update-alternatives --config javac
	```
(`xxx` est évidemment à remplacer par ce qui convient et vous adapterez le chemin si vous avez décider de stocker cette version de Java ailleurs que dans `~/local/softs`).

* Sélectionner la version de Java par défaut avec:

	```
	sudo update-alternatives --config java
	sudo update-alternatives --config javac
	```
(choisir la version fraîchement installée)

* Vérifiez que l'installation s'est bien déroulée
	```
	java --version
	```
	vous devriez obtenir quelque chose comme:
	```
	openjdk 11.0.4 2019-07-16
	OpenJDK Runtime Environment AdoptOpenJDK (build 11.0.4+11)
	OpenJDK 64-Bit Server VM AdoptOpenJDK (build 11.0.4+11, mixed mode)
	```

	
# Install IntelliJ IDEA
* The version of IntelliJ to use is IntelliJ 2019.2
* Go to https://www.jetbrains.com/idea/download/
* Click the Download button (download the free version of the community)
* Dezzip the archive, for example (X designates the version)
```
tar zxvf tar zxvf ideaIC-2019.X.X.tar.gz -C <"installation directory">
```
* Go to the installation directory and launch the installer (allow the creation of a desktop entry).
```
cd <"installation directory"> / idea-IC-XXXX / bin /
./idea.sh
```
* Start IntelliJ by launching the icon from
* Configure IntelliJ as shown in the document [Basic configuration](./basic_configuration.md) Configuration
