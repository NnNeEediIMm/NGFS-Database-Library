# NGFS-Database-Library
NGFS Database Library is a C# Library that is created for use for local database usage. It uses encryption, with local iles to save data. Keep in mind that it is curently in beta, so it is work still in progress.

Usage guide:
 - First you have to define class:
   NGFS db = new NGFS( -here goes path where database files will be saved- );

 - Then you can use commands:
------------------------------------
List:

db.DatabaseExists( database name );
Bool used to check if database exists
 
db.CreateDatabase( database name );
Used to create database
