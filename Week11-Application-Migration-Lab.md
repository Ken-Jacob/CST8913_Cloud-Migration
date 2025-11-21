# Week 11 – Application Migration Lab
### Tailwind Traders — 3-Tier Application Migration Plan

## Task 1 – Set Up Tooling for Discovery
### 1. Discovery Method
Tailwind Traders should use a **mixed discovery approach**:
- **Agentless** discovery for VM metadata and performance.
- **Agent-based** discovery for deep process-level and dependency mapping.

### 2. Number of Appliances Needed
One Azure Migrate appliance is needed because all servers are in the same VMware datacenter.

### 3. Required Credentials

### **Software Inventory**
- Domain account with local admin rights  

### **SQL Assessment**
- SQL authentication or Windows authentication with sysadmin / VIEW SERVER STATE permissions.

### **Dependency Mapping**
- Local admin to install dependency agents.

### 4. Best Practices
1. Run discovery for 14–30 days  
2. Ensure firewall ports 443/HTTPS are open  
3. Use dedicated service accounts  

## Task 2 – Assessment Planning
### 1. Assessment Type

A **Production Assessment** is required due to:

- High business impact,
- Strict downtime constraints (1 hour),
- Need for accurate performance‑based sizing.

### 2. Region & Duration
- **Region:** East US  
- **Performance history:** 30 days  

### 3. Sizing

Tailwind should use **performance‑based sizing** because:

- VMware VMs may be over‑provisioned.  
- SQL01 is a physical host requiring real performance metrics.  
- Reduces cost and ensures efficient VM sizing.

### 4. Comfort Factor & Licensing
- **Comfort factor:** 20–30%  
- **Pricing model:** Reserved Instances  
- **Licensing:** Azure Hybrid Benefit 

## Task 3 – Dependency Analysis
### Components

- WEB01, WEB02  
- APP01  
- SQL01  
- Internal Load Balancer (LB01)  
- Backup servers  
- DNS and Firewall systems  

### Dependencies

1. WEB → APP (TCP 443)  
2. APP → SQL (TCP 1433)  
3. WEB → Load Balancer (HTTP/HTTPS)  
4. Backup service → SQL01  
5. Domain controllers → all servers  
6. Patch management → all servers  
7. External HTTPS API → APP01  
8. Monitoring platform → all servers  

---

### Noise to Filter
- Broadcasts  
- DNS reverse lookups  
- Monitoring pings  
- Backup metadata traffic  

### Business Requirements

- **Criticality:** High (customer‑facing application)  
- **Uptime Requirement:** 99.9%  
- **Downtime Limit:** Maximum 1 hour  
- **Data Classification:** Sensitive (customer/transaction data)  
- **Licensing Dependencies:** Windows Server 2016, SQL Server 2017 Standard  
- **Patching:** Monthly maintenance window  
- **Firewall/IP Constraints:** Static IPs; required ports (443, 80, 1433)  
- **Backup:** Nightly full backups and hourly differentials  

## Task 4 – Validate Assessment Results
### Recommended Sizes
- **WEB:** D2s_v5 / B4ms  
- **APP:** D4s_v5  
- **SQL:** E8ds_v5 / DS14_v2  

### Components to Optimize

- Replace LB01 - Azure Internal Load Balancer
- Rehost SQL01 or use Azure SQL Managed Instance
- Migrate backups - Azure Backup
- Convert firewall rules - NSGs and optionally Azure Firewall

### Dependency Validation Summary

- All inter‑tier connections validated  
- External payment API confirmed  
- SQL dependency paths validated  
- Load balancer mappings recorded  

### SLA and Downtime Requirements

- Azure VMs can meet 99.9% to 99.99% SLA (when using Availability Zones)  
- SQL migration must be timed to respect the 1‑hour downtime ceiling

### SQL Migration Options
- Rehost  
- SQL Managed Instance  
- Azure SQL DB  

## Task 5 – Migration Plan
### Pre-Migration

- Establish Landing Zone  
- Build VNets, subnets, NSGs  
- Deploy internal load balancer  
- Prepare SQL target server  
- Configure Azure Backup  
- Validate replication health  
- Notify business stakeholders  
- Freeze configuration changes 24 hours before migration  

---

### Migration Procedures

- ### WEB Tier Migration

1. Sync final deltas  
2. Stop IIS  
3. Migrate with Azure Migrate  
4. Validate application startup  
5. Bind servers to Azure load balancer  

- ### APP Tier Migration

1. Final delta sync  
2. Stop application services  
3. Migrate VM  
4. Update configs and service endpoints  

- ### SQL Tier Migration

1. Perform complete backup  
2. Stop SQL jobs  
3. Final log shipping or replication cutover  
4. Bring SQL online in Azure  
5. Validate database integrity  

### Post‑Migration Steps

- Update public and internal DNS records  
- Update connection strings  
- Validate API responses  
- Check SQL connectivity  
- Enable and monitor backups  
- Verify firewall/NSG rules  
- Obtain final application owner sign‑off  

### Back‑Out Procedure

If a failure occurs:

1. Revert DNS to original on‑prem mapping  
2. Power‑on original servers  
3. Redirect SQL connections  
4. Disable Azure VMs to prevent conflicts  
5. Notify stakeholders  

## Task 6 – Migration Waves

### Wave Definition Table

| Wave | Components | Rationale |
|------|------------|-----------|
| **Wave 1** | WEB01, WEB02 | Low-risk, stateless servers; ideal for testing Azure networking and load balancers before migrating dependent components. |
| **Wave 2** | APP01 | Depends on WEB tier; needs the front end in place for API and functionality testing; moderate complexity. |
| **Wave 3** | SQL01 | Most critical tier; requires a planned downtime window; deep testing required (data, permissions, performance). |


