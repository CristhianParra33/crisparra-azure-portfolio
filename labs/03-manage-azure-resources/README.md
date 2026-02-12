# Lab 03 - Manage Azure Resources (Portal + Cloud Shell: PowerShell, Azure CLI y Bicep)

## Objetivo
Practicar el despliegue de recursos en Azure usando:
- **ARM Template + PowerShell (Cloud Shell)**
- **ARM Template + Azure CLI (Cloud Shell Bash)**
- **Bicep + Azure CLI (Cloud Shell Bash)**

> **Resource Group:** `az104-rg3` (East US)

---

## Task 3 - Cloud Shell (PowerShell) + ARM Template
En esta tarea subí `template.json` y `parameters.json`, edité el parámetro del nombre del disco y desplegué el template con PowerShell.

**Comando usado:**
```powershell
New-AzResourceGroupDeployment `
  -ResourceGroupName az104-rg3 `
  -TemplateFile ./template.json `
  -TemplateParameterFile ./parameters.json
