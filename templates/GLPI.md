# FICHE DE SITUATION PROFESSIONNELLE — BLOC 1 (ÉPREUVE E5)

## 1. IDENTIFICATION GÉNÉRALE
- **Titre de la réalisation :** Gestion d'un parc informatique avec GLPI : inventaire manuel et automatisé, plan de nommage et traitement des tickets d'assistance
- **Cadre de réalisation :** [ ] Stage 1  [ ] Stage 2  [ ] Atelier de professionnalisation  [x] Projet de cours
- **Période de réalisation :** Mars 2025
- **Modalité :** [x] Individuel  [ ] En équipe
- **Localisation / Organisation cliente :** BTS SIO — activités GLPI ACT1, ACT2 et ACT3, réalisées pour une organisation fictive répartie sur trois sites (Toulouse, Cugnaux, Tarbes)

## 2. CONTEXTE ET OBJECTIFS
- **Contexte organisationnel :** Organisation fictive implantée sur trois sites (Toulouse, Cugnaux et Tarbes), avec plusieurs services et profils d'utilisateurs (managers, techniciens, vendeurs). Son parc est composé de postes Windows de différents fabricants (Asus, Dell, HP). Le système informatique support est un serveur GLPI hébergé dans une machine virtuelle VirtualBox, accessible depuis le poste hôte sur le réseau du lycée.
- **Problématique / Besoin exprimé :** Le suivi du parc se faisait sans outil dédié. Un inventaire manuel de seulement cinq logiciels sur un poste a pris environ trente minutes, ce qui est irréaliste pour un parc de 200 postes. L'organisation n'avait pas non plus de règles pour nommer les postes ni de moyen de suivre les demandes d'assistance des utilisateurs.
- **Objectifs fixés :** Recenser les postes et les logiciels dans GLPI (lieux, fabricants, statuts, licences), automatiser la remontée d'inventaire grâce à l'agent GLPI, définir un plan de nommage des postes, puis traiter des demandes d'assistance par tickets, de leur création jusqu'à leur clôture.

## 3. DÉMARCHE ET ENVIRONNEMENT TECHNIQUE
- **Environnement technologique mobilisé :**
  - Systèmes d'exploitation utilisés : machine virtuelle hébergeant le serveur GLPI, poste client Windows 10 Famille (portable HP Pavilion Gaming)
  - Logiciels, rôles ou paquets installés : GLPI (gestion de parc et helpdesk), GLPI Agent (fichier de configuration agent.cfg, lancement avec glpi-agent.bat), VirtualBox (redirection de ports en NAT), carte OpenStreetMap intégrée à GLPI
  - Matériels ou éléments d'infrastructure concernés : poste hôte sur le réseau du lycée (192.168.1.151), machine virtuelle GLPI (10.0.2.15), redirection du port TCP 9980 de l'hôte vers le port 80 de la VM, ordinateurs de l'inventaire (Asus, Dell, HP)
- **Démarche suivie étape par étape :**
  1. Analyse préalable et préparation de la maquette (ACT1) : création des lieux (Toulouse, Cugnaux), des fabricants (Asus, Dell, HP) et des statuts (En service, HS, Neuf) ; ajout des ordinateurs nommés selon leur site et leur service ; positionnement des lieux sur la carte avec leurs coordonnées GPS ; recherches filtrées dans le parc (PC de Cugnaux, PC Asus, PC Dell du service études) ; ajout du logiciel Word (Microsoft 16.0) avec le suivi de ses installations et de ses licences.
  2. Configuration et mise en œuvre technique (ACT2) : réalisation d'un inventaire manuel de cinq logiciels (nom, version, date d'installation) pour mesurer le temps nécessaire ; configuration d'une redirection de ports dans VirtualBox (192.168.1.151:9980 vers 10.0.2.15:80) pour rendre GLPI joignable ; modification de la ligne server du fichier agent.cfg (http://192.168.1.151:9980/glpi/front/inventory.php) ; lancement de l'agent avec glpi-agent.bat ; manipulations sur l'inventaire remonté (comptage des composants, suppression en masse de logiciels vers la corbeille, règle de recherche excluant Notepad++).
  3. Tests d'acceptation et vérification du bon fonctionnement (ACT2 et ACT3) : vérification de la remontée automatique du poste dans GLPI (45 composants, 3 volumes, 247 logiciels, 4 ports réseau, ainsi que le modèle, le numéro de série et le processeur) ; définition d'un plan de nommage (site, puis poste, puis numéro : CU, TA ou TL, puis MA, TC ou VE, par exemple TL-MA-01) ; création de deux tickets avec leur urgence, leur impact, leur priorité et leur lieu (« Blue screen 2 fois par jour », priorité haute, et « Problème d'internet », priorité très haute) ; suivi avec une vue filtrée par statut et par observateur ; réponses aux demandeurs, demande d'une capture d'écran de la commande ipconfig, proposition de solutions, validation par les demandeurs et clôture des deux tickets.
- **Gestion des imprévus / Incidents rencontrés :** Lors de l'affichage sur la carte, les lieux apparaissaient en pleine mer, faute de coordonnées géographiques. Le problème a été corrigé en renseignant la localisation de chaque lieu, ce qui a permis d'afficher correctement Toulouse et Cugnaux. L'agent GLPI ne pouvait pas joindre le serveur installé dans la machine virtuelle, isolé en NAT : une règle de redirection de ports dans VirtualBox et l'adresse correspondante dans agent.cfg ont permis la remontée de l'inventaire.

## 4. RÔLE ET CONTRIBUTION PERSONNELLE
*(Particulièrement important si le projet a été mené en équipe)*
- **Responsabilité précise :** Réalisation de l'ensemble des activités GLPI ACT1 à ACT3 : paramétrage du parc, mise en place de l'inventaire automatique, définition du plan de nommage, traitement des tickets dans le rôle de technicien.
- **Actions menées individuellement :** Création des lieux, fabricants, statuts, ordinateurs et logiciels ; inventaire manuel et analyse de ses limites ; configuration de la redirection de ports et de l'agent GLPI ; manipulations et filtres sur l'inventaire ; rédaction du plan de nommage ; création, suivi, réponse et clôture des tickets ; rédaction du compte rendu illustré de captures d'écran.

## 5. LIVRABLES ET PREUVES ASSOCIÉES
*(Éléments vérifiables à intégrer sur le portfolio)*
- Procédure technique ou document d'exploitation rédigé : compte rendu GLPI ACT1, ACT2 et ACT3 décrivant la création du parc, la configuration de l'agent et le traitement des tickets
- Schéma d'architecture ou plan d'adressage : schéma du flux poste client → hôte 192.168.1.151:9980 → VM GLPI 10.0.2.15:80, et plan de nommage des postes (à mettre au propre)
- Extraits de configurations ou scripts commentés : ligne server du fichier agent.cfg et règle de redirection de ports VirtualBox
- Captures d'écran significatives (avec masquage des données sensibles) : liste des ordinateurs et carte des lieux, fiche du poste inventorié automatiquement (45 composants, 247 logiciels), échanges dans les tickets, liste des tickets clos
- Cahier de recette ou rapport de tests : comparaison entre inventaire manuel et inventaire automatique, et tableau de suivi des deux tickets (priorité, statut, date d'ouverture et de clôture)

## 6. COMPÉTENCES DU BLOC 1 MOBILISÉES
- [x] **B1.1 — Gérer le patrimoine informatique :** Recensement du matériel et des logiciels dans GLPI (lieux, fabricants, statuts, licences), automatisation de l'inventaire avec l'agent GLPI, définition d'un plan de nommage normalisé des postes.
- [x] **B1.2 — Répondre aux incidents et demandes d'assistance :** Création et qualification des tickets (urgence, impact, priorité), suivi avec des vues filtrées, diagnostic à distance (demande d'une capture ipconfig), proposition de solutions, validation par les demandeurs et clôture.
- [ ] **B1.3 — Développer la présence en ligne**
- [ ] **B1.4 — Travailler en mode projet**
- [x] **B1.5 — Mettre à disposition des utilisateurs un service informatique :** Mise en service d'un outil de gestion de parc et de helpdesk joignable depuis le réseau, et accompagnement des utilisateurs par des réponses détaillées étape par étape.
- [ ] **B1.6 — Organiser son développement professionnel**

## 7. BILAN RÉFLEXIF ET AUTO-ÉVALUATION
- **Points forts :** Le gain de l'automatisation est démontré concrètement : environ trente minutes pour cinq logiciels relevés à la main, contre 247 logiciels et 45 composants remontés automatiquement par l'agent. Les deux tickets ont été traités de bout en bout, jusqu'à leur validation et leur clôture.
- **Axes d'amélioration :** Appliquer le plan de nommage aux postes déjà créés dans GLPI pour harmoniser le parc. Déployer l'agent automatiquement sur l'ensemble des postes (script ou GPO) plutôt que par un lancement manuel. Configurer une exécution périodique de l'agent et utiliser HTTPS entre l'agent et le serveur. Approfondir le diagnostic avant de proposer une solution, par exemple en consultant l'observateur d'événements pour un écran bleu, et rédiger des réponses plus structurées dans les tickets.
- **Compétences professionnelles consolidées :** Prise en main de GLPI pour la gestion d'actifs et le helpdesk, configuration d'un agent d'inventaire et d'une redirection de ports en NAT, qualification et priorisation des incidents selon l'urgence et l'impact, et communication écrite avec des utilisateurs non spécialistes.
