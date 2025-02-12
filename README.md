# Kong API Gateway integrado con Keycloak y ArgoCD

Este repositorio contiene la configuración de Kubernetes para desplegar:

- **Keycloak**: Servidor de autenticación (con configuración básica para demo).
- **Kong API Gateway**: En modo DB-less, utilizando un archivo declarativo que integra el plugin OIDC para autenticación con Keycloak.
- **ArgoCD**: Manifiesto de aplicación para sincronizar y desplegar automáticamente estos recursos en tu clúster.

## Estructura

- **argocd/kong-keycloak-app.yaml**: Manifiesto de ArgoCD para la sincronización de la aplicación.
- **keycloak/**: Manifiestos de despliegue y servicio para Keycloak.
- **kong/**: Manifiestos de despliegue y servicio para Kong, y la configuración declarativa (ConfigMap) que incluye la integración con Keycloak.

## Despliegue con ArgoCD

1. **Instala ArgoCD** en tu clúster y accede a su interfaz o CLI.
2. **Crea la aplicación** en ArgoCD usando el manifiesto ubicado en `argocd/kong-keycloak-app.yaml`.  
   > Si lo prefieres, puedes crear la aplicación desde la interfaz web de ArgoCD apuntando al repositorio y al path correspondiente.
3. **Sincroniza la aplicación** para que ArgoCD despliegue los recursos en el clúster.

## Consideraciones

- Revisa y actualiza las configuraciones (por ejemplo, URL de descubrimiento, credenciales, realm de Keycloak) según tus necesidades.
- Este ejemplo utiliza configuraciones simples para fines demostrativos.
