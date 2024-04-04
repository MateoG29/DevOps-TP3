# DevOps-TP3
Infrastructure As Code avec Terraform

## Contenu

1. [Introduction](#introduction)
2. [Prérequis](#prérequis)
3. [Azure CLI](#azure-cli)
4. [Terraform](#terraform)
5. [Suppression](#suppression)

## Introduction

Ce projet permet de créer avec Terraform une Infrastructure as Code.

## Prérequis

- Ubuntu 22.04
- Terraform
- Azure CLI

## Azure CLI

1. Se connecter à son compte azure : ```az login --use-device-code```
2. Récupérer son subscriptionId : ```az account list --query "[].{name:name, subscriptionId:id}"```
3. Créer un service : ```az ad sp create-for-rbac --role="Contributor" --scopes="/subscriptions/votreSubscriptionID"```
4. Exporter les résultats dans des variables :
   - ```export ARM_SUBSCRIPTION_ID=<votreSubscriptionId>```
   - ```export ARM_CLIENT_ID=<votreappID>```
   - ```export ARM_CLIENT_SECRET=<votrePassword>```
   - ```export ARM_TENANT_ID=<votreTenant>```

## Terraform
1. Créer un dossier terraform, assurez-vous d'être dans ce dossier pour le reste des manipulations.
2. Récupérer les fichiers :
   - ```main.tf``` : Créer un ressource group
   - ```sa.tf``` : Créer un storage account
   - ```vm.tf``` : Créer une machine virtuelle
   - ```versions.tf``` : Stipule l'image de la vm
3. Créer une clé publique SSH dans : ```ssh-keygen -t rsa```
4. Initialiser le dossier : ```terraform init```
5. Valider la configuration : ```terraform validate```
6. Afficher le plan d'exécution : ```terraform plan```
7. Appliquer la configuration : ```terraform apply```

## Suppression
Si vous souhaitez supprimer votre Infrastructure : ```terraform destroy```
