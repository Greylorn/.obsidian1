In order to proceed with an  FRS to DFSR SYSVOL migration, the forest function level must be first configured on your Windows server. If your organization has not done this yet, you must first get the forest and domain function level updated.

You can verify if the system uses the FRS using dfsrmig /getglobalstate.

1)    Log in to domain controller as Domain admin or Enterprise Admin  
2)    Launch powershell console and type dfsrmig /getglobalstate.

Below output confirms that it has not yet initiated the DFRS migration yet.

![FRS to DFSR SYSVOL Migration Steps](https://cdn-ejaef.nitrocdn.com/OEqQeEpzgEgOHfhqKIdrGVhtvpvfgUII/assets/static/optimized/rev-59390d5/wp-content/uploads/2021/06/1.png)

Before proceeding with any configuration changes,  we suggest that you familiarize yourself  with the migration stage.

Below are are four states that correspond with the four migration phases.

1)    **State 0** – Start  
2)    **State 1** – Prepared  
3)    **State 2** – Redirected  
4)    **State 3** – Eliminated

_**State 0 – Start**_

With initiating this state, FRS will replicate the SYSVOL folder amongst the domain controllers. It is important to have a current copy of SYSVOL before begins the migration process to avoid any conflicts.

_**State 1 – Prepared**_

In this state, FRS continues replicating the SYSVOL folder while DFSR will replicate a copy of SYSVOL folder. It will be located in %SystemRoot%\SYSVOL_DFRS by default. But this SYSVOL will not respond to any other domain controller service requests.

_**State 2 – Redirected**_

In this state, the DFSR copy of SYSVOL starts to respond for SYSVOL service requests. FRS will continue the replication of its own SYSVOL copy but will not involve with production SYSVOL replication.

_**State 3 – Eliminated**_

In this state, DFS Replication will continue its replication and servicing SYSVOL requests. Windows will delete original SYSVOL folder users by FRS replication and stop the FRS replication.

In order to migrate from FRS to DFSR it must to go from State 1 to State 3. Let’s look into the migration steps in more detail.

#### **Prepared State**

Log in to domain controller as Domain admin or Enterprise Admin  
2.    Launch PowerShell console  
3.    Type dfsrmig /setglobalstate 1 and press enter

![FRS to DFSR SYSVOL Migration Steps](https://cdn-ejaef.nitrocdn.com/OEqQeEpzgEgOHfhqKIdrGVhtvpvfgUII/assets/static/optimized/rev-59390d5/wp-content/uploads/2021/06/2.png)

4.  Type dfsrmig /getmigrationstate to confirm all domain controllers have reached the prepared state

![FRS to DFSR SYSVOL Migration Steps](https://cdn-ejaef.nitrocdn.com/OEqQeEpzgEgOHfhqKIdrGVhtvpvfgUII/assets/static/optimized/rev-59390d5/wp-content/uploads/2021/06/3.png)

#### **Redirected State**

Log in to domain controller as Domain admin or Enterprise Admin  
2.    Launch PowerShell console  
3.    Type dfsrmig /setglobalstate2 and press enter

![FRS to DFSR SYSVOL Migration Steps](https://cdn-ejaef.nitrocdn.com/OEqQeEpzgEgOHfhqKIdrGVhtvpvfgUII/assets/static/optimized/rev-59390d5/wp-content/uploads/2021/06/4.png)

4. Type dfsrmig /getmigrationstate to confirm all domain controllers have reached redirected state

![FRS to DFSR SYSVOL Migration Steps](https://cdn-ejaef.nitrocdn.com/OEqQeEpzgEgOHfhqKIdrGVhtvpvfgUII/assets/static/optimized/rev-59390d5/wp-content/uploads/2021/06/5.png)

#### **Eliminated State**

Log in to domain controller as Domain admin or Enterprise Admin  
2.    Launch powershell console  
3.    Type dfsrmig /setglobalstate 3and press enter

![FRS to DFSR SYSVOL Migration Steps](https://cdn-ejaef.nitrocdn.com/OEqQeEpzgEgOHfhqKIdrGVhtvpvfgUII/assets/static/optimized/rev-59390d5/wp-content/uploads/2021/06/6.png)

4. Type dfsrmig /getmigrationstate to confirm all domain controllers have reached eliminated state

![FRS to DFSR SYSVOL Migration Steps](https://cdn-ejaef.nitrocdn.com/OEqQeEpzgEgOHfhqKIdrGVhtvpvfgUII/assets/static/optimized/rev-59390d5/wp-content/uploads/2021/06/7.png)

This completes the migration process and to confirm the SYSVOL share, type net share command and press enter.

![FRS to DFSR SYSVOL Migration Steps](https://cdn-ejaef.nitrocdn.com/OEqQeEpzgEgOHfhqKIdrGVhtvpvfgUII/assets/static/optimized/rev-59390d5/wp-content/uploads/2021/06/1-1.png)

Also make sure in each domain controller FRS service is stopped and disabled.

![FRS to DFSR SYSVOL Migration Steps](https://cdn-ejaef.nitrocdn.com/OEqQeEpzgEgOHfhqKIdrGVhtvpvfgUII/assets/static/optimized/rev-59390d5/wp-content/uploads/2021/06/2-1.png)