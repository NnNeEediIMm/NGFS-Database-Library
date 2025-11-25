# NGFS Database Library
NGFS Database Library is a C# Library that is created for use for local database usage. It uses encryption, with local iles to save data. Keep in mind that it is curently in beta, so it is work still in progress.

Usage guide:
 - First you have to define class:
   NGFS db = new NGFS( -here goes path where database files will be saved- );

 - Then you can use commands:
------------------------------------
List:

db.DatabaseExists( database name );
//Bool used to check if database exists
 
db.CreateDatabase( database name );
//Used to create database

db.DeleteDatabase( database name );
//Deletes the database

db.ResetDatabase( database name );
//resets database

db.Add( value to be added (string []) , database name );
//add info to database

db.IndexFromFieldValue( database name , value of field that you want to get index from , field index , if multiple indexes choose what  index u want (0 by default) );
//get index from field value

List<string[]> database list = db.GetDatabase( database name );
//get full database, list is made with string[] so list is made of rows and inside string[] are the fields;

db.DeleteIndex( database name , row index );
//delete certain row in a database

db.GetLibraryVersion();
//returns version of the library

db.EditIndex( database name , new text value of field , row index , field index );
//Changes certain field value in database

db.GetValueByIndex( database name , row index , field index );
//get value of a certain field
