# CursoXR - Application Android XR

Application Android développée en Kotlin avec Jetpack Compose qui fonctionne à la fois sur mobile et sur Android XR.

## Fonctionnalités

- **Liste de vidéos** : Affiche une liste de vidéos récupérées depuis l'API
- **Lecteur vidéo mobile** : Interface 2D pour la lecture de vidéos sur mobile
- **Lecteur vidéo XR** : Interface spatiale pour Android XR avec fenêtre séparée
- **Modèle 3D** : Affichage d'un terrain de football 3D lors de la lecture vidéo en mode XR

## Architecture

### Modèles de données
- `Video` : Modèle représentant une vidéo avec titre, description, URL, etc.
- `VideoList` : Conteneur pour la liste des vidéos

### Services
- `VideoApiService` : Service Retrofit pour récupérer les vidéos depuis l'API
- `ApiClient` : Client HTTP configuré avec Retrofit et Gson

### ViewModel
- `VideoViewModel` : Gestion de l'état de l'application et des interactions utilisateur

### Composants UI
- `VideoList` : Composant pour afficher la liste des vidéos
- `VideoPlayer` : Lecteur vidéo pour mobile (2D)
- `XrVideoPlayer` : Lecteur vidéo pour Android XR
- `FootballField3D` : Représentation 3D simplifiée d'un terrain de football

## Technologies utilisées

- **Kotlin** : Langage de programmation
- **Jetpack Compose** : Framework UI moderne
- **Android XR** : Support pour la réalité étendue
- **Retrofit** : Client HTTP pour les appels API
- **ExoPlayer** : Lecteur vidéo
- **Coil** : Chargement d'images
- **Material Design 3** : Design system

## Configuration

### Dépendances principales
- Android XR Compose
- Retrofit pour les appels réseau
- ExoPlayer pour la lecture vidéo
- Coil pour le chargement d'images

### Permissions
- `INTERNET` : Pour les appels API
- `ACCESS_NETWORK_STATE` : Pour vérifier l'état du réseau

## API

L'application utilise l'API suivante :
- **Endpoint** : `https://hls-video-samples.r2.immersiv.cloud/videos.json`
- **Format** : JSON avec liste de vidéos

## Utilisation

### Mode Mobile (2D)
1. L'application affiche la liste des vidéos
2. Cliquer sur une vidéo ouvre le lecteur en plein écran
3. Bouton pour basculer en mode XR (si disponible)

### Mode Android XR
1. La liste des vidéos s'affiche dans une fenêtre spatiale
2. Cliquer sur une vidéo ouvre le lecteur dans une fenêtre séparée
3. Un terrain de football 3D apparaît devant la fenêtre vidéo lors de la lecture

## Développement

### Compilation
```bash
./gradlew assembleDebug
```

### Tests
L'application peut être testée sur :
- Émulateur Android standard
- Émulateur Android XR (selon la documentation officielle)

## Notes techniques

- Le modèle 3D du terrain de football est une représentation simplifiée
- L'application détecte automatiquement si elle fonctionne en mode XR
- Les vidéos sont lues avec ExoPlayer qui supporte HLS
- L'interface s'adapte automatiquement au mode d'affichage (2D/XR)

## Auteur

Développé pour le test technique Android - Immersiv.io

