# TP 14: Client SOAP Android avec Kotlin et KSOAP2

Ce projet est une application Android développée en **Kotlin** qui agit comme un client pour consommer un service web **SOAP** de gestion de comptes bancaires.

## 📋 Fonctionnalités

L'application permet d'effectuer les opérations suivantes via le protocole SOAP :
*   **Afficher la liste des comptes** : Récupération et affichage de tous les comptes bancaires.
*   **Ajouter un compte** : Création d'un nouveau compte avec un solde initial et un type (Courant/Épargne).
*   **Supprimer un compte** : Suppression d'un compte existant (avec confirmation).
*   *Modifier un compte (Structure en place, implémentation future)*.

## 🛠 Technologies Utilisées

*   **Langage** : Kotlin
*   **Plateforme** : Android SDK (API 21+)
*   **Communication SOAP** : Librairie [ksoap2-android](https://github.com/simpligility/ksoap2-android) (v3.6.4)
*   **Interface Utilisateur** :
    *   Material Design Components
    *   RecyclerView & CardView
    *   ConstraintLayout
*   **Asynchronisme** : Kotlin Coroutines

## ⚙️ Configuration du Projet

### Prérequis
*   Android Studio Iguana ou supérieur.
*   JDK 17 ou supérieur (configuré pour le projet).
*   Un service web SOAP backend fonctionnel (ex: JAX-WS, Spring Boot SOAP).

### Configuration de l'Adresse IP
L'application est configurée pour fonctionner avec un émulateur Android accédant au `localhost` de la machine hôte.
Dans `Service.kt`, l'URL est définie ainsi :
```kotlin
private const val URL = "http://10.0.2.2:8082/services/ws"
```
*   `10.0.2.2` est l'alias spécial pour `localhost` depuis l'émulateur Android.
*   Si vous testez sur un appareil physique, remplacez cette IP par l'adresse IP locale de votre machine (ex: `192.168.x.x`).

### Build & Gradle
Le projet utilise les versions récentes des outils de build pour assurer la compatibilité avec Java 21 :
*   **Gradle Wrapper** : 8.10
*   **Android Gradle Plugin** : 8.2.0
*   **Kotlin** : 1.9.22
*   **JVM Target** : 1.8 (Compatible Java 17+)

## 🚀 Installation et Exécution

1.  Clonez ce dépôt :
    ```bash
    git clone https://github.com/ghassane04/TP-14-Client-Soap-Android-Kotlin-avec-KSOAP.git
    ```
2.  Ouvrez le projet dans **Android Studio**.
3.  Laissez Gradle synchroniser les dépendances (cela peut prendre quelques minutes).
4.  Assurez-vous que votre backend SOAP est démarré et accessible sur le port `8082`.
5.  Lancez l'application sur un émulateur ou un appareil connecté.

## 📱 Structure du Code

*   `beans/` : Classes de données (`Compte`, `TypeCompte`).
*   `ws/` : Gestion des appels réseau SOAP (`Service.kt`).
*   `adapter/` : Adaptateur pour la RecyclerView (`CompteAdapter`).
*   `MainActivity.kt` : Logique principale de l'interface et gestion des interactions.

---
**Auteur** : Ghassane