[title]: # (SQL Server Transaction Log)
[tags]: # (where are)
[priority]: # (4)
# SQL Server Transaction Log

SQL Server maintains a history of all operations using a Transaction Log. If this transaction log becomes full, you may receive one or more of the following errors:

* System.ArgumentException: Cannot add two background tasks with the same name.
* Thycotic.Data.DataAccessorException: The transaction log for database '{database}' is full. To find out why space in the log cannot be reused, see the log_reuse_wait_desc column in sys.databases

By default, a transaction log can grow to an unrestricted size. A transaction log may become full under the following circumstances:

* The drive where the transaction log file is kept is out of disk space.
* The transaction log file hits its growth limit.

Possible solutions include:

* Backing up the log.
* Freeing disk space so that the log can automatically grow.
* Moving the log file to a disk drive with sufficient space.
* Increasing the size of a log file.
* Adding a log file on a different disk.
* Completing or killing a long-running transaction.
* Switching to simple recovery mode and truncating the log.

For more detailed information on transaction logs in SQL, see http://technet.microsoft.com/en-us/library/ms345583%28v=sql.90%29.aspx
