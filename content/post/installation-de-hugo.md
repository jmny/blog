+++
date = "2017-02-04T15:39:13+01:00"
title = "Installation de hugo"
draft = false

+++

# Creation d'un blog avec Hugo sur github pages

Installation, configuration et deployement.

## Qu'est ce que Hugo

C'est un générateur de site statique. dans la meme famille on retrouve [Jekill](https://jekyllrb.com/). 

Les cas d'utilisations sont :
- Une home de projet open source
- Un blog
- Une homepage de site public
- Un portefolio
- et tout ce que peut gérer un site html statique


## Machine de travail

Je suis sous ubuntu 16.04, mais cet exemple d'installation fonctionne sur Linux et Mac OS à minima.

## Installer Hugo


```
sudo apt install snapd
snap install hugo
hugo version
```
(Plus de details [ici](https://gohugo.io/overview/installing).)


## Creer son blog

```
hugo new site monblog

# pour voir ce qui a été généré ( soyons curieux :) )
cd monblog
tree -a
```

(La documention est [là](https://gohugo.io/overview/quickstart/).)


## Ecrire son premier article


``` 
hugo new post/protocols-war.md
echo "
# Protocols war

 \![ ](https://imgs.xkcd.com/comics/standards.png)

" >> content/post/protocols-war.md
```

Je vous invite à modifier le post, avec peut être un contenu plus personnel. Via le cartouche du header, vous pouvez également renseigner des information comme l'etat brouillon, le titre du post, ou les tags associés. Notez que *dans le header, le titre est vide, il faut le remplir* sinon le titre sera vide.

```
vim content/post/protocols-war.md
```
(la documentation est [par ici](https://gohugo.io/overview/quickstart/#step-3-add-content).)


## Choisir un theme et l'installer

Avec hugo, pas de theme par defaut. Je vous laisse vous perdre dans [la gallerie de thème disponible](http://themes.gohugo.io/) et choisir le votre (ou le [faire](https://gohugo.io/themes/creation/). Mon choix s'est arrêté sur ghostwriter. Je reprend donc ce pour l'exemple, à remplacer par votre préférez au besoin donc.


```
git clone https://github.com/jbub/ghostwriter themes/ghostwriter
```

Faisons nous plaisir et regardons le resultat. Option -D pour générer aussi les brouillons, par default __hugo serve__ surveille les modifications et regénérer automatiquement, plus d'info avec : hugo help serve.

```
hugo serve -D 
```

## Publier le blog sur github page

Bon, on arrive dans la partie qui merite un peu de concentration et d'explication.  



https://help.github.com/articles/user-organization-and-project-pages/






 1072  04/02/17 17:37:01 git remote rm origin
 1073  04/02/17 17:37:21 git remote add origin git@github.com:jmny/blog.git
 1074  04/02/17 17:37:34 ls
 1075  04/02/17 17:37:50 echo "/public/" >> .gitignore
 1076  04/02/17 17:38:01 echo "/themes/" >> .gitignore




 1042  04/02/17 16:35:10 rm -r exampleSite
 1043  04/02/17 16:35:25 cp content/post/installation-de-hugo.md  .
 1044  04/02/17 16:35:41 cp -r themes/cocoa/exampleSite/* .
 1045  04/02/17 16:35:47 tree -I "themes*|public*"
 1046  04/02/17 16:36:30 rm -r content/page
 1047  04/02/17 16:36:38 rm -r content/post
 1048  04/02/17 16:38:41 tree -I "themes*|public*"
 1049  04/02/17 17:00:27 ls
 1050  04/02/17 17:00:33 cd ../jmny-blog/
 1051  04/02/17 17:01:02 vim config.toml 
 1052  04/02/17 17:03:19 git clone git clone https://github.com/jbub/ghostwriter themes/
 1053  04/02/17 17:03:33 git clone git clone https://github.com/jbub/ghostwriter themes/ghostwriter
 1054  04/02/17 17:03:39 cd ../jmny-blog/
 1055  04/02/17 17:03:45 git clone https://github.com/jbub/ghostwriter themes/ghostwriter
 1056  04/02/17 17:04:18 cp themes/ghostwriter/exampleSite/config.toml .
 1057  04/02/17 17:05:54 vim config.toml 
 1058  04/02/17 17:49:45 more themes/ghostwriter/exampleSite/content/post/creating-a-new-theme.md 
 1059  04/02/17 17:50:43 vim config.toml 
 1060  04/02/17 17:54:55 vim content/post/installation-de-hugo.md 

 1007  04/02/17 16:58:41 rm -rf jmny-blog
 1008  04/02/17 16:58:49 hugo new site
 1009  04/02/17 16:58:56 hugo new site jmny-blog
 1010  04/02/17 16:59:35 cp installation-de-hugo.md jmny-blog/content/
 1011  04/02/17 16:59:37 ls
 1012  04/02/17 16:59:40 cd jmny-blog/
 1013  04/02/17 16:59:41 ls
 1014  04/02/17 16:59:44 tree 
 1015  04/02/17 16:59:58 hugo serve
 1016  04/02/17 17:43:34 ls
 1017  04/02/17 17:43:57 hugo
 1018  04/02/17 17:44:00 ls
 1019  04/02/17 17:44:06 cd public/
 1020  04/02/17 17:44:17 cd ..
 1021  04/02/17 17:44:22 more .gitignore 
 1022  04/02/17 17:44:41 cd public/
 1023  04/02/17 17:44:51 git init
 1024  04/02/17 17:45:01 git add *
 1025  04/02/17 17:45:07 git ci -am 'init'
 1026  04/02/17 17:45:24 git remote add origin git@github.com:jmny/jmny.github.io.git
 1027  04/02/17 17:45:30 git push origin master
 1028  04/02/17 17:47:02 hugo
 1029  04/02/17 17:47:30 git st
 1030  04/02/17 17:47:35 git push origin master
 1031  04/02/17 17:47:50 git ci -am 'baseUrl :) '
 1032  04/02/17 17:47:59 git push origin master
 1033  04/02/17 17:52:52 gt
 1034  04/02/17 17:53:02 git ci -am 'remove discus'
 1035  04/02/17 17:53:06 git push origin master
 1036  04/02/17 17:53:46 history



