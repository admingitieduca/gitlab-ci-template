# AUTODEPLOY

## Configuración YML

### App

copiar el archivo [.gitlab-ci.yml](https://gitlab.com/developers.ieduca/devops/gitlab-ci-template/-/raw/master/ejemplos/v1/contenedor/.gitlab-ci.yml)  en la raiz del repositorio

![image-20201016141530553](./imagenes/yml3.png)

modificar los tags con el nombre de los runners respectivos

![image-20201016142048997](./imagenes/yml4.png)

Las variables de QA se colocan en el before_script del job deploy_release

![image-20201016142728922](/persistence/repos/gitlab-ci-template/imagenes/image-20201016142728922.png)

Las variables de PRD se colocan en el before_script del job deploy_prod

![image-20201016142821916](./imagenes/image-20201016142821916.png)



> **No son necesarias las variables REGISTRY_IMAGE,IMAGE_VERSION y PROJECT_NAME en los exports.** 

Solo es necesario las variables que son usadas por el contenedor en el docker-composer.

### Composer

Copiar el archivo [.gitlab-ci.yml](https://gitlab.com/developers.ieduca/devops/gitlab-ci-template/-/raw/master/ejemplos/v1/composer/.gitlab-ci.yml)  en la raiz del repositorio

![image-20201016140829370](./imagenes/yml1.png)

modificar los tags con el nombre de los runners respectivos

![image-20201016141009953](./imagenes/yml2.png)



## Configuración de repositorio

### Environments

Crear 3 enviroments  master, SNAPSHOT y RELEASE

![image-20201016144538532](./imagenes/image-20201016144538532.png)

### Proteger Branchs

![image-20201016145144907](./imagenes/image-20201016145144907.png)

### Proteger Tags

![image-20201016154548871](./imagenes/image-20201016154548871.png)

### Variables

#### APP

Los repositorios de app deben configurarse  las variables COMPOSE_PATH y PROJECT_NAME

![image-20201016143858252](./imagenes/app-variables.png)

las variables adicionales se deben configurar de acuerdo a su ambiente  

![image-20201016144154889](./imagenes/image-20201016144154889.png)

Las variables que contienen información sensible se configuran en el grupo y solo lo puede hacer el administrador(owner)

![image-20201016144326896](./imagenes/image-20201016144326896.png)

#### Composer

Los repositorios composer deben tener la variable   COMPOSE_PATH de la carpeta donde estara el composer

![image-20201016130429808](./imagenes/composer-variables.png)

#### 



