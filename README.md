# Evaluación 1: Sistemas Operativos (Cliente y Servidor)

**Instituto Universitario de Tecnología de Administración Industrial (IUTA)**  
**Especialidad:** Informática  
**Sección:** 285A1  
**Unidad Curricular:** Electiva  
**Profesor:** Hisiu Díaz  
**Estudiante:** Nomar Nuñez  

---

## 1. Tema Seleccionado
**Sistemas Operativos (Cliente y Servidor):** Implementación de una arquitectura de red Cliente-Servidor mediante la configuración de un Servidor de Autenticación, Gestión de Recursos (Active Directory / LDAP / DHCP / DNS) y Clientes de Red.

---

## 2. Informe Técnico: Impacto y Utilidad

Los sistemas operativos son el núcleo que permite gestionar los recursos de hardware y software en cualquier arquitectura de red. La evolución tecnológica ha impulsado una clara separación entre los **Sistemas Operativos Cliente** (enfocados en la interacción fluida del usuario final, interfaces gráficas intuitivas y ejecución de aplicaciones de escritorio) y los **Sistemas Operativos Servidor** (diseñados para garantizar alta disponibilidad, procesamiento masivo de solicitudes, estabilidad y administración centralizada de la seguridad).

La implementación de estas arquitecturas cliente-servidor representa el estándar de la industria para garantizar la disponibilidad, el control de accesos y la escalabilidad de los servicios informáticos dentro de las organizaciones.

Desde mi perspectiva, la importancia de esta arquitectura radica en su capacidad para descentralizar el procesamiento mientras se centraliza la administración y la seguridad. Al utilizar un sistema operativo servidor junto con clientes de red, se logra un ecosistema altamente eficiente. El servidor se encarga de gestionar la autenticación de usuarios, la asignación dinámica de direcciones IP (DHCP), la resolución de nombres (DNS) y el almacenamiento centralizado, permitiendo que las estaciones cliente ejecuten sus tareas sin comprometer los datos críticos de la empresa.

---

## 3. Diagrama de Flujo del Proceso de Implementación

![Diagrama de Flujo](./diagrama.png)

```mermaid
graph TD
    A([Inicio: Configuración del Entorno]) --> B[1. Instalación del SO Servidor]
    B --> C[2. Asignación de IP Estática, Máscara y Gateway]
    C --> D[3. Configuración de Servicios: Active Directory, DHCP y DNS]
    D --> E[4. Instalación y Configuración del SO Cliente]
    E --> F[5. Configuración de Red Cliente via DHCP]
    F --> G[6. Solicitar Autenticación / Unión al Dominio]
    
    G --> H{¿Autenticación y Red Válidas?}
    
    H -- SÍ --> I[7. Conexión Establecida: Aplicar Políticas y Acceso a Recursos]
    H -- NO --> J[8. Diagnóstico de Red: Revisar Ping, DNS y Firewall]
    
    J --> F
    I --> K([Fin del Proceso])
