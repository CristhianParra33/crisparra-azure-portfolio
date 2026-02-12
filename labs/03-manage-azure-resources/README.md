# Lab 03 - Manage Azure Resources using ARM Templates (PowerShell, Azure CLI y Bicep)

## Objetivo
En este laboratorio practiqué despliegues de infraestructura como código (IaC) usando:
- ARM Template + **Cloud Shell (PowerShell)**
- ARM Template + **Cloud Shell (Bash) con Azure CLI**
- **Bicep** + **Azure CLI**

> Resource Group: `az104-rg3`

---

## Task 3 - Cloud Shell (PowerShell) + ARM Template
En esta tarea validé el Resource Group, subí los archivos `template.json` y `parameters.json` a Cloud Shell, corregí el contexto de suscripción y ejecuté el despliegue con PowerShell para crear `az104-disk3`.

**Evidencias:**
![RG3 resources (disk1 & disk2)](./screenshots/02_RG3_resources_disk1_disk2.png)
![RG3 deployments list](./screenshots/03_RG3_deployments_list.png)
![Cloud Shell upload details](./screenshots/07_CloudShell_upload_details_parameters_template.png)
![parameters.json edited (disk3)](./screenshots/13_parameters_json_edited_disk3.png)
![New-AzResourceGroupDeployment succeeded (disk3)](./screenshots/19_New_AzResourceGroupDeployment_succeeded_disk3.png)
![Get-AzDisk (disk1 disk2 disk3)](./screenshots/20_Get_AzDisk_list_disks_1_2_3.png)

---

## Task 4 - Cloud Shell (Bash) + Azure CLI + ARM Template
En esta tarea edité `parameters.json` para crear `az104-disk4` y desplegué el template usando Azure CLI.

**Evidencias:**
![Bash started](./screenshots/01_Bash_shell_started.png)
![Bash pwd + ls (files present)](./screenshots/02_Bash_pwd_ls_files_present.png)
![parameters.json edited (disk4)](./screenshots/03_parameters_json_edited_disk4.png)
![az deployment group create output (part 1)](./screenshots/06_az_deployment_group_create_output_part1.png)
![az disk list (clean view, includes disk4)](./screenshots/10_az_disk_list_clean_view.png)

---

## Task 5 - Bicep + Azure CLI (Cloud Shell Bash)
En esta tarea subí `azuredeploydisk.bicep`, modifiqué parámetros para crear `az104-disk5` (32 GiB, StandardSSD_LRS) y desplegué con Azure CLI.

**Evidencias:**
![ls shows azuredeploydisk.bicep](./screenshots/01_ls_shows_azuredeploydisk_bicep.png)
![bicep open in editor](./screenshots/02_azuredeploydisk_bicep_open_in_editor.png)
![bicep edits (disk5 + size 32)](./screenshots/03_bicep_edits_managedDiskName_disk5_and_size32.png)
![bicep edits (sku StandardSSD_LRS)](./screenshots/04_bicep_edits_sku_StandardSSD_LRS.png)
![bicep deployment succeeded](./screenshots/05_bicep_deployment_output_succeeded.png)
![az disk list (includes disk5)](./screenshots/06_az_disk_list_with_disk5_StandardSSD_LRS.png)

---

## Cleanup (Importante)
Al finalizar el laboratorio, se recomienda eliminar el Resource Group para evitar costos.

![Delete RG confirmation](./screenshots/01_Delete_RG_confirmation.png)
