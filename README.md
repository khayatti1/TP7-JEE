# TP7– Communication entre microservices avec Spring Cloud OpenFeign

## Description

Ce TP met en œuvre la **communication inter-microservices** à l’aide de **Spring Cloud OpenFeign**.
Une application **MCommerce** est composée de plusieurs microservices indépendants, orchestrés par un **microservice Client** jouant le rôle de **point d’entrée unique**.

OpenFeign permet de **simplifier les appels REST** entre microservices grâce à une approche déclarative.

## Architecture

L’application est composée de **4 microservices** :

1. **Microservice Client (ClientUI)**

   * Interface utilisateur
   * Orchestration des appels
   * Port : 8080

2. **Microservice Produits**

   * Gestion des produits
   * Port : 9001

3. **Microservice Commandes**

   * Gestion des commandes
   * Port : 9002

4. **Microservice Paiement**

   * Gestion des paiements
   * Port : 9003

Chaque microservice dispose de sa **base H2** et expose ses propres **API REST**.

## Fonctionnalités

* Communication REST entre microservices
* Appels HTTP simplifiés avec OpenFeign
* Orchestration centralisée via le microservice Client
* Séparation claire des responsabilités
* Application distribuée cohérente

## Annotations clés

* `@EnableFeignClients` : activation des clients Feign
* `@FeignClient` : déclaration d’un client REST
* `@SpringBootApplication` : démarrage des microservices

## Endpoints principaux

* Microservice Produits :

  ```
  GET /Produits
  GET /Produits/{id}
  ```
* Application Client :

  ```
  http://localhost:8080/
  ```

## Exécution

### Ordre de démarrage

```bash
# Microservice Produits
mvn spring-boot:run -pl microservice-produits

# Microservice Commandes
mvn spring-boot:run -pl microservice-commandes

# Microservice Paiement
mvn spring-boot:run -pl microservice-paiement

# Microservice Client
mvn spring-boot:run -pl client-ui
```

## Vérifications

* Accéder à l’application Client :

  ```
  http://localhost:8080/
  ```
* Consulter les produits
* Passer une commande
* Simuler un paiement
* Vérifier les données via les consoles H2

## Screen

![1](https://github.com/user-attachments/assets/196567cb-1010-466f-a132-4a3fe5861b05)
![2](https://github.com/user-attachments/assets/916937ff-9077-40b7-833d-83ecdac04c1d)
![3](https://github.com/user-attachments/assets/1f1182b1-be7b-4288-a7c3-3056da865b54)
![4](https://github.com/user-attachments/assets/e9113ec9-4dc3-4175-bc10-0e3812a39adc)
![5](https://github.com/user-attachments/assets/a58c18f5-5e37-4c4d-81b7-c32837c958c6)
![7](https://github.com/user-attachments/assets/093b279d-3b29-4c1f-b37a-c308e59d95b8)
![8](https://github.com/user-attachments/assets/2873d357-bc5d-44e5-a58b-e0e5a4683c14)
![9](https://github.com/user-attachments/assets/e3a3a5d2-b26f-4851-8a36-8777f1f2750f)
![10](https://github.com/user-attachments/assets/f893d47c-fe0b-4757-ad09-efb9de8bf38f)
![11](https://github.com/user-attachments/assets/4068c7b6-13f7-4368-bbfc-3930d242f283)

## Objectifs pédagogiques

* Comprendre la communication entre microservices
* Utiliser OpenFeign pour les appels REST
* Orchestrer des services distribués
* Construire une application microservices complète
* Améliorer la lisibilité et la maintenance du code

---

**MOHAMMED EL KHAYATI & MOUAD MOUDID --5IIR-11**

Si tu veux, je peux maintenant te livrer **un README final global regroupant tous les TPs (TP1 → TP OpenFeign)** prêt à être déposé sur **GitHub ou Moodle**, avec une présentation homogène.
