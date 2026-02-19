# Extra Lab - Linux VM + Nginx + Azure Monitor + Alertas (AZ-104)

> Portal de Azure en **español** | Nivel: Intermedio | Enfoque: VM + Red (NSG) + Monitorización + Alertas + Cleanup

---

## Índice
- [Objetivo](#objetivo)
- [Arquitectura](#arquitectura)
- [Prerequisitos](#prerequisitos)
- [Laboratorio paso a paso](#laboratorio-paso-a-paso)
  - [1) Crear VM Linux (Ubuntu)](#1-crear-vm-linux-ubuntu)
  - [2) Configurar NSG para HTTP (puerto 80)](#2-configurar-nsg-para-http-puerto-80)
  - [3) Conectarse por SSH e instalar Nginx](#3-conectarse-por-ssh-e-instalar-nginx)
  - [4) Validar Nginx desde navegador](#4-validar-nginx-desde-navegador)
  - [5) Monitoreo básico en la VM con htop](#5-monitoreo-básico-en-la-vm-con-htop)
  - [6) Revisar Azure Advisor](#6-revisar-azure-advisor)
  - [7) Azure Monitor: Métricas](#7-azure-monitor-métricas)
  - [8) Azure Monitor: Crear alerta por CPU](#8-azure-monitor-crear-alerta-por-cpu)
  - [9) Cleanup: Eliminar el grupo de recursos](#9-cleanup-eliminar-el-grupo-de-recursos)
- [Troubleshooting rápido](#troubleshooting-rápido)
- [Aprendizajes clave](#aprendizajes-clave)

---

## Objetivo

Desplegar una **máquina virtual Linux (Ubuntu)** en Azure, publicar un servicio web con **Nginx**, abrir acceso HTTP mediante **NSG**, y habilitar observabilidad con **Azure Monitor** (métricas y alertas), además de revisar recomendaciones en **Azure Advisor** y finalizar con **cleanup**.

---

## Arquitectura

**Recursos y componentes**
- Resource Group
- Virtual Machine (Ubuntu 24.04 LTS)
- Network Security Group (NSG)
- Nginx (servidor web)
- Azure Advisor
- Azure Monitor (Métricas)
- Azure Alerts (regla CPU)

---

## Prerequisitos

- Suscripción de Azure (ej. “Suscripción Prueba”)
- Acceso al portal de Azure en español
- Cliente SSH (PowerShell, Terminal, VSCode o Cloud Shell)
- Clave privada SSH descargada al crear la VM

> ⚠️ Buenas prácticas: al terminar, **elimina el grupo de recursos** para evitar costos.

---

# Laboratorio paso a paso

## 1) Crear VM Linux (Ubuntu)

1. En el portal: **Crear un recurso** → **Máquina virtual**
2. Selecciona:
   - **Suscripción**: tu suscripción de prueba
   - **Grupo de recursos**: el de este lab
   - **Nombre**: `MaquinaVirtuallab1`
   - **Región**: `México Central`
   - **Imagen**: `Ubuntu Server 24.04 LTS - Gen2`
   - **Autenticación**: `Clave pública SSH`
   - **Puertos de entrada**: `SSH (22)` permitido
3. **Revisar y crear** → **Crear**
4. Descarga la clave privada cuando el portal la ofrezca.

📸 **Captura**
- Resumen “Revisar y crear” de la VM:

![VM - Review + Create](images/01_ReviewCreate_VM_Summary.png)

---

## 2) Configurar NSG para HTTP (puerto 80)

Objetivo: permitir que el navegador llegue a Nginx usando **HTTP (80/TCP)**.

1. En la VM: **Redes** → **Reglas de puerto de entrada**
2. Crea una regla (ACL del puerto) para **TCP/80**:
   - **Puerto de destino**: `80`
   - **Protocolo**: `TCP`
   - **Acción**: `Permitir`
   - **Nombre**: por ejemplo `accesohttp` o `AccesoHTTP`
   - **Prioridad**: una libre (ej. 310)

📸 **Capturas**
- Vista general de reglas de red / NSG asociado:

![NSG Overview](images/02_VM_Networking_Rules_Overview.png)

- Formulario agregando la regla de entrada para HTTP:

![Add Inbound Rule](images/03_Add_Inbound_SecurityRule_HTTP80.png)

- Regla creada en la lista:

![Inbound Rule Created](images/04_Inbound_Rule_HTTP80_Created.png)

---

## 3) Conectarse por SSH e instalar Nginx

### 3.1 Conexión SSH desde PowerShell (ejemplo)
En el portal: **Conectar** → **SSH nativo** → copia el comando.

Ejemplo (ajusta ruta de tu .pem y la IP):
```bash
ssh -i C:\Users\TU_USUARIO\Downloads\TU_CLAVE.pem azureuser@TU_IP_PUBLICA
