# Comandos Frecuentes de Minikube

## Operaciones Básicas

### Inicio y Detención

```bash
# Iniciar cluster de Minikube
minikube start

# Detener cluster
minikube stop

# Eliminar cluster
minikube delete - p nombre-cluster

# Verificar estado de Minikube
minikube status
```

### Gestión del Cluster

```bash
# Obtener la IP del cluster
minikube ip

# Conocer en que nodo estoy trabajando (default)
minikube profile
minikube profile list

# Abrir el dashboard de Kubernetes
minikube dashboard

# Obtener la URL del dashboard
minikube dashboard --url
```

## Gestión de Recursos

```bash
# Ver logs de Minikube
minikube logs

# Acceder mediante SSH al nodo de Minikube
minikube ssh

# Verificar la configuración del cluster
minikube config view

# Conocer memoria y CPU del nodo
minikube config get memory
minikube config get cpus

# Aumentar recursos (CPU/memoria) del cluster
minikube config set memory 4096
minikube config set cpus 2
```

## Solución de Problemas

```bash
# Reiniciar cluster
minikube start --force

# Verificar componentes del cluster
minikube kubectl -- get componentstatuses

# Actualizar Minikube a la última versión
minikube update-check

# Limpiar recursos locales
minikube delete --all --purge
```

## Integración con kubectl

```bash
# Usar kubectl con Minikube
minikube kubectl -- get pods
minikube kubectl -- get nodes
minikube kubectl -- get services

# Cambiar el contexto a Minikube
kubectl config use-context minikube
```

## Gestión de Nodos Multi-cluster

```bash
# Crear cluster con múltiples nodos
minikube start --nodes 3 --kubernetes-version=latest  # Crear cluster con 3 nodos

# Gestión de nodos
minikube node add                                     # Agregar un nodo adicional
minikube node list                                   # Listar todos los nodos
minikube node delete nombre-cluster                     # Eliminar un nodo específico

# Configuración de recursos por nodo
minikube start --nodes 2 --cpus=2 --memory=2048mb    # 2 nodos con 2 CPUs y 2GB RAM cada uno

# Acceder a un nodo específico
minikube ssh --node nombre-cluster                      # SSH a un nodo específico
minikube node start nombre-cluster                      # Iniciar un nodo específico
minikube node stop nombre-cluster                       # Detener un nodo específico
```
