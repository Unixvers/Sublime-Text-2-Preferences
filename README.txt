Mise à jour et correction de petit défaut+ ajout de nouveau snippets

pour les petits défaut : 
	- j'ai retiré tout les point-virgule inutile
	- corrigé <?php au lieu de <?= dans les condition et boucle coté cakephp niveau template
	- j'ai ajouter une variable supplémentaire pour aller soit a chaque fois à la fin de la ligne d'instruction ou d'un saut de ligne en fonction du contexte
	- j'ai retiré certain snippets que je jugé inutile coté php notamment les double array et multiple array
	- j'ai revue le nommage des snippets afin de facilité leur mémorisation
	- j'ai égalisé les niveau défois il y e en que 3 ou 5 voir 7 là il y en a 10 partout
	
pour le nommage j'ai gardé le même principe qu'auparavent sauf que j'ai essayer de faire plus simple.

Pour le dossier PHP et aussi CakePHP/template

Les boucles (fe = foreach (avec elements as element), fek = foreach (avec elements as key => value), do = do while, w = while, f = for, sw = switch)
Pour appliquer les boucle à une vue cakephp utilisé le préfix v devant (ex: "fe" donne pour une vue "vfe") 
Une seul exception il n'y a pas de boucle do pour la vue ni de switch du moinns sans préfix "v" qui signifie vue et que par conséquant le code derrière et formaté en tant que tel 

Les conditions sont prefixé par cd : donc (cdi = if, cde = else et cdei = else if => ceci produit seulement le terme par exemple cde donne else { } c'est tout) par contre il y a
les blocs enuméré qui vont de cd1 à cd10 ( cd1 revient à faire un cdi donc un if seul, parcontre cd2 revient à faire un cdi + cde donc un if puis un else, et cd3 donne un cdi + cdie + cde soit l'équivalent d'un if - else if - else et de 4 à 10 on ajoute des blocs else if entre deux )
Pour appliquer les conditions à une vue cakephp il suffit d'utilisé le préfix v devant (cela fonctionne pour cdi qui donne vcdi et même cd5 qui donne vcd5)
Pour retenir facilement ce que fait un cd6 par exemple il permet d'écrire 5 condition auquel s'ajoute le else final soit 5 + else = 6 lol )
Seul execption coté vue cakephp il y a un snippet de plus qui est vei qui se traduit par v = vue, e = end et i = if donc cela créer un <?php endif ?> seul (comme vcdei est utilisé et que ce bloc existe que dans la vue j'ai omit le cd pour faire court )

Les tableaux il y a deux sortent les indexé ou les associatif pour les indexés comme c'est les plus simples il se nomme "a" pour array et pour les associatif il se nomme "aa" pour array associatif
ici c'est simple un "a" ou un "aa" peut aller de 1 à 10 en fonction du nombre de paramètre que l'on a besoin ( ex : a5 donne array("","","","","") et aa3 donne array(""=>"",""=>"",""=>"") )
Bonus sur les array associatif si on ajoute comme suffix "i" alors le tableau tiendra sur une ligne si on le met pas alors il sera sur plusieurs ligne une pour chaque paire clé valeur )
Ici coté vue cakephp pas besoin de préfixé le tout de "v" le "a3" par exemple reste "a3" tout comme un "aa6i" reste un "aa6i"

Les crochets c'est le plus simple il a le préfix "c" suivie du nombre de crochet que l'on a besoin et qui peut aller de 1 à 10 donc un c5 donne [""][""][""][""][""]
Ici comme pour les tableu pas de préfix à mettre du coté vue cakephp donc "c3" reste "c3"

coté php j'ai garder les 3 sippet de base qui sont :
	= pour un <?= ?>
	e pour un echo
	? pour <?php ?>
	
Un gros bonus à été ajouté pour ceux qui n'aime pas avec le type de codage A et qui préfère le type de codage B (voir ci-dessous)

Le type A (accolade a droite)			Le type B (accolade en dessous)

if (CONDITION) {						if (CONDITION) 
										{

} 										}	
else {									else
										{

}										}

ou aussi                                ou aussi

do {									do
										{
										
} while (CONDITION) ;					} while (CONDITION) ;

Par défaut c'est du type A mais si on préfère le type B alors 2 choix s'offre à nous

	- soit on préfix les conditions, boucles et switch du signe + ( ex : cdi -> +cdi ou w -> +w etc...)
	- soit on remplace les dossiers condition et boucle du dossier PHP par ceux contenu dans le zip accolade cela aura pour effet d'inversé le type par défaut (soit ici B devient le type par défaut donc pas le + devant mais si on préfix alors on se retrouve avec le type A)
De plus on a le choix de conserver ou non le deuxième type donc celui préfixé et les snippet sont dans un dossier nommé accolade à coté de default dans les dossiers condition et boucle du dossier PHP

Dans le zip il y a les deux dossiers nommés type A et type B dans chacun d'eux il y a les sous-dossiers "boucle et condition" et ses sous dossiers sont eux même composé de deux sous dossiers nommé "default et accolade"
Dans le projet les dossiers default et accolade se situe dans PHP puis dans les sous dossiers condition et boucle, le dossier default contient le type par défaut non préfixé du + et accolade contient le deuxième type mais avec le préfixe +

Voilà pour ce qui est des accolades çà c'est fait =)
Ah oui cela ne fonctionne que pour les snippets se trouvant dans ses dossiers donc PHP (uniquement), car je vais faire de même avec les snippets utilisées avec CakePHP. ( pour le moment ils sont tous du type A )

D'ailleur dans ce dossiers j'ai ajouter d'autre snippet comme par exemple ( dd pour debug($this->request->data) ou d tout seul pour debug() aussi da pour debug($this->Auth->user($1)) et ceci avec un préfix "v" ajoute un echo devant pour vd et vdd pour le coté vue et pour le vda fait un echo de AuthComponent::user() ) )
puis aussi ajout du "bf" (beforeFilter) comme indiqué cela ajoute un beforeFilter une variante aussi avec "bfa" qui ajoute un beforeFilter pour admin_index,admin_edit,admin_delete et index 

Et le admin je les remodifier aussi pour lui ajouter $this->layout="admin"; 

Alors coté flash là il y a eu pas mal d'ajout intéressant car les notif on des messages du prêt à être utilisé et dans plusieurs contexte comme l'ajout, la suppression, la modification, la connexion et la validation d'un formulaire et le tout avec les trois types de notification par défaut du bootstrap de Twitter
Donc si je résume pour les 3 couleur (rouge, vert et orange qui ont les class error, warning et success) ont chacune leur 5 types de message prédéfinit
A cela s'ajoute les notifs flash avec d'autre nom de class comme inverse,notif et les 3 du dessus mais sans message prédéfinit

les snippets flash sont préfixé par "fl" suivie de la première lettre de la class souhaite exemple success donne "fls" et si on veut mettre le message préséfinit avec on ajoute la première lettre des 5 types ci-dessous mais en aglais soit (u = update, a = added, d = delete, c = connect, f = form)
Exemple pour un message d'avertissement lors d'un ajout (type ajouter une catégorie) le snippet sera "flwa" et le message prédéfini dans ce cas là est : "Attention : certaine information manquante sont requisent pour valider votre enregistrement, merci de bien vouloir les renseigner." alors que pour une erreur du même type soit "flea" le message sera "Problème rencontré : les données transmises sont incorrectes , merci de bien vouloir les vérifier." chaque message et différent et de caractère générique afin qu'il s'adapte au mieux dans tous les cas en fonction du contexte et du type d'action effectué

Pour les formulaire coté vue CakePHP donc qui dit vue dit le préfixe "v" et pour le formlaire c'est "f" et pour un formulaire de type file "ff" a cela s'ajoute le nombre de champ désiré allant de 1 à 10
Exemple : vf5 -> donne un formulaire avec 5 champ et vff5 - donne un formulaire de type file avec 5 champ dont le premier et de type file

A cela s'ajoute de snippet "vfi" ajoute un champ form input et "vfif" ajoute un champ form input de type file

Enfin coté vue CakePHP 2 autres snippets utile "vtfl" v = vue et tlf = title for layout donc ajoute un title_for_layout et vl le v toujours vue et le l = link donc ajoute un lien $this->Html->link("$1",array('controller'=>'$2','action'=>'$3','admin' => $4))


Et pour finir ajout de snippet pour SASS dans le dossier du même nom pour le moment il y en a que 5 énnoncé ci-dessous il produise le code en conséquence

	ex = extends
	fu = function
	im = import
	in = include
	mi = mixin
	
Le seul point particulier avec les snippets SASS c'est que je leur est fixé un scope sur leur type de fichier scss donc ne sont utilisables que si le fichier porte cette extension