# Lab 04 - Manage Virtual Networking

Evidencias del laboratorio: creación y configuración de VMs y redes virtuales, reglas NSG, VNet peering, pruebas de conectividad y limpieza del Resource Group.

---

## 1) VM1 (creación) + troubleshooting
**Deployment en progreso**
![VM1 deployment in progress](screenshots/lab04_01_vm1_deployment_in_progress.png)

**Error en el deployment**
![VM1 deployment error](screenshots/lab04_02_vm1_deployment_error.png)

---

## 2) VM1 (eliminación) + limpieza del RG
**Eliminar VM1 (diálogo de borrado)**
![Delete VM1 dialog](screenshots/lab04_03_vm1_delete_dialog.png)

**Error al eliminar (AllocationFailed / recursos asociados)**
![Delete VM1 AllocationFailed](screenshots/lab04_04_vm1_delete_error_allocation_failed.png)

**Recursos en RG antes del cleanup**
![RG resources before cleanup](screenshots/lab04_05_rg4_resources_before_cleanup.png)

**RG después de borrar VM1 (recursos restantes)**
![RG resources after VM deleted](screenshots/lab04_06_rg4_resources_after_vm_deleted.png)

**RG con solo VNets**
![RG resources only VNets](screenshots/lab04_07_rg4_resources_only_vnets.png)

---

## 3) VM1 (Networking) en CoreServicesVnet
**Crear VM1 - Networking (CoreServicesVnet / SharedServicesSubnet)**
![VM1 networking CoreServices](screenshots/lab04_08_vm1_create_network_coreservices.png)

**Deployment completado**
![VM1 deployment completed](screenshots/lab04_09_vm1_deployment_completed.png)

**VM1 Overview**
![VM1 overview](screenshots/lab04_10_vm1_overview.png)

**VM1 - Network configuration**
![VM1 network configuration](screenshots/lab04_11_vm1_network_configuration.png)

**NSG inbound: RDP 3389 permitido**
![VM1 NSG inbound RDP](screenshots/lab04_12_vm1_nsg_inbound_rdp.png)

**RDP a VM1 (pantalla de primer login)**
![VM1 RDP first login](screenshots/lab04_13_vm1_rdp_first_login.png)

---

## 4) VM2 (sin IP pública) en ManufacturingVnet
**Crear VM2 - Networking (ManufacturingVnet / SensorSubnet1, Public IP: None)**
![VM2 networking Manufacturing](screenshots/lab04_14_vm2_create_network_manufacturing.png)

**VM2 Overview**
![VM2 overview](screenshots/lab04_15_vm2_overview.png)

**VM2 - Network configuration**
![VM2 network configuration](screenshots/lab04_16_vm2_network_configuration.png)

---

## 5) VNet Peering (CoreServicesVnet ↔ ManufacturingVnet)
**Formulario de peering (CoreServicesVnet → ManufacturingVnet)**
![Add peering form](screenshots/lab04_17_add_peering_form_core_to_manufacturing.png)

**Configuración remota (ManufacturingVnet)**
![Peering remote config](screenshots/lab04_18_peering_remote_configuration.png)

**Configuración local (CoreServicesVnet)**
![Peering local config](screenshots/lab04_19_peering_local_configuration.png)

**Peerings en CoreServicesVnet (Connected/Synced)**
![CoreServices peerings connected](screenshots/lab04_20_peerings_coreservices_connected.png)

**Peerings en ManufacturingVnet (Connected/Synced)**
![Manufacturing peerings connected](screenshots/lab04_21_peerings_manufacturing_connected.png)

---

## 6) Pruebas de conectividad y acceso (Nested RDP)
**Desde VM1: Test-NetConnection a VM2:3389 (Success)**
![Test-NetConnection to VM2 3389](screenshots/lab04_22_vm1_testnetconnection_to_vm2_3389.png)

**Nested RDP (VM1 → VM2)**
![Nested RDP VM1 to VM2](screenshots/lab04_23_nested_rdp_vm1_to_vm2.png)

**Dentro de VM2: ipconfig + hostname**
![VM2 ipconfig hostname](screenshots/lab04_24_vm2_ipconfig_hostname.png)

---

## 7) Cleanup final (borrar RG)
**Eliminando az104-rg4 (en progreso)**
![Delete RG in progress](screenshots/lab04_25_delete_rg4_in_progress.png)

**RG eliminado correctamente**
![RG deleted success](screenshots/lab04_26_rg4_deleted_success.png)
