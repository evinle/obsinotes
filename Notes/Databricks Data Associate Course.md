- What is Databricks?
	- Multi cloud Lakehouse platform based on Apache Spark
		- Combines Data Lake and Data warehouse
			- Data Lake: Open, flexible, ml support
			- Data warehouse: reliable, performant, strong governance
- 3 Layers
	- Cloud Service: Multi cloud
	- Runtime: Core components like Spark and Delta Lake
		- Provision VMs or nodes of a cluster
		- Nodes of a cluster comes preinstalled with databricks runtime
	- Workspace 
- How databricks resources are deployed
	- Control plan: in dbr account
	- Data plan: in Cloud sub
- Databricks gives tools to control and deploy your infra
- Spark on Databricks
	- Spark is open source in memory distributed computing 
	- Designed to process realtime/batch/analytics/sql all in one
- DBFS - distributed Databricks file system
	- Abstraction layer, still uses underlying cloud storage
	- Data is not encrypted or transformed, stored as regular cloud storage objects underneath
	- Proprietary: dbr FUSE mount `/dbfs`
- Also Delta Lake, developed by dbr
	- Open source
	- high performance storage layer that integrates with spark
	- brings new features like ACID, schema validation and time travel

## Pracs
- Free Azure Data bricks VM
- Databricks Free Edition

I guess the value really comes from the ability to integrate everything together
There are some proprietary technologies here and there, but the selling point seems to be integration between between layers, storage + compute + analysis, rather than a groundbreaking proprietary closed off stack
For example, it could be costly to do testing on integrating everything on the stack manually, like spinning up a cluster of VMs that have workers and driver all running spark, and then orchestrating them to also write to the underlying storage, but that time is now saved through databricks, with updates, security and everything else taken care off as well