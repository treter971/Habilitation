# Application Habilitations
Application C# écrite sous Visual Studio 2019 Entreprise et exploitant une BDD MySQL.<br><br>
<strong>Important :</strong><br>
Si lors de l'exécution, vous obtenez une erreur d'accès à la BDD de type :<br>
<code>Error: 0 : Retrieval of the RSA public key is not enabled for insecure connections.</code> <br>
Alors, il faut ajouter le paramètre suivant dans la chaîne de connexion : <br>
<code>AllowPublicKeyRetrieval=True;</code><br>
La chaîne de connexion se trouve dans la classe Access (package 'dal') jusqu'au commit "Phase 6". Elle est transférée dans le fichier 'App.config' à partir du commit "Phase 7".<br>

### But de l'application
L'entreprise cliente a développé une application interne pour générer plus facilement des sites pour ses clients. Son utilisation consiste à gérer des paramétrages pour obtenir un site opérationnel (couleur de la charte, liste des pages souhaitées, fonctionnalités désirées…). Cette application est régulièrement enrichie par l'ajout de nouveaux modules et nécessite aussi la mise à jour des modules existants. Les modules sont hiérarchisés suivant le type de fichiers à générer : CSS, JavaScript, HTML, PHP. L'accès à la partie back-end de cette solution applicative doit être sécurisé. Suivant le profil des intervenants (stagiaire, designer, dev-front, dev-back), le niveau d'habilitation est différent et ne permet pas de faire les mêmes manipulations.<br>
Le responsable souhaite avoir <strong>un petit utilitaire pour gérer les profils, et donc les niveaux d'habilitations, des différents développeurs</strong>.<br>
L'application Habilitations représente cet utilitaire.<br>

### Instllation de l'application
Pour installer l'application vous devez cliquer sur le bouton "code" en haut a droite des fichiers, cette action ouvrira une fenetre avec marquer "Download ZIP" cliquez dessu.
une fois le fichier zip installer, vous devez l'extraire pour pouvoir procéder a l'instalation.
quand cette étape est terminé, ouvree le fichier, et rendez vous sur le dossier "Habilitations2024Installeur" puis "Release" et ensuite, cliquez sur "Habilitations2024Installeur.msi" ce qui vous ouvrira l'installeur.
