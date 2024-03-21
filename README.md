# TP2 - CI-CD
## Résumé du projet
Ce repository GitHub contient un prototype simple d'une application Flask avec une pipeline CI/CD intégrée, déployée sur Azure Web App. Cette démonstration met en œuvre les bonnes pratiques DevOps, notamment l'utilisation de Git, la mise en place de tests unitaires et la mise en place d'une pipeline CI/CD pour automatiser le processus de build, de test et de déploiement.
## Pré-requis
- Python 3.x
- Un compte GitHub
- Un compte Azure avec accès à Azure Web App
## Contenu du Repository
- **app.py**: Fichier principal de l'application Flask contenant les routes et la logique métier.
- **test_app.py**: Fichier de test unitaire pour l'application Flask.
- **requirements.txt**: Fichier spécifiant les dépendances Python nécessaires à l'application.
- **azure-pipelines.yml**: Fichier de configuration de la pipeline CI/CD pour Azure DevOps.
- **.github/workflows/main.yml**: Fichier de configuration de la pipeline CI/CD utilisant GitHub Actions.
- **README.md**: Fichier de documentation expliquant le projet et fournissant des instructions pour le configurer et l'exécuter.
## Installation & Exécution
### Clonage du repository
```
git clone https://github.com/Valkaido/CI-CD/
cd CI-CD
```
### Création de l'environnement virtuel
```
python3 -m venv venv
source venv/bin/activate
```
### Installation des dépendances
```
pip install -r requirements.txt
```
### Lancement des tests unitaires
```
python -m pytest -v
```
### Lancement de l'application en local
```
python app.py
```
## Fonctionnalités de l'Application
-  Route **Racine (/)**
    - Affiche un message de bienvenue.

-  Route **/new-deployment**
    - Simule un nouveau déploiement à partir de la pipeline CI/CD.

-  Route **/info**
     - Affiche des informations sur l'utilisateur.

## Pipeline CI/CD avec GitHub Actions
La pipeline CI/CD automatisée est configurée dans le fichier **.github/workflows/main.yml**. Cette pipeline comprend les étapes suivantes :
1. **Build de l'Application**:
      -  Installe les dépendances spécifiées dans requirements.txt.
      -  Effectue la vérification de conformité avec Flake8.
2. **Exécution des Tests Unitaires**:
      -  Lance les tests unitaires définis dans test_app.py.
3. **Déploiement en Production sur Azure Web App**:
      -  Utilise les actions Azure pour déployer l'application Flask sur Azure Web App.
## Démo et Tests de la Pipeline CI/CD
Pour tester la pipeline CI/CD, effectuez les étapes suivantes :

1.  Effectuez des changements dans le code.
2.  Poussez les changements vers la branche principale du repository GitHub.
3.  Suivez l'exécution de la pipeline CI/CD dans l'onglet "Actions" de votre repository GitHub.
4.  Vérifiez que les tests passent avec succès et que l'application est déployée sur Azure Web App.
