# the_spacer
Stellar Development with Symfony 4

1- composer create-project symfony/skeleton the_spacebar
2- php -S 127.0.0.1:8000 -t public 
3- Open on browser http://127.0.0.1:8000
4- Open new window with cmd and go to your directory the_spacer
5- git status
6- git add .
7. git commit 

For configuration:
git config --global user.email "Vous@exemple.com"
git config --global user.name "Votre Nom"

8-  git push --set-upstream url-github-repository master

#console
1- composer require server
2- ./bin/console server:run

#SSH 
Générer une nouvelle clé SSH

    Ouvrez le terminal
    Collez cette ligne de code en substituant l’adresse email par votre email configuré sur GitHub.

    ssh-keygen -t rsa -b 4096 -C "votre_email@exemple.com"

    Vous devriez obtenir ceci

    Generating public/private rsa key pair.

    Le terminal va vous demander où sauvegarder la clé, pressez le bouton Entrée pour choisir le chemin par défaut

    Enter a file in which to save the key (/Users/you/.ssh/id_rsa): [Press enter]

    Enfin, il faudra définir un mot de passe complexe, ce que bon vous semble à condition de ne pas mettre un toto ou autre

    Enter passphrase (empty for no passphrase): [Type a passphrase]
    Enter same passphrase again: [Type passphrase again]

 
Ajouter la clé SSH à ssh-agent

Un agent SSH ? Qu’est ce que c’est ? Vous vous souvenez de la passphrase que vous avez crée plus tôt ? Le but c’est d’éviter de la retaper systématiquement à chaque fois qu’on va la solliciter. Le rôle de l’agent est de stocker ces clés, ensuite nous n’y toucherons plus.

    Pour assigner une nouvelle clé à l’agent ssh, il faut démarrer le service

    eval "$(ssh-agent -s)"

    Vous devriez obtenir une information du type

    Agent pid 78944

    On ajoute la clé au ssh-agent

    ssh-add -K ~/.ssh/id_rsa

    Où id_rsa représente le nom de la clé, celui ci peut varier
    Ajoutez la clé sur votre compte GitHub ou Bitbucket et le tour est joué

    pbcopy < ~/.ssh/id_rsa.pub
    # Cette ligne de code copie dans le presse-papiers la clé

