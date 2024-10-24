
# Terraform et Azure :
## Comment créer une ressource Azure avec Terraform ?
- Expliquez les étapes pour provisionner une ressource sur Azure en utilisant Terraform (écriture de fichiers `.tf`, utilisation des modules, initialisation de Terraform, et exécution de la commande `terraform apply`).
- Quelle est la structure de base d’un fichier de configuration Terraform pour créer une VM sur Azure ?
- Comment gérez-vous les variables d'environnement sensibles dans Terraform (par exemple, les credentials Azure) ?
- Comment utilisez-vous Terraform pour appliquer des modifications incrémentales à l'infrastructure Azure existante ?

## Comment gérez-vous les états dans Terraform ?
- Parlez de l'état Terraform et expliquez comment le gérer (fichier local ou distant via un backend comme Azure Blob Storage).
- Que faites-vous en cas de conflit d’état entre plusieurs utilisateurs ?

# Kubernetes :
## Comment vérifiez-vous les services dans Kubernetes ?
- Comment utiliser la commande `kubectl` pour lister les services disponibles dans un cluster Kubernetes (`kubectl get services`) ?
- Comment vérifiez-vous si un service Kubernetes est correctement exposé à l'extérieur du cluster (vérification du type de service, de l'IP et des ports) ?
- Expliquez l'interaction entre les services et les pods via des endpoints.

## Comment diagnostiquer et résoudre les problèmes dans un cluster Kubernetes ?
- Que faites-vous lorsque des pods ne se déploient pas correctement ?
- Comment utilisez-vous les logs des pods (`kubectl logs`) et les descripteurs d'objets Kubernetes (`kubectl describe`) pour diagnostiquer les problèmes ?

# Ansible et Terraform :
## Pourquoi avez-vous choisi Ansible plutôt que Terraform, ou inversement, dans un projet ?
- Quelles sont les différences fondamentales entre Ansible et Terraform en termes de cas d'utilisation (Ansible pour la configuration et l'automatisation des serveurs vs Terraform pour l'orchestration d'infrastructure) ?
- Quand choisiriez-vous d'utiliser Ansible plutôt que Terraform, ou l'inverse ?
- Pouvez-vous expliquer une situation où vous avez combiné l'utilisation d'Ansible et Terraform dans un projet ?

## Comment gérer les dépendances entre les tâches dans Ansible ?
- Expliquez comment vous gérez les rôles et les playbooks dans Ansible.
- Comment Ansible gère-t-il l'idempotence, et pourquoi est-ce important ?

# CI/CD et Kubernetes :
## Comment intégrer un pipeline CI/CD pour déployer une application sur Kubernetes ?
- Expliquez comment vous utilisez GitLab CI, Jenkins, ou un autre outil CI/CD pour automatiser le déploiement d'applications sur un cluster Kubernetes.
- Comment assurer la gestion des secrets dans un pipeline CI/CD pour Kubernetes (par exemple, en utilisant Vault ou Kubernetes Secrets) ?

# Azure (général) :
## Comment sécuriser les ressources dans Azure ?
- Comment utilisez-vous Azure RBAC (Role-Based Access Control) pour gérer les permissions ?
- Quelle est l'importance des Managed Identities pour les ressources dans Azure ?
- Pouvez-vous expliquer l'usage des policies dans Azure pour garantir la conformité ?

## Quels sont les services gérés dans Azure pour améliorer la scalabilité d'une application ?
- Expliquez comment vous pouvez utiliser Azure App Service, Azure Kubernetes Service (AKS), ou Azure Functions pour une architecture scalable.

# Certifications :
## KCNA (Kubernetes and Cloud Native Associate) :
- Pouvez-vous expliquer ce qu'est une architecture cloud native et comment Kubernetes s'intègre dans cette approche ?
- Comment gérez-vous les mises à jour de clusters Kubernetes dans un environnement de production tout en minimisant les interruptions de service ?

## Vault (HashiCorp Certified: Vault Associate) :
- Comment Vault gère-t-il les secrets dynamiques, et comment cela peut-il être utilisé dans un environnement multi-cloud ?
- Pouvez-vous expliquer comment configurer un backend de stockage pour Vault et gérer la haute disponibilité ?
- Quelles sont les bonnes pratiques pour sécuriser les accès à Vault dans un pipeline CI/CD ?

## Terraform (HashiCorp Certified: Terraform Associate) :
- Pouvez-vous décrire une infrastructure as code que vous avez mise en place avec Terraform ? Comment gérez-vous la modularité dans vos fichiers Terraform ?
- Comment gérez-vous les environnements de développement, de staging et de production avec Terraform ?

## CKAD (Certified Kubernetes Application Developer) :
- Pouvez-vous expliquer comment vous déployez une application en utilisant un Helm Chart dans Kubernetes ?
- Comment gérez-vous la persistance des données dans Kubernetes avec des PersistentVolumeClaims (PVC) ?

## AZ-104 (Microsoft Azure Administrator) :
- Quelles sont les meilleures pratiques pour configurer et gérer la sécurité réseau sur Azure ?
- Comment gérez-vous les identités et les accès dans Azure (par exemple, via Azure AD ou RBAC) ?

## AWS Certified Cloud Practitioner :
- Pouvez-vous expliquer les différences entre les services de stockage S3, EBS et EFS dans AWS ?
- Quels sont les outils et services AWS que vous utiliseriez pour surveiller et optimiser les coûts de votre infrastructure ?

# Expériences :
## SRE DevOps chez Numspot :
- Comment avez-vous intégré GitLab-CI pour automatiser les déploiements dans un contexte SRE ?
- Quelles sont les métriques que vous surveillez en priorité pour maintenir la fiabilité des systèmes ?

## Tech Lead chez TE46 :
- Comment avez-vous géré la coordination technique pour la synchronisation Cloud Azure ? Quels défis avez-vous rencontrés et comment les avez-vous résolus ?
- Comment assurez-vous la scalabilité et la résilience des infrastructures Cloud Azure ?

## DevOps chez BNP Paribas :
- Quelles méthodes avez-vous utilisées pour optimiser les pipelines CI/CD avec Jenkins ? Pouvez-vous partager un exemple de pipeline optimisé ?
- Comment gérez-vous la migration de systèmes vers le cloud dans un environnement hautement sécurisé tel que celui d'une banque ?

## Expérience avec Neocase Software :
- Pouvez-vous expliquer comment vous avez utilisé Ansible pour automatiser des processus ? Quels types de tâches avez-vous automatisé avec Ansible et Bash ?
- Comment avez-vous implémenté les bonnes pratiques de sécurité dans les déploiements Docker ?

# Outils DevOps :
## Jenkins :
- Comment configurez-vous un pipeline Jenkins pour intégrer des tests unitaires, des tests de sécurité (par exemple avec SonarQube), et des déploiements automatisés ?
- Comment gérez-vous les credentials dans un pipeline Jenkins tout en garantissant leur sécurité ?

## Kubernetes et Openshift :
- Quelles sont les différences majeures entre Kubernetes et Openshift ? Quand choisiriez-vous l’un plutôt que l’autre ?
- Comment configureriez-vous un cluster Kubernetes pour gérer des déploiements multi-régions ?

## SonarQube :
- Comment configurez-vous SonarQube pour effectuer des analyses automatiques sur le code dans un pipeline CI/CD ?
- Comment gérez-vous les violations de sécurité critiques détectées par SonarQube dans un projet en cours ?

# Méthodologies :
## Agile et SRE (Site Reliability Engineering) :
- Comment adaptez-vous les méthodologies Agile dans un environnement SRE ?
- Pouvez-vous expliquer comment vous gérez les incidents et les résolutions dans un environnement SRE avec des outils comme Kubernetes et Prometheus ?
