Bonjour et merci pour vos formations tr�s enrichissante, surtout CakePHP et sublime text que j'ai d�couvert gr�ce � vous et dont je ne peux plus m'en pass�. (lol)


Modification des snippets CakePHP

J'ai effectu� quelque modification au snippet d�j� existant afin de mieux correspondre au version r�cente de CakePHP 2.3.4 et supp�rieur

En plus j'en ai ajouter plusieurs que ce soit du cot� des Mod�les , Vues et Controlleur.

Ajout des snippets PHP

J'ai cr�er une s�rie de plusieurs snippets PHP 

Pour les snippets voici la logique que j'ai respect�

 Si fichier existant sans �tre modifi� alors :
 
	nom = correspond au nom du fichier
	.sublime-snippet = extension
	
	auth.sublime-snippet le snippet reprend le nom du fichier + la touche tab ( auth + TAB )
	
Si j'ai modifi� ou ajout� un nouveau snippet alors :

	- = le s�parateur
	code = code du snippet sera le code a taper + la touche TAB
	info = nom du snippet ou une br�ve description
	.sublime-snippet = extension
	
	c5-crochet5.sublime-snippet le code du snippet est c5 sont info crochet5 indique qu'il y aura 5 crochets cela donnera $[""][""][""][""][""] ; avec \$$1["$2"]["$3"]["$4"]["$5"]["$6"] ; $7
	(=)-echo.sublime-snippet le code ici sera juste le = sans les parenth�ses info indique un echo celui-ci donnera <?=  ; ?> avec <?= $1; ?>
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
		
	et un autre exemple pour CakePHP cot� vues
	
	vff5.sublime-snippet le code vff5 ici le code est vff5 � savoir que ce fichier est ranger dans PHP\template\forms 
	
	ici le code traduit v = vue pour tous les snippet des vues il ont ce prefix v au d�but
	le premier f = form indique un formulaire
	le deuxi�me f = indique que ce form sera de type file d'ou le deuxi�me f
	et le 5 indique qu'il y aura 5 champs de type input avec comme premier champ un input qui aura le type file en param�tre
	
	cela donne au format snippet pour voir les $
	
	<?= \$this->Form->create('$1', array('type' => 'file')); ?>
		<?= \$this->Form->input('$2', array('type' => 'file', 'label' => '$3')); ?>
		<?= \$this->Form->input('$4', 'label' => '$5')); ?>
		<?= \$this->Form->input('$6', 'label' => '$7')); ?>
		<?= \$this->Form->input('$8', 'label' => '$9')); ?>
		<?= \$this->Form->input('$10', 'label' => '$11')); ?>
	<?= \$this->Form->end('Enregistrer'); ?>
	
	il y a aussi sont �quivalent qui est : 
	
	vf5.sublime-snippet le code vf5 ici le code est vf5 � savoir que ce fichier est ranger dans PHP\template\forms 
	
	ici le code traduit v = vue pour tous les snippet des vues il ont ce prefix v au d�but
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
	
	adp3-array-double-param3.sublime-snippet le code adp3 info indique un tableau double voulant dire un array associatif alors que si on ne met pas le d cela fera un array index� et param3 indique qu'il y aura 3 param�tres
	
	cela donne en code snippet
	
	array("$1" => array("$2" => "$3"),"$4" => array("$5" => "$6"),"$7" => array("$8" => "$9")); 
	
	Ah si j'oubli� il y en a un de sp�cial car windows m'aime pas les ? dans les nom de fichier alors que le = passe aller comprendre donc ce fichier est :
	
	php.sublime-snippet sont code snippet est le ? + la touche de tabulation comme toujours. sont r�sultat est simple <?php $1 ; ?>
	
	Voil� pour la d�mo rapide mais il y en a plusieurs que vous allez d�couvrir et normalement il devrait aller vite � prendre en main apr�s cela vous pourrez me dire ce que vous en pensez =)