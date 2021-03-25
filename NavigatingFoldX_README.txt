- Navigating FoldX to run commands -

As you have seen, there are two commands to run when performing stability
prediction with FoldX. Although FoldX is simple for a novice user, there are
still some important considerations to take into account:

1) Running from the Current Directory -

The ./ before foldx and RepairPDB_<pdbname>.cfg tells your system that the
executable (foldx) and the .cfg file are in your working/current directory/folder. 
To check your working directory in a unix command prompt, use:

pwd

All of the necessary files should be located in the working directory when
running the command in this way. To avoid clutter, consider making a seperate 
directory where all of the necessary files and executables will be located.
In a unix command prompt, you can make a new directory as so:

mkdir <newdirectoryname>

2) Necessary Files -

To execute the RepairPDB and PositionScan command, your working directory should
contain these files and executables:

(RepairPDB)
 - RepairPDB_<pdbname>.cfg
 - foldx executable
 - <pdbname>.pdb

(PositionScan)
 - PS_<pdbname>_Repair.cfg
 - foldx executable
 - <pdbname>_Repair.pdb ## you will only have this file after RepairPDB is complete

As mentioned in (1), it is critical that the correct files and executables are located
in the directory from which you run each command, avoiding the hassel of setting a path
for you foldx executable and simplifying the command line itself.

3) Notes when working with FoldX

 - Once you acquire a license and download and unpack FoldX, keep in mind the expiration
 date, as you will need to re-download FoldX if you plan to continue using it past that 
 date.

 - For a 58 Residue protein (1H0T_WT.pdb) on a 2.5 GHz Dual-Core Intel Core i5 10 GB
 1600 MHz DDR3 Mid 2012 MacBook Pro:
 	(RepairPDB) took ~1.5 minutes
	
 - For a 58 Residue protein (1H0T_WT.pdb) on a computing cluster using MaxRSS below 5 Gb*
 for one Node, one task per node, and one CPU per task:
	(PositionScan; 13 positions each mutated to all 20 amino acids) took ~13.5 minutes
	* - This is not a recommendation when performing PositionScan





