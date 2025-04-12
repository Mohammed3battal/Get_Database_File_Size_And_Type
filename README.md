## Script: Get SQL Server Database File Information and Disk Size

**Description**:
This script queries the `sys.dm_io_virtual_file_stats` dynamic management view to gather I/O statistics for all database files. It joins this with `sys.master_files` to retrieve metadata, including file type (data or log), logical name, physical path, and disk size (in KB, MB, and GB).

**What It Shows**:
- `DB Name`: The name of the database.
- `File Logical Name`: The logical name of the database file.
- `File Type`: Whether it's a data file or log file.
- `File Physical Name`: The path of the physical file.
- `Size(KB)`, `Size(MB)`, `Size(GB)`: The file size on disk in different units.

**Use Case**:
- Monitor file growth and disk usage across databases.
- Perform space audits to determine the size of data and log files.
- Check whether files are distributed properly across storage devices.

**Requirements**:
- SQL Server 2008 or later
- `VIEW SERVER STATE` permission
- Can be executed on any instance hosting SQL Server databases

**Notes**:
- Sizes reported are based on `sys.dm_io_virtual_file_stats`, which reflects the current disk usage of each file, rather than logical file sizes.
