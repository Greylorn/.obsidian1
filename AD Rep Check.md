
### Step 1 - Check the replication health

Run the following command :  
Repadmin /replsummary

The “/replsummary” operation quickly summarizes replication state and relative health of a forest.

![how-to-check-if-domain-controllers-are-in-sync-with-each-other](https://www.manageengine.com/products/active-directory-audit/kb/images/how-to-check-if-domain-controllers-are-in-sync-with-each-other.png)

### Step 2 - Check the inbound replication requests that are queued.

Repadmin /Queue

This command lists elements that are remaining in the replication queue. It displays inbound replication requests that the Domain Controller needs to issue in order to become consistent with its source replication partners.

![how-to-check-if-domain-controllers-are-in-sync-with-each-other-2](https://www.manageengine.com/products/active-directory-audit/kb/images/how-to-check-if-domain-controllers-are-in-sync-with-each-other-2.png)

### Step 3 - Check the replication status

Repadmin /Showrepl

This command displays the replication status when the specified domain controller last attempted to implement an inbound replication of Active Directory partitions. It helps in figuring out the replication topology and replication failure.

![how-to-check-if-domain-controllers-are-in-sync-with-each-other-3](https://www.manageengine.com/products/active-directory-audit/kb/images/how-to-check-if-domain-controllers-are-in-sync-with-each-other-3.png)

### Step 4 - Synchronize replication between replication partners

Repadmin /syncall

It ensures synchronization between replication partners

### Step 5 - Force the KCC to recalculate the topology

Repadmin /KCC

This command forces the KCC (Knowledge Consistency Checker) on targeted domain controller(s) to immediately recalculate its inbound replication topology. It checks and creates the connections between the Domain Controllers. By default KCC runs in the background every 15 minutes to check if a new connection has been established between DCs.

![how-to-check-if-domain-controllers-are-in-sync-with-each-other-4](https://www.manageengine.com/products/active-directory-audit/kb/images/how-to-check-if-domain-controllers-are-in-sync-with-each-other-4.png)

### Step 6 - Force replication

Repadmin /replicate

This command forces the replication of the specified directory partition to the destination domain controller from the source DC.