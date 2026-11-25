# FICHE DE SITUATION PROFESSIONNELLE — BLOC 1 (ÉPREUVE E5)

## 1. IDENTIFICATION GÉNÉRALE
- **Titre de la réalisation :** Préparation, masterisation et déploiement de postes clients sous Windows 11
- **Cadre de réalisation :** [x] Stage 1  [ ] Stage 2  [ ] Atelier de professionnalisation  [ ] Projet de cours
- **Période de réalisation :** Mai/Juin 2025 (du 26 mai au 25 juin 2025, livraison prévue le 1er juillet 2025)
- **Modalité :** [ ] Individuel  [x] En équipe (Avec l'aide d'un des membres du service informatique)
- **Localisation / Organisation cliente :** SCLE — service informatique, pour le compte de plusieurs entreprises clientes

## 2. CONTEXTE ET OBJECTIFS
- **Contexte organisationnel :** L'entreprise d'accueil dispose d'un service informatique qui gère le support interne (tickets GLPI, comptes utilisateurs, brassage réseau, dépannage matériel) et fournit des postes de travail à des entreprises clientes. Le système informatique support comprend un parc de PC sous Windows 10 et 11, un serveur sur lequel les postes sont référencés (avec mise en liste noire des postes hors service), un outil de déploiement d'images système (Theopenem), l'outil de gestion de parc GLPI et une baie de brassage.
- **Problématique / Besoin exprimé :** Plusieurs entreprises clientes ont demandé le renouvellement de leurs postes avec des dates de livraison rapprochées. Il fallait livrer des postes prêts à l'emploi : matériel mis à niveau, système à jour, configuration personnalisée pour chaque utilisateur et accessoires fournis.
- **Objectifs fixés :** Préparer un lot de postes clients (dont 7 PC le 16 juin) pour une livraison au 1er juillet 2025 : passage de la RAM de 8 Go à 16 Go, installation de Windows 11 à jour avec pilotes et logiciels, application de l'image système de l'entreprise (ghost), personnalisation de chaque poste, configuration de l'adaptateur série USB et préparation du matériel de livraison.

## 3. DÉMARCHE ET ENVIRONNEMENT TECHNIQUE
- **Environnement technologique mobilisé :**
  - Systèmes d'exploitation utilisés : Windows 11 (version 24H2), Windows 10 (migration d'un poste depuis Windows 7)
  - Logiciels, rôles ou paquets installés : clé USB d'installation (image ISO Windows 11), Windows Update, invite de commandes (CMD) en mode administrateur, Theopenem (ghost), gestionnaire de périphériques, pilotes constructeurs (Dell, Moxa), BIOS/UEFI, VMware, GLPI
  - Matériels ou éléments d'infrastructure concernés : PC portables clients, barrettes de RAM (8 Go → 16 Go), SSD, adaptateur série USB Moxa UPort 1100 Series, adaptateurs USB-Ethernet, câbles RJ45 de 2 m, lecteurs DVD, sacoches et chargeurs
- **Démarche suivie étape par étape :**
  1. Analyse préalable et préparation de la maquette : recensement des demandes dans un tableau de suivi (nom de l'entreprise, nom du client, date de livraison) pour planifier la préparation selon les échéances, puis préparation des composants et accessoires de chaque client.
  2. Configuration et mise en œuvre technique : ajout d'une barrette de RAM (8 Go → 16 Go), désactivation du Secure Boot et de la virtualisation dans le BIOS, installation de Windows 11 depuis la clé USB, mises à jour du système et des logiciels, redémarrage avec F9 et application du ghost depuis le dossier Theopenem, mise à jour des pilotes, renommage de l'utilisateur au nom du client, synchronisation de l'horloge et configuration de l'adaptateur série (passage de COM3 à COM1, latence au minimum).
  3. Tests d'acceptation et vérification du bon fonctionnement : contrôle du démarrage après le ghost et des mises à jour installées, vérification dans le gestionnaire de périphériques qu'aucun pilote ne manque et que l'adaptateur est sur COM1, vérification de la RAM, du nom d'utilisateur et de l'heure, contrôle du contenu de chaque sacoche avant livraison.
- **Gestion des imprévus / Incidents rencontrés :** Erreur 0xc1900201 lors de la mise à jour Windows 11 24H2, due à un manque d'espace sur la partition EFI : résolue avec l'invite de commandes en mode administrateur en libérant de l'espace sur la partition EFI, puis en relançant la mise à jour. Démarrage impossible sur la clé USB : résolu en désactivant le Secure Boot et la virtualisation dans le BIOS. Adaptateur série non reconnu : après l'échec de la recherche automatique, identification du modèle exact (Moxa UPort 1100 Series), téléchargement du pilote Windows 11 sur le site officiel du constructeur et installation, ce qui a permis le passage de COM3 à COM1.

## 4. RÔLE ET CONTRIBUTION PERSONNELLE
*(Particulièrement important si le projet a été mené en équipe)*
- **Responsabilité précise :** Préparer et configurer les postes clients de bout en bout, de la mise à niveau matérielle jusqu'à la préparation pour la livraison, sous la supervision d'un membre de l'équipe.
- **Actions menées individuellement :** Installation des barrettes de RAM et remplacement d'un SSD, installation de Windows 11, mises à jour, application du ghost et personnalisation des postes, diagnostic et résolution de l'erreur 0xc1900201, recherche et installation des pilotes (Dell, Moxa), configuration des ports COM, tenue du tableau de suivi des livraisons, préparation des sacoches et rédaction d'un lexique technique.

## 5. LIVRABLES ET PREUVES ASSOCIÉES
*(Éléments vérifiables à intégrer sur le portfolio)*
- Procédure technique ou document d'exploitation rédigé : procédure de préparation d'un poste client Windows 11 et procédure de résolution de l'erreur 0xc1900201
- Schéma d'architecture ou plan d'adressage : schéma du processus de préparation d'un poste (réception → mise à niveau → installation → ghost → tests → livraison)
- Extraits de configurations ou scripts commentés : réglages BIOS (Secure Boot, virtualisation) et propriétés du port COM1 (latence)
- Captures d'écran significatives (avec masquage des données sensibles) : message d'erreur 0xc1900201, gestionnaire de périphériques avant/après installation du pilote Moxa, tableau de suivi des livraisons anonymisé
- Cahier de recette ou rapport de tests : liste de contrôle par poste (RAM, mises à jour, pilotes, nom d'utilisateur, heure, port COM, contenu de la sacoche)

## 6. COMPÉTENCES DU BLOC 1 MOBILISÉES
- [x] **B1.1 — Gérer le patrimoine informatique :** Recensement des postes à livrer, mise à niveau matérielle (RAM, SSD), application de l'image système de référence, mise en liste noire des postes hors service et récupération de leurs composants.
- [x] **B1.2 — Répondre aux incidents et demandes d'assistance :** Diagnostic et résolution de l'erreur 0xc1900201 et du pilote manquant de l'adaptateur série, traitement des demandes liées aux postes (remplacement de clavier et de SSD).
- [ ] **B1.3 — Développer la présence en ligne :** Non mobilisée dans cette réalisation.
- [x] **B1.4 — Travailler en mode projet :** Planification de la préparation selon les dates de livraison (tableau de suivi), respect de l'échéance du 1er juillet 2025, travail en équipe avec le service informatique.
- [x] **B1.5 — Mettre à disposition des utilisateurs un service informatique :** Déploiement de postes opérationnels et personnalisés, tests de bon fonctionnement avant livraison, fourniture du matériel nécessaire à l'utilisateur final.
- [x] **B1.6 — Organiser son développement professionnel :** Recherche de solutions dans des ressources en ligne (tutoriel, sites constructeurs), rédaction d'un lexique technique, maquette Linux personnelle menée en parallèle (Auditd, PAM, Cron, Bash).

## 7. BILAN RÉFLEXIF ET AUTO-ÉVALUATION
- **Points forts :** Démarche de préparation rapidement maîtrisée et reproductible, autonomie croissante dans le diagnostic (recherche du code d'erreur, identification du modèle exact, sites officiels des constructeurs) et échéance de livraison respectée.
- **Axes d'amélioration :** Rédiger dès le départ une procédure et une liste de contrôle formelles, réactiver le Secure Boot après l'installation pour la sécurité, intégrer à l'image ghost les réglages faits à la main (pilotes, port COM, horloge) pour automatiser, et enregistrer chaque poste livré dans l'inventaire GLPI pour la traçabilité.
- **Compétences professionnelles consolidées :** Maîtrise du BIOS/UEFI et de l'installation de Windows 11, déploiement par image système, gestion des pilotes et des périphériques, méthode de résolution d'incidents (identifier, rechercher, appliquer, vérifier) et organisation du travail selon des échéances clients.
