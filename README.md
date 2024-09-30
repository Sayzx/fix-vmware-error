# fix-vmware-error
Fix vmware permissions error

# Résolution de l'erreur "Accès refusé" sur VMware

## Problème
L'utilisateur reçoit un message d'erreur **"Accès refusé"** lors de l'exécution de VMware Workstation ou d'autres programmes. Cela indique un manque d'autorisations sur le répertoire d'installation.

## Solution
Pour résoudre ce problème, suivez ces étapes :

1. **Ouvrir l'Invite de commandes en tant qu'administrateur** :
   - Recherchez `cmd` dans Windows.
   - Faites un clic droit sur **Invite de commandes** et sélectionnez **"Exécuter en tant qu'administrateur"**.

2. **Prendre possession du dossier** :
   - Exécutez la commande suivante :

	(Ne pas oublier de remplacer le chemin par le vôtre)

      ```takeown /F "C:\Program Files (x86)\VMware\VMware Workstation" /R /D Y ```
 
   - Cela permet à l'utilisateur de devenir le propriétaire du dossier et de son contenu.

4. **Attribuer des permissions à l'utilisateur** :
   - Accordez les permissions avec la commande :
    
	 (Toujours pas oublier de remplacer le chemin & Remplacer tonuser par votre user de base)
	
      ```icacls "C:\Program Files (x86)\VMware\VMware Workstation" /grant tonuser:(F) /T ```
   
   - Remplacez `tonuser` par le nom de l'utilisateur concerné.

5. **Vérification des permissions** :
   - Pour vérifier que les permissions ont été correctement appliquées, utilisez :
     
	 (Toujours pas oublier de remplacer le chemin)
 
     ```icacls "C:\Program Files (x86)\VMware\VMware Workstation"```

5. Si cela marche pas vous pouvez **Redémarrer ou relancer la session** :
   - Fermez la session de l'utilisateur et rouvrez-la, ou redémarrez l'ordinateur pour appliquer les changements.

Cette procédure permet de résoudre les problèmes d'accès pour l'utilisateur lors de l'exécution de VMware ou d'autres applications.

