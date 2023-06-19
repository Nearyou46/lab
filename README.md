# lab
Kubernetes
Метою даного проекту є вивчення основних складових k8s таких як:
pod, deployments, DaemonSets, StatefulSets, replicaSets, Jobs, CronJobs, ConfigMaps, Secrets, ResourseQuotas, LimitRanges, HPA, PDB, PriorityClases, 
Services, Endpoints, Ingresses, NP, PV, PVC, StorageClasses, Roles, ClusterRoles, RoleBinding, ClusterRoleBinding. 
Та взаємодія між kubernetes та HELM. 
Для набуття та покращення практичних навичок було вибрано проходження сертифікації від Linux Fondation за напрямком CKA (certified-kubernetes-administrator).
В цьому курсі використовувались наступні середовища для навчання. remote(GCP k8s cluster) та local(minikube(VirtualBox)).
Було протестовану роботу вищезгаданих ресурсів та їх розгортання з *.yaml файлів до прикладу найпростіший conf file for pod with nginx container.
---
apiVersion: v1
kind: Pod
metadata:
  name: nginx
spec:
  containers:
  - name: nginx
    image: nginx:1.14.2
    ports:
    - containerPort: 80
---
Та деплойменту
---
-
apiVersion: apps/v1
kind: Deployment
metadata:
  name: nginx-deployment
  labels:
    app: nginx
spec:
  replicas: 3
  selector:
    matchLabels:
      app: nginx
  template:
    metadata:
      labels:
        app: nginx
    spec:
      containers:
      - name: nginx
        image: nginx:1.14.2
        ports:
        - containerPort: 80

        
Було досліджено як можна керувати K8s інфраструктурою, оновлювати K8s cluster та робити бекап ETCD.
Після 60 днів курсу було пройдено екзамен та отримано сертифікат про відповідність знаннь.

