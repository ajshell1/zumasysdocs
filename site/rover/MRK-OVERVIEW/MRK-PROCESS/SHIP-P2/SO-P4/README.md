##  Sales Order Purge Process (SO.P4)

<PageHeader />

**Form Details**  
[ Form Details ](SO-P4-1/README.md)   

**Purpose**  
The SO.P4 procedure is used to purge inactive sales orders from the data base.
The criteria used to deterime which records are purged is based on a user
defined cut-off date. All sales order records which have a closed date that is
less than or equal to the cut-off date, and whose shipment records are already
deleted or show a status of posted will be deleted. Any associated shipment
records which are still on file will also be deleted.

**Frequency of Use**  
The frequency with which a purge is performed will vary depending on such
factors as available disk space and the amount of on-line history desired. At
a minimum purges should be performed on a yearly basis. Purging on a quarterly
or even a monthly basis may be desirable if the volume of transactions is
fairly high.

**Prerequisites**  
It is strongly recommended that a full account backup be performed prior to
executing any purge process. It is also recommended that this be a permanent
backup so that any records which were purged can be restored at a later date
if required.

<badge text= "Version 8.10.57" vertical="middle" />

<PageFooter />