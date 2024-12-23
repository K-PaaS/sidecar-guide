### [Index](https://github.com/K-PaaS/Guide/blob/master/README.md) > [K-PaaS Sidecar Install](../README.md) > Sidecar Portal

## Table of Contents

1. [문서 개요](#1)  
  1.1. [목적](#1.1)  
  1.2. [범위](#1.2)  
  1.3. [참고자료](#1.3)  

2. [Portal 설치](#2)  
  2.1. [Prerequisite](#2.1)  
  2.2. [컨테이너 플랫폼 포털 리소스 배포](#2.2)  
  2.3. [Portal 배포](#2.3)  
  2.4. [Keycloak Redirect URL 설정](#2.4)  

# <div id='1'> 1. 문서 개요
## <div id='1.1'> 1.1. 목적
본 문서는 K-PaaS Sidecar(이하 Sidecar) 환경에서 Sidecar Portal을 설치하기 위한 가이드를 제공하는 데 목적이 있다.

<br>

## <div id='1.2'> 1.2. 범위
설치 범위는 Sidecar Portal을 검증하기 위한 Portal 배포를 기준으로 작성하였다.  

<br>


## <div id='1.3'> 1.3. 참고자료
Paketo Buildpack Github : [https://github.com/paketo-buildpacks](https://github.com/paketo-buildpacks)  
Paketo Buildpack Document : [https://paketo.io/docs/](https://paketo.io/docs/)  
K-PaaS 컨테이너 플랫폼 : [https://github.com/K-PaaS/container-platform](https://github.com/K-PaaS/container-platform)  

<br>


# <div id='2'> 2. Portal 설치
## <div id='2.1'> 2.1. Prerequisite
본 설치 가이드는 컨테이너 플랫폼 포털 리소스를 일부 사용하여 Sidecar에 Portal 배포를 진행한다.  

사용하는 리소스는 다음과 같다.

- cp-portal-common-api
- cp-portal-metric-api
- cp-harbor
- cp-keycloak
- cp-mariadb
- cp-vault

<br>

## <div id='2.2'> 2.2. 컨테이너 플랫폼 포털 리소스 배포  
Sidecar Portal 배포에 필요한 컨테이너 플랫폼 포털 리소스를 배포한다.
컨테이너 플랫폼 포털 리소스가 이미 배포 되있을 경우 해당 과정을 생략한다.
- INGRESS_HOST_DOMAIN 값 설정 ({ingress-nginx-controller 서비스의 EXTERNAL-IP}.nip.io)
```diff
$ cd $HOME/sidecar-deployment/install-scripts/portal
$ vi deploy-cp-portal-infra.sh

#!/bin/bash

#VARIABLES
+INGRESS_HOST_DOMAIN="{host domain}"    # Host Domain (e.g. xx.xxx.xxx.xx.nip.io)

CP_PORTAL_VERSION=v1.5.2

# SCRIPT START

......................
......................




$ chmod +x deploy-cp-portal-infra.sh 
$ ./deploy-cp-portal-infra.sh
```


## <div id='2.3'> 2.3. Portal 배포   
Sidecar 환경에 Portal을 배포한다 (환경에 맞춰 CUSTOM VARIABLES 변경)
```
$ cd $HOME/sidecar-deployment/install-scripts/portal
$ vi portal-deploy-variables.yml


# CUSTOM VARIABLES
HELM_CP_PORTAL_NAMESPACE=cp-portal
HELM_CP_PORTAL_RESOURCE_NAME=cp-portal
HELM_SIDECAR_NAMESPACE=sidecar
HELM_SIDECAR_NAME=sidecar
TARGET_CLUSTER=host-cluster #check cp-portal-deployment/script/cp-portal-vars.sh HOST_CLUSTER_NAME
K8S_CLUSTER_ADMIN_NAMESPACE=kube-system #check cp-portal-deployment/script/cp-portal-vars.sh K8S_CLUSTER_ADMIN_NAMESPACE
K8S_CLUSTER_ADMIN=cp-cluster-admin #check cp-portal-deployment/script/cp-portal-vars.sh K8S_CLUSTER_ADMIN
ORG_NAME=system
SPACE_NAME=portal
SIDECAR_ADMIN_KUBECONFIG=$(pwd)/../support-files/user/sidecar-sidecar-admin.ua.kubeconfig
PORTAL_API_NAME=sidecar-portal-api
PORTAL_UI_NAME=sidecar-portal-ui
CP_PORTAL_ADMIN_NAME=cp-cluster-admin #check cp-portal-deployment/script/cp-portal-vars.sh K8S_CLUSTER_ADMIN



$ chmod +x deploy-portal.sh
$ ./deploy-portal.sh


......................
......................

Getting apps in org system / space portal as sidecar-admin...

name                 requested state   processes                               routes
sidecar-portal-api   started           web:3/3, executable-jar:0/0, task:0/0   sidecar-portal-api.apps.k-paas.kr
sidecar-portal-ui    started           web:1/1, executable-jar:0/0, task:0/0   sidecar-portal-ui.apps.k-paas.kr
```

## <div id='2.4'> 2.4. Keycloak Redirect URL 설정  
- Sidecar Portal로 접근하기 위하여 Keycloak Redirect URL 설정을 진행해야 한다.
```
# keycloak 주소 확인
$ kubectl get ing -n keycloak
NAME                  CLASS   HOSTS                            ADDRESS       PORTS   AGE
cp-keycloak-ingress   nginx   keycloak.k-paas.kr               10.0.12.150   80      28d
```
- 접속 후 Administration Console을 접근하여 로그인을 진행한다. 
- 로그인과 관련된 정보는 다음 [링크](https://github.com/K-PaaS/container-platform/blob/master/install-guide/portal/cp-portal-standalone-guide.md#-key-%EC%BB%A8%ED%85%8C%EC%9D%B4%EB%84%88-%ED%94%8C%EB%9E%AB%ED%8F%BC-%ED%8F%AC%ED%84%B8-%EA%B4%80%EB%A6%AC%EC%9E%90-%EA%B3%84%EC%A0%95-%ED%8C%A8%EC%8A%A4%EC%9B%8C%EB%93%9C-%EC%84%A4%EC%A0%95-)를 확인한다.

![2-4-1]

- 좌측 상단의 Master를 클릭하여 Cp-realm으로 변경을 진행한다.

![2-4-2]

- Clients - cp-client를 클릭한다.

![2-4-3]

- Access settings - Valid redirect URIs에 sidecar-portal-ui의 주소를 다음과 같은 형식으로 추가한 뒤 저장한다.  
  예시) http://sidecar-portal-ui.apps.k-paas.kr/*

![2-4-4]

- 이후 sidecar-portal-ui의 route인 http://sidecar-portal-ui.apps.k-paas.kr 로 접속을 시도한다.


### <div id='2.4.1'> ※ (참고) Sidecar Portal 삭제
```
$ chmod +x delete-portal.sh
$ ./delete-portal.sh
```

### <div id='2.4.2'> ※ (참고) Sidecar Dependency 삭제 (Sidecar 삭제 후)
```
$ cd $HOME/sidecar-deployment/install-scripts/portal/cp-portal-deployment/script
$ chmod +x uninstall-cp-portal.sh
$ ./uninstall-cp-portal.sh
```

----
[2-4-1]:../images/portal/2-4-1.jpeg
[2-4-2]:../images/portal/2-4-2.jpeg
[2-4-3]:../images/portal/2-4-3.jpeg
[2-4-4]:../images/portal/2-4-4.jpeg

### [Index](https://github.com/K-PaaS/Guide/blob/master/README.md) > [K-PaaS Sidecar Install](../README.md) > Sidecar Portal
