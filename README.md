# git_worflow 

## faire son propre depot avec fork et upstream (forker et lier votre depot au mien)

  - first : fork le depot de base (le github actuel) (url https://github.com/romain20260/domBeginner)
  
  - second : depuis votre espace prendre l'url de votre propre depo de domBeginner soit: https://github.com/__"votreNomUserGithub"__/domBeginner
  
  - third : clone votre depot pour faire un cpie de travail en local (terminal)
  
    - command dans votre terminal (console)
    - dans le path de votre desktop par exemple 
    - git clone https://github.com/__"votreNomUserGithub"__/domBeginner (url doit correspondre au path de votre depot)
    
  - fourth : check les remotes 
  
    -toujours dans la console
    - git remote -v (vous indique les remotes de votre copie de travail (les liens des actions fetch (pull) et push pointant vers url de votre depot)
    (origin est part convention le nom du remote à utiliser pour pointer vers le liens)
    (d'ou le git pull origin master pour sync le depot distant)
    
  - fifth : creer un lien depuis votre copie de travail (donc le local) vers le depot https://github.com/romain20260/domBeginner donc celui-ci
  
    - toujour dans le terminal 
    - git remote add upstream https://github.com/romain20260/domBeginner
    (cela va rajouter deux remote name upstream (ici aussi s'est un convention), un fetch et un push 
    - verifier avec git remote -v
    
  - sixth : enlever le remote du upstream push (car cela pointe le push sur mon depot) par précaution 
   
   - toujours dans le terminal
   - git remote set-url --push upstream DISABLED 
   (cela set la commande push de upstream vers DISABLE qui n'est pas un url)
   (si lors de la creation du remote add vous avez rentrer un autre nom veillez a upstream de la commande par le nom de la remote que vous avez creer)
   - verifier avec gt remote -v
   
votre propre copie de travail du depot de domBeginner (dans le local) et liée avec mon depot pour etre pull grace a upstream

## comment pull mon depot sur votre local avant d update votre depot distant

  - firts : recuperer mes commit from mon depot et les fusionner sur votre copie de travail (local)
  
    - dans votre terminal(console) dans le dossier du depot local (dans la branch master)
    - git pull upstream master 
    (va chercher dans mon depot les commits de master et puis les mergent a votre branch actuel (veillez a ce que ce soit master)
    (ceci va mettre a jour le master de votre local)
    
  - second : push ses modification sur votre depot distant (soit origin)
  
    - git push origin master 
    (ainsi les modification seront pousser vers origin (votre depot distant))
    
bien-sur tout ca vous pouvez le faire sur n'importe quelle branche mais en general ont le fais sur master puis tirer un branche ou rebase sa branche de dev (histoire de laissez les master propre)

## rebase sa branche de travail si master est up-to-date

  - firts : verifier que master (local) soit à jour
    - avec git pull upstream master 
    (le terminal vous informe que vous etes à jour ou effectue le pull dans le cas echeant)
  
  - si vous etes pas a jour :
    - depuis master faites : 
    git pull upstream master
    - puis pousser les modif sur votre depot distant(origin) : 
    git push origin master 
    - puis depuis votre branch de travil (local) :
    git rebase master
    (voila votre branch de travail est à jour)
    
    
## bonne pratique git et github
 
 - veillez à travail sur un fork (au besoin pull request la base "upstream")
 - veillez à travaillez sur des branche up-to-date (à jour) sur votre master lui meme up-to-date par rapport a upstream
 - ne pas travaillez sur master directement
 - veillez mettre a jours votre master depot local au debut
 - commit avant de cloturer le travail (voir un push sur origin pour plus de securité)
 - veillez a verifier avec un rebase avant tout push
    
  


# domBeginner
série d'exercice pour le Dom 

## prérequis

- savoir manipuler des données via differentes structures (variables, tableaux, objets).

- connaitre les structures de contrôle (boucles et conditions).

- connaitre les fonctions (classic, anonymes, fléchées, notions de callback (synchrone et un peu d'asynchrone).

- difference entre passez en arguments (lors de l'appel de la fonction) la valeur , ou la reference.

## contenue des exercices
#### les exercices sont de plus en plus dur meme si parfois vous pourriez avoir un exercice d'appoint 

  + au __début__ les énnoncés sont rédiger clairement en dessus du noeud à ciblé
  
  >>
                  <div>section 1 enfant 1 (class)</div>
                <!-- selectionne le node du dessus grace à une class -->
  >>
  
  + parfois un commentaires permet d'avoir une astuce ou un __liens vers de la documentation__ pour debloquer des situation d'exercices 
  
  >>
      
                                                            exercice astuce : 
          ASTUCE PART       ========>>>>>>                  Lorem ipsum dolor sit amet, consectetur adipiscing elit. Ut ex nisl, tristique vel lacus et, 
                                                            blandit pretium ante. Maecenas hendrerit, ipsum pharetra ornare
                                                            imperdiet, diam nisi congue nulla, in condimentum justo orci sit amet metus. 
                                                            Curabitur quam elit, varius dapibus dapibus maximus, semper ut diam. Aenean interdum 

  >>

  + observation... est une notation pour indiquer qu'il est __important d'analyser le comportement du code et des données__
  
  >>
                   <-- observation..... -->
  >>
  suivi ou non bien d'une target OBSERVATION
  >>
                      <!-- OBSERVATION....
                         Donec vitae libero ultrices, dignissim nibh quis, volutpat metus. Nullam 
                         viverra ultrices massa, nec feugiat erat. Donec eu veli. 
                    -->
  >>
  
  + CONSEIL est utiliser pour donner des conseil, bonne pratique ou eclairer un point important __génèralement en fin de page__
  
  >>
      <!--
    :
    CONSEIL...
    :
    Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nullam rhoncus purus ipsum, non efficitur 
    est fermentum sit amet. Donec consequat ipsum sed elit volutpat ultricies. Sed scelerisque mollis sem ut convallis. 
    Praesent suscipit lectus in tristique ullamcorper. Donec vitae libero ultrices, dignissim nibh quis, volutpat metus. Nullam 
    viverra ultrices massa, nec feugiat erat. Donec eu velit mi. Mauris blandit non mauris suscipit aliquet.  
      -->
  >>
  
  ## conseil de worflow
  
 -- une fois __forked dans votre repositorie__ de votre compte GitHub, __cloné__ depuis __votre repositorie__  une __copie de travail dans votre local__
  je vous __conseil__ de tirer une branche tout les trois exercices.
  ainsi vous pouvez tirer de nouveau apres les trois exercice fini depuis master, pouvons ainsi au besoin refaire les exercices en amont(laisser master clean)
  apres s'est a votre guise.
  
 -- ecrivez votre JavaScript ou vous le souhaitez meme si les bonnes pratique veulent que l'on l'ecrive dans un fichiers à part, 
    pour la bonne tenue des exercices et la comprehension du script je vous conseil de l'ecrire à la fin du body dans la balise script qui lui est attribuer. 
   
   >>
   
     <script>




     </script>
     
   >>
  
  ## les partie aborder ou en ellaboration
  
  - chercher un noeuds du DOM depuis un script 
  
  - manipuler en element (noeuds)
  
  - les events 
  
  - les forms
  
  
