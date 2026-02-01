
--Flush dirty SQL pages
CHECKPOINT;

--Clear Buffer Pool(data cache)
DBCC DROPCLEANBUFFERS;

--Clear SP cache for all DBs
DBCC FREEPROCCACHE

--Clear SP cache for [YourDatabaseName] DB
USE [YourDatabaseName];
ALTER DATABASE SCOPED CONFIGURATION CLEAR PROCEDURE_CACHE;

--Clear System Cache(ad hoc & prepared plans)
DBCC FREESYSTEMCACHE('SQL Plans')

--Clear ALL System Cache [USE CAREFULLY ON PRODUCTION]
DBCC FREESYSTEMCACHE('ALL')
