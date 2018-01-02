---

title:="Azure SQL Database backups - automatic, geo-redundant | Microsoft Docs" 
description: "SQL Database automatically creates database backups and uses Azure read-access geo-redundant storage for geo-redundancy."
services: "sql-database"
documentationCenter: ""
authors: "CarlRabeler"
manager: "jhubbard"
editor: ""/>

ms.service="sql-database"
ms.devlang="NA"
ms.custom: "NA"
ms.topic="article"
ms.tgt_pltfrm="NA"
ms.workload="NA"
ms.date="11/16/2016"
ms.author="carlrab;barbkess"/>

---

# How database backups work in Azure SQL Database

<!------------------
This topic is annotated with TEMPLATE guidelines for overview topics.

The overview topic is a one-pager (ok, sometimes a bit longer) that explains capabilities of the service. It explains what the capability is, the benefits of using it, and how it works.  The term "capability" is broad and includes concepts, product overviews, features, scenarios, etc.

The overview topic does not necessarily have the word OVERVIEW in the title. Here are some title examples:

	What is ...?
	Learn about ...
	Capabilities of ...
	How ... works
	What's new in ... ?
	Understand  ... 
	Overview of ... 
	
The overview topic is a "learning" topic, not an action topic.

DO explain this:
	• Definition of the capability and the associated terminology.  i.e., What is a database backup?
	• Characteristics of the capability and how this works.
	• Common uses with links to other overview topics that recommend when to use this.
	• Optional reference specifications (Limitations and Restrictions, Permissions, General Remarks, etc.)
	• Next Steps with links to related overviews, scenarios, and tasks.

DON'T explain this:
	• How to steps for using the capability.
	• How to solve business problems that incorporate the capability, feature, etc.
----------------------->

<!---------------------
**Metadata guidelines**

pageTitle
	60 characters or less. Includes name of the capability - primary benefit. Not the same as H1. It's 60 characters or fewer including all characters between the quotes and the Microsoft Docs site identifier.

	Use the service name in the title and precede the service with "Azure".  For example, "Azure SQL Database".

description
	115-145 characters. Duplicate of the first sentence in the introduction. This is the abstract of the article that displays under the title when searching in Bing or Google. 

	Example: "SQL Database automatically creates a local database backup every few minutes and uses Azure read-access geo-redundant storage for geo-redundancy."
----------------------->

<!---------------------
**GUIDELINES for the H1**
	
	The H1 should answer the question "What is in this topic?" Write the H1 heading in conversational language and use search keywords as much as possible. Since this is a learning topic, make sure the title indicates that and doesn't mislead people to think this will tell them how to do tasks.  
	
	To help people understand this is a learning topic and not an action topic, start the title with "How something works ... " or one of the other terms suggested previously

	Heading must use an industry standard term. If your feature is a proprietary name like "Elastic database pools", use a synonym. For example:	"Learn about elastic database pools for multi-tenant databases". In this case multi-tenant database is the industry-standard term that will be an anchor for finding the topic.
---------------------->

<!--------------------
**GUIDELINES for introduction**
	
	The introduction is 1-2 sentences.  It is optimized for search and sets proper expectations about what to expect in the article. It should contain the top keywords that you are using throughout the article.The introduction should be brief and to the point of what the feature is, what it is used for, and what's in the article. 

	In this example:

Sentence #1 Explains what the article will cover, which is what the feature is or does. This is also the metadata description. 
	SQL Database automatically creates a local database backup every five minutes and uses Azure read-access geo-redundant storage (RA-GRS) to provide geo-redundancy. 

Sentence #2 Explains why I should care about this.  
	Database backups are an essential part of any business continuity and disaster recovery strategy because they protect your data from accidental corruption or deletion.
---------------------->

SQL Database automatically creates database backups and uses Azure read-access geo-redundant storage for geo-redundancy. Database backups are an essential part of any business continuity and disaster recovery strategy because they protect your data from accidental corruption or deletion. 

<!-- Add an image if it is self-explanatory. It shouldn't need a written explanation. 

![How SQL Database backups work](./media/sql-database-geo-restore/geo-restore-1.png)

-->

<!-----------------
GUIDELINES for the first ## H2.

	The first ## describes what the capability encompasses and how it is used. It points to related task articles.
	
	For consistency, begin the heading with "What is ... "
------------------->

## What is a SQL Database backup?  

<!----------------- 
	Explains what a SQL Database backup is and answers an important question that people want to know.
------------------>

A SQL Database backup includes both local database backups and geo-redundant backups. These backups are created automatically and at no additional charge. You don't need to do anything to make them happen.

<!----------------- 
	Explains first component of the backup capabilities
------------------>

For local backups, SQL Database uses SQL Server technology to create [full](../../docs/relational-databases/backup-restore/full-database-backups-sql-server.md), [differential](../../docs/relational-databases/backup-restore/differential-backups-sql-server.md) backups. The transaction log backups happen every five minutes, which allows you to do a point-in-time restore to the same server that hosts the database. When you restore a database, the service figures out which full, differential, and transaction log backups need to be restored.

<!--------------- 
	Explicit list of what to do with a local backup. "Use a ..." helps people to scan the topic and find the uses quickly.
---------------->

Use a local database backup to:

- Restore a database to a point-in-time within the retention period. With a database backup you can restore a database to a point-in-time, restore a deleted database to the time it was deleted, or restore a database to another geographical region. To perform a restore, see [restore a database from a database backup](sql-database-recovery-using-backups.md).

- Copy a database to a SQL server in the same or different region. The copy is transactionally consistent with the current SQL Database. To perform a copy, see [database copy](sql-database-copy.md).

- Archive a database backup beyond the backup retention period. To perform an archive, [export a SQL database to a BACPAC](sql-database-export.md) file. You can then archive the BACPAC to long-term storage and store it beyond your retention period. Or, use the BACPAC to transfer a copy of your database to SQL Server, either on-premises or in an Azure virtual machine (VM).

<!----------------- 
	Explains second component of the backup capabilities
------------------>

For geo-redundant backups, SQL Database uses [Azure Storage replication](../storage/storage-redundancy.md). SQL Database stores local database backup files in a [Read-Access Geo-Redundant Storage (RA-GRS)](../storage/storage-redundancy.md#read-access-geo-redundant-storage) account. Azure replicates the backup files to a [paired data center](../best-practices-availability-paired-regions.md). 

<!--------------- 
	Explicit list of what to do with a geo-redundant backup. "Use a ..." helps people to scan the topic and find the uses quickly.
---------------->

Use a geo-redundant backup to:

- Restore a database to a different geographical region in case you cannot access the database backup from your primary database region. 

> [!NOTE] 
> In Azure storage, the term *replication* refers to copying files from one location to another. SQL's *database replication* refers to keeping to multiple secondary databases synchronized with a primary database. 

<!----------------
	The next ## H2's discuss key characteristics of how the capability works. The title is in conversational language and asks the question that will be answered. The title does not have to be written in question form.
------------------->
## How much backup storage is included at no cost?

SQL Database provides up to 200% of your maximum provisioned database storage as backup storage at no additional cost. For example, if you have a Standard DB instance with a provisioned DB size of 250 GB, you have 500 GB of backup storage at no additional charge. If your database exceeds the provided backup storage, you can choose to reduce the retention period by contacting Azure Support. Another option is to pay for extra backup storage that is billed at the standard Read-Access Geographically Redundant Storage (RA-GRS) rate. 

## How often do backups happen?

For local database backups, full database backups happen weekly, differential database backups happen hourly, and transaction log backups happen every five minutes. The first full backup is scheduled immediately after a database is created. It usually completes within 30 minutes, but it can take longer when the database is of a significant size. For example, the initial backup can take longer on a restored database or a database copy. After the first full backup, all further backups are scheduled automatically and managed silently in the background. The exact timing of full and [differential](../../docs/relational-databases/backup-restore/differential-backups-sql-server.md) database backups is determined as it balances the overall system workload. 

For geo-redundant backups, full and differential backups are copied according to the Azure Storage replication schedule.

<!------------------
	Use conversational words that people really use.  "How long do you keep my backups?" is much more friendly than saying "Backup retention schedule." The retention schedule sounds institutional.
------------------->

## How long do you keep my backups?

Each SQL Database backup has a retention period that is based on the [service-tier](sql-database-service-tiers.md) of the database. The retention period for a database in the:

<!------------------
	Use lists when possible so the information is easy to find when scanning.
------------------->

- Basic service tier is seven days.
- Standard service tier is 35 days.
- Premium service tier is 35 days.


If you downgrade your database from the Standard or Premium service tiers to Basic, the backups are saved for seven days. All existing backups older than seven days are no longer available. 

If you upgrade your database from the Basic service tier to Standard or Premium, SQL Database keeps existing backups until they are 35 days old. It keeps new backups as they occur for 35 days.
 
If you delete a database, SQL Database keeps the backups in the same way it would for an online database. For example, suppose you delete a Basic database that has a retention period of seven days. A backup that is four days old is saved for three more days.


<!-----------------
    Use notes sparingly. Customer might ignore the notes. They do help break up the visual space to make the article look more interesting.  Use them to add a related piece of information that broadens the customer's knowledge.
------------------->

>[AZURE.IMPORTANT]
	If you delete the Azure SQL server that hosts SQL Databases, all databases that belong to the server are also deleted and cannot be recovered. You cannot restore a deleted server.

<!-------------------
OPTIONAL section
## Best practices 
--------------------->

<!-------------------
OPTIONAL section
## General remarks
--------------------->

<!-------------------
OPTIONAL section
## Limitations and restrictions
--------------------->

<!-------------------
OPTIONAL section
## Metadata
--------------------->

<!-------------------
OPTIONAL section
## Performance
--------------------->

<!-------------------
OPTIONAL section
## Permissions
--------------------->

<!-------------------
OPTIONAL section
## Security
--------------------->

<!-------------------
GUIDELINES for Next Steps

	The last section is Next Steps. Give a next step that would be relevant to the customer after they have learned about the feature and the tasks associated with it.  Perhaps point them to one or two key scenarios that use this feature.

	You don't need to repeat links you have already given them.
--------------------->

## Next steps

Database backups are an essential part of any business continuity and disaster recovery strategy because they protect your data from accidental corruption or deletion. To see how database backups into a broader strategy, see [Business continuity overview](sql-database-business-continuity.md).


