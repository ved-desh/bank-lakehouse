# End-of-day shutdown checklist (serverless workspace)

- [ ] Notebooks detached from serverless compute
- [ ] SQL Warehouses: none running (2X-Small, shortest auto-stop)
- [ ] Jobs & Pipelines: no active runs, no continuous jobs or streams
- [ ] Storage account: SFTP disabled
- [ ] Cloud Shell closed
- [ ] Today's DBUs recorded from ops/cost_check; Azure cost filled in next day from Cost Analysis
