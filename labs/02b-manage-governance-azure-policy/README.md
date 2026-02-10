# Lab 02b - Manage Governance via Azure Policy

## Overview
In this lab, I implemented governance controls using **Azure Policy**, **resource tags**, and **resource locks** to enforce standards and protect resources.

## Objectives
- Apply tags to a resource group.
- Enforce tags using an Azure Policy assignment.
- Remediate non-compliant resources using a Modify policy.
- Configure and validate resource locks.

---

## Task 1: Create a resource group and assign tags
![01](./images/01_lab02b_create_rg_basics.png)
![02](./images/02_lab02b_create_rg_tags.png)
![03](./images/03_lab02b_resource_groups_list.png)

---

## Task 2: Enforce tagging with Azure Policy (Deny)
![04](./images/04_lab02b_policy_definitions_list.png)
![05](./images/05_lab02b_policy_definition_require_tag_filtered.png)
![06](./images/06_lab02b_assign_require_tag_scope_selector.png)
![07](./images/07_lab02b_assign_require_tag_scope_set.png)
![08](./images/08_lab02b_assign_require_tag_details.png)
![09](./images/09_lab02b_assign_require_tag_parameters.png)
![10](./images/10_lab02b_require_tag_assignment_created_success.png)
![11](./images/11_lab02b_storage_validation_error_requestdisallowedbypolicy.png)

---

## Task 3: Remediate tagging with Azure Policy (Modify / Inherit Tag)
![12](./images/12_lab02b_policy_tasks_list_require_cost_center.png)
![13](./images/13_lab02b_assign_inherit_tag_scope_selector.png)
![14](./images/14_lab02b_assign_inherit_tag_select_definition.png)
![15](./images/15_lab02b_assign_inherit_tag_parameters.png)
![16](./images/16_lab02b_assign_inherit_tag_remediation.png)
![17](./images/17_lab02b_policy_assignments_list_inherit_cost_center.png)
![18](./images/18_lab02b_storage_creation_validation_passed.png)
![19](./images/19_lab02b_storage_deployment_in_progress.png)
![20](./images/20_lab02b_storage_account_overview_created.png)
![21](./images/21_lab02b_storage_account_tags_cost_center_000.png)

---

## Task 4: Configure and test resource locks
![22](./images/22_lab02b_resource_group_locks_empty.png)
![23](./images/23_lab02b_add_lock_dialog_rg_lock_delete.png)
![24](./images/24_lab02b_lock_created_rg_lock.png)
![25](./images/25_lab02b_delete_rg_confirmation.png)
![26](./images/26_lab02b_delete_rg_error_locked.png)

---

## Key takeaways
- **Tags** help organize resources and improve reporting.
- **Azure Policy** enforces standards (Deny) and can remediate resources (Modify).
- **Remediation tasks** help bring existing resources into compliance.
- **Resource locks** prevent accidental deletion/modification.

## Cleanup

- [cleanup.md](./cleanup.md)
