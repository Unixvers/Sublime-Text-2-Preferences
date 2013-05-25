Bonjour et merci pour vos formations très enrichissante, surtout CakePHP et sublime text que j'ai découvert grâce à vous et dont je ne peux plus m'en passé. (lol)


Modification des snippets CakePHP

J'ai effectué quelque modification au snippet déjà existant afin de mieux correspondre au version récente de CakePHP 2.3.4 et suppérieur

En plus j'en ai ajouter plusieurs que ce soit du coté des Modèles , Vues et Controlleur.

Ajout des snippets PHP

J'ai créer une série de plusieurs snippets PHP 

Pour les snippets voici la logique que j'ai respecté

 Si fichier existant sans être modifié alors :
 
	nom = correspond au nom du fichier
	.sublime-snippet = extension
	
	auth.sublime-snippet le snippet reprend le nom du fichier + la touche tab ( auth + TAB )
	
Si j'ai modifié ou ajouté un nouveau snippet alors :

	- = le séparateur
	code = code du snippet sera le code a taper + la touche TAB
	info = nom du snippet ou une brève description
	.sublime-snippet = extension
	
	c5-crochet5.sublime-snippet le code du snippet est c5 sont info crochet5 indique qu'il y aura 5 crochets cela donnera $[""][""][""][""][""] ; avec \$$1["$2"]["$3"]["$4"]["$5"]["$6"] ; $7
	(=)-echo.sublime-snippet le code ici sera juste le = sans les parenthèses info indique un echo celui-ci donnera <?=  ; ?> avec <?= $1; ?>
	e-echo.sublime-snippet le code est le e info indique un echo celui-ci donnera echo  ;  avec echo $1; 
	
	exemple d'un snippet un peut plus puissant pour PHP
	
	si5-if-else-if5.sublime-snippet le code sera si5 l'info indique un if else if fois 5 donc :
		
		if() avec if($1)
		{
		 ; avec $2
		}
		else if() avec else if ($3) etc...
		{
		 ;
		}
		else if()
		{
		 ;
		}
		else if()
		{
		 ;
		}
		else if()
		{
		 ;
		}
		else if()
		{
		 ;
		}
		else 
		{
		 ;
		}
		
	et un autre exemple pour CakePHP coté vues
	
	vff5.sublime-snippet le code vff5 ici le code est vff5 à savoir que ce fichier est ranger dans PHP\template\forms 
	
	ici le code traduit v = vue pour tous les snippet des vues il ont ce prefix v au début
	le premier f = form indique un formulaire
	le deuxième f = indique que ce form sera de type file d'ou le deuxième f
	et le 5 indique qu'il y aura 5 champs de type input avec comme premier champ un input qui aura le type file en paramètre
	
	cela donne au format snippet pour voir les $
	
	<?= \$this->Form->create('$1', array('type' => 'file')); ?>
		<?= \$this->Form->input('$2', array('type' => 'file', 'label' => '$3')); ?>
		<?= \$this->Form->input('$4', 'label' => '$5')); ?>
		<?= \$this->Form->input('$6', 'label' => '$7')); ?>
		<?= \$this->Form->input('$8', 'label' => '$9')); ?>
		<?= \$this->Form->input('$10', 'label' => '$11')); ?>
	<?= \$this->Form->end('Enregistrer'); ?>
	
	il y a aussi sont équivalent qui est : 
	
	vf5.sublime-snippet le code vf5 ici le code est vf5 à savoir que ce fichier est ranger dans PHP\template\forms 
	
	ici le code traduit v = vue pour tous les snippet des vues il ont ce prefix v au début
	le f = form indique un formulaire
	et le 5 indique qu'il y aura 5 champs de type input
	
	cela donne au format snippet pour voir les $
	
	<?= \$this->Form->create('$1'); ?>
		<?= \$this->Form->input('$2', array('label' => '$3')); ?>
		<?= \$this->Form->input('$4', 'label' => '$5')); ?>
		<?= \$this->Form->input('$6', 'label' => '$7')); ?>
		<?= \$this->Form->input('$8', 'label' => '$9')); ?>
		<?= \$this->Form->input('$10', 'label' => '$11')); ?>
	<?= \$this->Form->end('Enregistrer'); ?>
	
	J'ai pris exemple avec le 5 qui est le maximum donc il existe les version 1, 2, 3 et 4 aussi
	
	Allez un dernier pour la route
	
	adp3-array-double-param3.sublime-snippet le code adp3 info indique un tableau double voulant dire un array associatif alors que si on ne met pas le d cela fera un array indexé et param3 indique qu'il y aura 3 paramètres
	
	cela donne en code snippet
	
	array("$1" => array("$2" => "$3"),"$4" => array("$5" => "$6"),"$7" => array("$8" => "$9")); 
	
	Ah si j'oublié il y en a un de spécial car windows m'aime pas les ? dans les nom de fichier alors que le = passe aller comprendre donc ce fichier est :
	
	php.sublime-snippet sont code snippet est le ? + la touche de tabulation comme toujours. sont résultat est simple <?php $1 ; ?>
	
	Voilà pour la démo rapide mais il y en a plusieurs que vous allez découvrir et normalement il devrait aller vite à prendre en main après cela vous pourrez me dire ce que vous en pensez =)