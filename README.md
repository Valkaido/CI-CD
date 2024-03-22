# TP2 - CI-CD
## Résumé du projet
Ce repository GitHub contient un prototype simple d'une application Flask avec une pipeline CI/CD intégrée, déployée sur Azure Web App. Cette démonstration met en œuvre les bonnes pratiques DevOps, notamment l'utilisation de Git, la mise en place de tests unitaires et la mise en place d'une pipeline CI/CD pour automatiser le processus de build, de test et de déploiement.
## Pré-requis
- Python 3.x
- Un compte GitHub
- Un compte Azure avec accès à Azure Web App
## Microsoft Azure
- Créer une web application depuis le portail azure
- Récupérer le profil de publication de la web app
- Aller dans les settings de son repository puis dans **Secrets and variables** puis **Actions**
- Ajouter un nouveau repository secret avec comme nom : **AZURE_WEBAPP_PUBLISH_PROFILE** à l'intérieur de celui-ci copier coller ce que vous avez dans le fichier que vous venez de télécharger précédemment.
## Contenu du Repository
- **app.py**: Fichier principal de l'application Flask contenant les routes et la logique métier.
- **test_app.py**: Fichier de test unitaire pour l'application Flask.
- **requirements.txt**: Fichier spécifiant les dépendances Python nécessaires à l'application.
- **.github/workflows/main.yml**: Fichier de configuration de la pipeline CI/CD utilisant GitHub Actions.
- **README.md**: Fichier de documentation expliquant le projet et fournissant des instructions pour le configurer et l'exécuter.
## Installation & Exécution
### Clonage du repository
```
git clone https://github.com/Valkaido/CI-CD/
cd CI-CD
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

1.  Effectuez des changements dans le code (exemple fichier app.py) depuis VSCode :
```
@app.route("/")
def home():
    return "Welcome to the Flask CI/CD Demo! This is V3!"
```
2.  Poussez les changements vers la branche principale du repository GitHub (dans le terminal VSCode) :
```
git add.py
git commit -m "Update app.py"
git push
```
3.  Suivez l'exécution de la pipeline CI/CD dans l'onglet "Actions" de votre repository GitHub.
<img src="https://cdn.discordapp.com/attachments/873558423793446987/1220312468476395571/image.png?ex=660e7b8c&is=65fc068c&hm=9424fc59425adf604b207b81b31511bc136c347d54f774d5baaf783cdbb85ea1&"></img>
4. Détail du run
<img src="https://cdn.discordapp.com/attachments/873558423793446987/1220312516337598464/image.png?ex=660e7b98&is=65fc0698&hm=51f5d13109109bd57c471f5fd407130a24a83c3f76bd557f575947767f65acac&">
5.  Vérifiez que les tests passent avec succès et que l'application est déployée sur Azure Web App.
<img src="https://cdn.discordapp.com/attachments/873558423793446987/1220302141453766706/image.png?ex=660e71ee&is=65fbfcee&hm=899088e8c75b245c961b8dc83ef83d7389635c66742a5d68e29e8c35828776d0&">
L'exemple ci-dessus montre un test qui a bien était déployé sur Azure Web App.
