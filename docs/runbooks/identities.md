# Identities and naming register

| Object | Name | Purpose |
|---|---|---|
| Resource group | rg-bank-lh-dev | All lab resources (Southeast Asia) |
| Storage account | stgbanklhdev0609 | ADLS Gen2: landing, raw-archive, lakehouse |
| Access connector | aconn-bank-lh-dev | Managed identity Databricks uses for storage |
| Storage credential | cred_bank_lh_dev | Unity Catalog handle on the access connector |
| External locations | el_landing, el_raw_archive, el_lakehouse | Approved storage paths |
| Catalog | bank_dev | Dev environment catalog |
| Owner group | grpdb-bank-lhouse-admins | Owns catalog, credential, external locations |
| Job identity | sp-bank-lh-jobs (Databricks-managed) | Run-as identity for all jobs |

## Human identities (roles only; real names kept locally)
- Azure platform identity: subscription Owner; portal and AzCopy
- Data platform identity: Databricks account admin; daily work
- Break-glass identity: Entra Global Admin; MFA; emergencies only
