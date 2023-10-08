# How to use


You'll need to restore backup

* Run docker-compose up -d

* Connect using a client you can use AzureDataStudio

* Once you are connected with client

* Run the following query

```bash
USE master;
GO

CREATE DATABASE YourDatabaseName
    ON (FILENAME = '/database-data/backup.mdf')
    FOR ATTACH;
GO
```


```bash
RESTORE FILELISTONLY 
FROM DISK = '/database-data/bkpDoxa_20231013.bak'

RESTORE DATABASE [DOXA] FROM DISK = '/database-data/bkpDoxa_20231013.bak'
WITH MOVE 'SisACCo' TO '/database-data/SisACCo',
    MOVE 'SisACCo_log' TO '/database-data/SisACCo_log'
```