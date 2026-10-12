# Minecraft Backup Restore Drills

A practical runbook for proving that Minecraft world backups can be restored. A successful backup job is not evidence that a usable restore exists.

## Principles
- Keep backup credentials separate from game-server credentials.
- Store at least one encrypted copy outside the server host and account.
- Back up world data only while the server is stopped or after a documented consistent snapshot.
- Never run restore exercises against the production world path.

## Restore exercise
1. Select a dated backup and record its checksum and source.
2. Restore into an isolated staging directory with restricted permissions.
3. Verify expected world folders, level metadata, and region-file readability.
4. Start a disposable server on the restored copy and check startup logs, spawn, and representative chunks.
5. Record elapsed recovery time, missing data, and the tested backup age.
6. Delete staging data according to the retention policy and remove temporary credentials.

## Report
Record operator, UTC start/end, backup identifier, checksum, server and plugin versions, validation results, recovery time, and follow-up actions. Redact player identifiers and storage secrets from shared logs.

This repository provides operational guidance only; adapt retention and recovery objectives to your own service.