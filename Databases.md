# AWS Database Design

## Database types
- hosted services
  - relational/non-relational (NoSQL)
- Custom installs
  - BYOL

### Hosted Services
- AWS Relational Db Service (RDS)
  - Aurora MySQL/PostgreSQL
  - Oracle
  - SQL Service
  - MySQL
  - PostgreSQL
  - MariaDB

### Custom Instance
- Start an instance w/ OS
  - AMI
- Install the DB service
  - ISO image
- Create DB

### Flat File vs. Relational
- Flat file
  - One line per record
  - does not contain multiple tables
  - think excel with one sheet
- Relation DB
  - store portions into tables
  - tables are related base on unique identifier

### NoSQL
- Not based on SQL or relational design theory
- fast transactions
- DynamoDB is a NoSQL

### Data Warehouses
- large central repos for data
- aggregated from one or more sources
- used for BI or analytics
- RedShift does this

## Relational Databases

### RDB Terms
- Rows = tuples
- Columns = attributes/properties
- Tables = relations/entities/objects
- views and results
  - view = saved set of results

### Relationships
- Primary Key
  - ID in the current table
- Foreign Key
  - ID in the other table
- Join
  - based on foreign and primary keys matching

### Normalization
- process for eval and correct structure
  - determines the best column to tables
- works through stages
  - 1, 2, 3, 4 NormalForm (NF)
  - higher NF slower reads/faster writes

## DB Hosting Methods

### EC2 Instances
1. Launch instance
2. Install the DB service
3. Open ports
4. Connect
- complete control
- manual performance/update

### AWS Service
1. Launch DB
2. Connect!
- less control
- auto performance/update

## HA Solutions

### Clustering
- multiple instances
- one database with replication
- auto failover
- active/active cluster
- increased cost

### Standby Instances
- multiple servers
- one db w/ replication
- increase recoverability
- no auto failover
- reduced cost
  - second instance doesn't have to be as powerful

### Single AZ Deployment
- one instance, AZ, and region

### Multiple AZ Deployment
- multi instance, AZ, and region
- increased availability and performance
- increased cost as well

## Scalability Solutions

### Scalability
- can increase capacity
  - storage, processing, network throughput 

### Scaling the instance
- changing instance type or class
- AutoScaling is not supported in RDS
  - can be scripted with CLI commands for DBs
 
### Read Replica
- RO copy
- offloads RO traffic from main DB
- multiple instances in regions
  
## Database Security

### Encryption
- RDS support _at-rest_ encryption
- must be enabled at creation
  - can be enabled at recovery though

### Permissions
- admin access based on IAM
- data access based on capabilities
  - CRUD
  - managed in the permissions of the DB
  - DB admin with the DB

## Aurora

### What is it?
- built by Amazon
- RelationDB
- optimized for online transaction processing (OLTP)
  - very fast writes
  - not so good for reads
- MySQL compatible
- 5x faster

### Scaling
- initially 10GB, grows in 10GB increments
  - max 64TB
- compute resources
  - max 32 CPUs
  - max 244 GiB RAM

### Availability
- defaults
  - 2 DB copies
  - min 3 AZs
- write capability
  - continues with up to two copies lost
- read capability
  - continues with up to three lost

### Replicas
- up to 15
  - auto failover
- up to 5 MySQL read replicas
  - no auto failover

## Redshift

### What is it?
- data warehouse DB
- optimized for Online Analytics (OLAP)
- AWS managed
- Pricing
  - entry $0.25/hr
  - $1,000 per TB/yr
- single node
  - 160GB
- multi node
  - leader node
    - connects and queries
  - computer node
    - stores data and executes queries

### Speed
- Columnar data stores
  - like an excel spreadsheet
  - very fast sequential reads
- Data compression
- Massively Parallel Processing (MPP)

### Security
- SSL transit encryption
- AES-256 for at-rest encryption
- Managed through AWS Key Management

### Availability
- operates in one AZ
- Snapshots can be restored to new AZs

## DynamoDB

### What is it?
- NoSQL service
- not a relationship database
- provide special features
  - millisecond latency at any scale
    - Very VERY fast RW
  - Stored on SSD
  - Spread across 3 distinct data centers
- read consistency types
  - eventual reads
    - few seconds delay
  - strongly reads

### Pricing
- Storage
  - $0.25/GB per month
- Throughput
  - Write: billed per hour for every 10 units
  - Read: billed per hour for every 50 units
  - 1 unit equals 1 RW per second

