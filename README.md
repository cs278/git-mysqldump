git-mysqldump
=============

Git wrapper around mysqldump, simplifying the storage of MySQL backups in a
git repository.

A few words of warning:
* First off this hasn't had extensive testing. It works for me, but as always
  YMMV. Remember an untested backup is *not* a backup!
* There won't be any consistency between databases, however tables in the same
  database *should* be consistent.

Requirements
------------
* Git >= 1.4.4
* bash >= 4.0.0
* mysql >= 5.0.26
* coreutils

Usage
-----

	# Initialise a git repository
	git init
	
	# Configure to use a MySQL configuration file and backup all databases
	git mysqldump config -c /path/to/my.cnf -a
	
	# Append the 'database1' and 'database2' to the backup list
	git mysqldump config database1 database2
	
	# Set list of databases to 'stuff'
	git mysqldump config -t stuff
	
	# Get a list of available databases
	git mysqldump ls-db
	
	# Test connection to MySQL
	git mysqldump test
	
	# Run a backup and commit with the given message
	git mysqldump "New backup message"
