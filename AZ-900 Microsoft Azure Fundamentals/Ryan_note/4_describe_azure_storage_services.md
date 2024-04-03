# 4.0 Describe storage accounts

## Types of Storage Account : determining storage services and redundancy options

- redundency options

1. Locally redundant storage (LRS)
1. Geo-redundant storage (GRS)
1. Read-access geo-redundant storage (RA-GRS)
1. Zone-redundant storage (ZRS)
1. Geo-zone-redundant storage (GZRS)
1. Read-access geo-zone-redundant storage (RA-GZRS)

## Account endpoints

- naming rules apply

# 4.1 Describe Storage Redundancy

## Term: redundancy

- Redundancy is the duplication of critical components or functions of a system with the intention of increasing reliability of the system, usually in the form of a backup or fail-safe.
- Azure Storage alwasy **stores mutiple copies** of data

## Redundnacy in primary region

- 3 times replication
- 2 options: LRS, ZRS

### Locally redundant storage (LRS)

1. 3 copies , in a single datacenter
2. lowest cost
3. Ok: server rack failure, drive failure
4. Not Ok: datacenter failure, natural disaster

### Zone-redundant storage (ZRS)

![recap: azure geographies](https://k21academy.com/wp-content/uploads/2023/06/AvailabilitySet.webp)

1. 3 copies, in 3 different AZs in a primary region
2. accessible for R&W operations
3. high availability

## Redundancy in secondary region

- high durability
- copied to another region miles away from pirmary
- paired region chosen by Azure, not changeable
- 2 options: GRS, GZRS
- by default, not for R/W
- if failover, secondary becomes primary with potential data loss
  - RPO recovery point objective: time between last backup and failure

### Geo-redundant storage (GRS)

- 3 copies in a single physical location
- similar to LRS

![GRS](https://learn.microsoft.com/en-us/training/wwl-azure/describe-azure-storage-services/media/geo-redundant-storage-3432d558.png)

### Geo-zone-redundant storage (GZRS)

- similar to ZRS
  ![GZRS](https://learn.microsoft.com/en-us/training/wwl-azure/describe-azure-storage-services/media/geo-zone-redundant-storage-138ab5af.png)

### Read only

- read enabled only when failover
- cf. RA-GRS, RA-GZRS
  - read access in secondary

# 4.2 Describe Azure Storage Services

## Azure Blob

- for massive unstructured data
- ideal for :
  - serving images or documents directly to a browser
  - storing files for distributed access
  - Streaming video and audio
  - storing data for backup and restore, disaster recovery, and archiving
  - storing data for analysis by an on-premises or Azure-hosted service

### Storage tiers

- hot: frequent access
- cool: infrequent access (30days min)
- cold: rare access (90days min)
- archive: long term retention (180days min)
  - stored offline

## Azure Files

## Azure Queues

- for large numbers of messages

## Azure Disks

- block-level volumes for VMs
  - virtualised 'physical' disk

## Azure Tables

- for large amounts of structured data

# 4.3 Identify Azure data migraiton options

- support: real-time & asynchronous data transfer

## Azure Migrate

- for on-premises to Azure

## Integrated tools

1. Azure migrate: discovery and assessment 评估、准备 VMware, Hyper-V, physical servers
2. Azure migrate: server migration 准备后，真正迁移
3. Data migration assistant: 专门评估 SQL 服务器
4. Database migration service : SQL 服务器迁移
5. App service migration assistant 评估 on-premises websites for migration 如.net, Php 网页软件
6. Data box 迁移海量数据
   1. 80 TB
   2. 物理迁移
   3. Import to or export from Azure

# 4.4 Identify Azure file movement options

## AZCopy

- command line utility
- work with other clouds

## Storage explorer

- standalone app , graphical interface, across platforms

## File sync

- centralize file share in Azure
