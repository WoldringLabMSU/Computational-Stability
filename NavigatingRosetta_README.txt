 - Navigating Rosetta to run executables -

As you have seen, the workflow, executables, and operands/arguments are much longer in Rosetta.
There are some important considerations similar to FoldX navigation, as well as new ones, to take into account:

1) Your /PATH/TO/ROSETTA/ and A Comment On Unix Commands -

The /PATH/TO/ROSETTA/ is a placeholder for your actual path to the Rosetta directory/folder.
As an example, the PATH to Rosetta may look like this on a unix command prompt:

/Users/<Username>/Desktop/Rosetta/rosetta_bin_linux_2020.08.61146_bundle/

or

/mnt/home/<Username>/Rosetta/rosetta_bin_linux_2020.08.61146_bundle/

Typing out rosetta_bin_linux_2020.08.61146_bundle should not be necessary, you can rename
the directory as so:

mv rosetta_bin_linux_2020.08.61146_bundle Rosetta

*** Because these unix commands and others are commonly used and are a necessity
to become familiar with for using Rosetta in it's simplest form (Rosetta Commandline), it
is recommended that you learn these common commands before proceeding. ***

2) Necessary Files -

To execute the Rosetta executables below, your working directory should
contain these files:

(clean_pdb.py)
 - <pdbname>.pdb

(pdb_renumber.py)
 - <pdbname>_<chainid>.pdb ## you will only have this file after clean_pdb.py is complete

(ddg_monomer.linuxgccrelease - For Low Resolution ddG_monomer)
 - <renumberedpdbname>.pdb
 - <resfilename>.resfile

(minimize_with_cst.linuxgccrelease - For High Resolution ddG_monomer)
 - <listname>

(convert_to_cst_file.sh - For High Resolution ddG_monomer)
 - mincst.log

(ddg_monomer.linuxgccrelease - For High Resolution ddG_monomer)
 - min_cst_0.5.<renumberedpdbname>_001.pdb
 - <renumberedpdbname>.resfile
 - <constraintfilename>.cst

3) Notes when working with Rosetta - 

 - If you are working between a server cluster and your local desktop, you may need to transfer
 certain files back and forth depending on your permissions to use certain commands on the server
 cluster. The example commands below indicate how to transfer files/folders between the server cluster and
 your local desktop on a unix command prompt, but it is recommended that you explore its 
 functionality further online or your server cluster documentation/help desk:

	(Server Cluster -> Local Desktop)
	scp -r <username>@<something>.<something>:/PATH/TO/FILE/OR/FOLDER/ /PATH/IN/LOCAL/DESKTOP/

	(Local Desktop -> Server Cluster)
	scp -r /PATH/TO/FILE/OR/FOLDER/ <username>@<something>.<something>:/PATH/IN/SERVER/CLUSTER/

 - For a 58 Residue protein (1H0T_WT.pdb) on a computing cluster requesting 2000Gb*
 for one Node, one task per node,and one CPU per task:
        
	(minimize_with_cst) took ~25 seconds
        * - This is not a recommendation when performing minimize_with_cst and was only used for convenience

	(ddg_monomer) took ~24 hours
	* - This is not a recommendation when performing ddg_monomer and was only used for convenience


	
