# Cleanup — Lab 02b

## What I removed / reverted

- (Optional) Deleted the Storage Account created for testing (if not needed anymore)
- (Optional) Removed the Azure Policy assignments created in this lab:
  - Require Cost Center tag and its value on resources
  - Inherit the Cost Center tag and its value 000 from the resource group if missing
- (Optional) Removed the resource lock `rg-lock` from resource group `az104-rg2`
- Deleted the resource group `az104-rg2` (recommended to avoid costs)

## Cost check

- Verified no leftover resources generating cost in the subscription
