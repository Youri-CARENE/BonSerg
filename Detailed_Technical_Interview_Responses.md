
# Terraform et Azure :
## Comment créer une ressource Azure avec Terraform ?
Créer un fichier `.tf` avec la configuration de la ressource, initialiser Terraform avec `terraform init`, utiliser `terraform plan` pour vérifier les changements, puis exécuter `terraform apply`. Par exemple, pour créer une machine virtuelle sur Azure, j’ai utilisé `resource "azurerm_virtual_machine"`, et défini des paramètres tels que l'image de l'OS et la taille de la VM.

## Quelle est la structure de base d’un fichier de configuration Terraform pour une VM Azure ?
La configuration de base inclut un `provider "azurerm"` pour se connecter à Azure, un `resource "azurerm_virtual_network"` pour le réseau, et `resource "azurerm_virtual_machine"` pour définir la VM. J'ai également utilisé des variables pour rendre la configuration modulaire et adaptable à différents environnements.

## Comment gérez-vous les variables sensibles dans Terraform ?
J'utilise un fichier `terraform.tfvars` pour stocker les variables sensibles, mais dans les projets critiques, je les stocke dans un outil de gestion de secrets tel que HashiCorp Vault ou Azure Key Vault pour éviter qu’elles ne soient versionnées accidentellement dans le dépôt Git.

## Comment utilisez-vous Terraform pour appliquer des modifications incrémentales à l'infrastructure Azure existante ?
Après avoir apporté des modifications au fichier `.tf`, j’utilise `terraform plan` pour visualiser les changements avant de les appliquer avec `terraform apply`. Cela permet de vérifier que seules les ressources modifiées sont impactées. Par exemple, lors de la mise à jour d'une VM, seule sa configuration réseau a été modifiée sans affecter les autres ressources.

## Comment gérez-vous les états dans Terraform ?
Dans un projet multi-utilisateur, j'ai utilisé un backend distant comme Azure Blob Storage pour centraliser et sécuriser l'état Terraform. J'ai également mis en place des verrous (`lock`) pour empêcher des utilisateurs multiples de modifier l'état simultanément.

## Que faites-vous en cas de conflit d’état entre plusieurs utilisateurs ?
En cas de conflit, j’analyse l'état pour identifier les changements en conflit, puis je décide s'il faut appliquer ou rejeter certaines modifications. J’utilise également `terraform refresh` pour synchroniser l'état local avec les ressources réelles.

# Kubernetes :
## Comment vérifiez-vous les services dans Kubernetes ?
J'utilise `kubectl get services` pour lister les services actifs dans le cluster et `kubectl describe service` pour obtenir des détails supplémentaires. En production, j'ai également utilisé Prometheus et Grafana pour surveiller les services et leur performance.

## Comment vérifier si un service est exposé correctement ?
J'utilise `kubectl describe service` pour vérifier le type de service (ClusterIP, NodePort, LoadBalancer) et m'assurer que les ports et IP sont configurés correctement. Lors de la configuration d’un service LoadBalancer pour une application web, j'ai vérifié que l'IP externe assignée par le cloud provider était accessible.

## Expliquez l'interaction entre les services et les pods via des endpoints.
Un service Kubernetes utilise les endpoints pour rediriger le trafic vers les pods associés. Lors de la création d'un service pour une application, je vérifie que les endpoints sont correctement liés aux pods actifs avec `kubectl get endpoints`.

## Que faites-vous lorsque des pods ne se déploient pas correctement ?
Je commence par utiliser `kubectl logs` pour analyser les journaux des pods, et `kubectl describe pod` pour vérifier les événements ou erreurs. Dans un cas, les erreurs venaient d’une image corrompue, donc j’ai mis à jour l'image et relancé le déploiement.

# Ansible et Terraform :
## Pourquoi avez-vous choisi Ansible plutôt que Terraform, ou inversement, dans un projet ?
J'ai utilisé Terraform pour provisionner l'infrastructure cloud (comme la création de VMs sur Azure) et Ansible pour automatiser les configurations à l'intérieur des VMs (par exemple, l'installation de packages). Terraform est plus adapté pour gérer les ressources en cloud tandis qu’Ansible est utile pour les tâches de configuration.

## Quand utiliseriez-vous Ansible plutôt que Terraform, ou l'inverse ?
J’utilise Terraform lorsque je dois gérer l’infrastructure (création de réseaux, VMs, load balancers) et Ansible pour gérer les configurations au niveau des serveurs (gestion des utilisateurs, déploiement d’applications).

## Avez-vous combiné Ansible et Terraform dans un projet ?
Oui, dans un projet de déploiement de microservices, j'ai utilisé Terraform pour créer l'infrastructure sur Azure et Ansible pour configurer les serveurs et déployer les applications Docker sur ces machines.

## Comment gérer les dépendances entre les tâches dans Ansible ?
J'utilise les rôles et les `handlers` dans Ansible pour gérer les dépendances entre les tâches. Par exemple, une tâche de redémarrage de service est déclenchée seulement après que la configuration du service ait été modifiée.

## Comment Ansible gère-t-il l'idempotence, et pourquoi est-ce important ?
Ansible garantit que chaque tâche est exécutée de manière idempotente, c’est-à-dire qu’elle ne modifie l'état d’un serveur que si nécessaire. Cela est important pour éviter des modifications inutiles et préserver la stabilité du système.

# CI/CD et Kubernetes :
## Comment intégrer un pipeline CI/CD pour déployer une application sur Kubernetes ?
J'ai utilisé GitLab CI pour créer un pipeline qui compile et teste une application, puis construit une image Docker avant de la déployer sur Kubernetes avec `kubectl`. J'ai également configuré Helm pour gérer les versions d’applications et simplifier le processus de déploiement.

## Comment assurer la gestion des secrets dans un pipeline CI/CD pour Kubernetes ?
J'ai utilisé Kubernetes Secrets pour stocker les informations sensibles comme les tokens d'API, et intégré HashiCorp Vault pour centraliser et gérer dynamiquement les secrets dans le pipeline CI/CD.

# Azure :
## Comment sécuriser les ressources dans Azure ?
J’utilise Azure RBAC pour définir des rôles précis pour chaque utilisateur, limitant ainsi l’accès aux ressources critiques. Par exemple, seuls les administrateurs réseau ont des autorisations pour configurer les pare-feux.

## Quelle est l'importance des Managed Identities pour les ressources dans Azure ?
Les Managed Identities permettent à une ressource Azure (comme une VM ou une fonction) d'accéder à d'autres ressources sans avoir à gérer des credentials manuellement. Cela élimine le besoin de stocker des secrets dans les configurations et améliore la sécurité.

## Comment utiliser les policies dans Azure pour garantir la conformité ?
J’ai utilisé des Azure Policies pour appliquer des règles de sécurité, par exemple interdire la création de ressources publiques non sécurisées ou forcer l'utilisation du chiffrement pour le stockage.

## Quels services Azure pour améliorer la scalabilité ?
J’ai utilisé Azure App Service pour déployer des applications web évolutives et Azure Kubernetes Service (AKS) pour orchestrer des conteneurs à grande échelle. Azure Functions est également utile pour les architectures serverless qui scalent automatiquement.

# Certifications :
## Pouvez-vous expliquer l'architecture cloud native ?
Une architecture cloud native est basée sur des conteneurs, des microservices, et des services managés. Kubernetes joue un rôle clé en orchestrant ces conteneurs pour permettre des déploiements flexibles et scalables dans le cloud.

## Comment gérer les mises à jour de clusters Kubernetes dans un environnement de production ?
J'ai utilisé des stratégies de rolling updates pour minimiser les interruptions en mettant à jour progressivement les pods. Cela permet de maintenir le service actif tout en déployant de nouvelles versions.

# Expériences :
## Comment avez-vous intégré GitLab-CI pour automatiser les déploiements SRE ?
J'ai créé des pipelines CI/CD avec GitLab-CI pour automatiser le déploiement de microservices, incluant des étapes de tests, de packaging Docker et de déploiement sur Kubernetes. Cela a réduit les délais de mise en production.

## Quelles sont les métriques que vous surveillez en priorité en SRE ?
J'ai utilisé Prometheus pour surveiller des métriques telles que la latence des services, le taux d'erreurs et l’utilisation des ressources, afin de garantir des SLA stricts.
