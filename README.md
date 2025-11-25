# NGFS Database Library
NGFS Database Library is a C# Library that is created for use for local database usage. It uses encryption, with local iles to save data. Keep in mind that it is curently in beta, so it is work still in progress.

Usage guide:
 - First you have to define class:
   NGFS db = new NGFS( -here goes path where database files will be saved- );

 - Then you can use commands:
------------------------------------
List:
db.DatabaseExists(databaseName);
// Returns a bool indicating whether the database file exists.


db.CreateDatabase(databaseName);
// Creates a new empty database (.ngfsdata file).
// Throws an exception if it already exists.


db.DeleteDatabase(databaseName);
// Deletes the specified database file.
// Throws an exception if it does not exist.


db.ResetDatabase(databaseName);
// Deletes the database if it exists, then recreates it empty.


db.Add(databaseName, stringArrayValues);
// Adds a new row to the database.
// The row consists of encrypted fields from the string[] array.


db.AddAtIndex(databaseName, stringArrayValues, rowIndex);
// Inserts a new row at the specified index (shifting existing rows down).


db.IndexFromFieldValue(databaseName, fieldValue, fieldIndex);
// Searches rows for a specific field value, at field index.
// Returns the row index where value of field at fieldIndex == fieldValue.
// Returns array of index as int


List<string[]> database = db.GetDatabase(databaseName);
// Loads the entire database into a List of string[].
// Each List entry = a row, and each string[] = decrypted fields.


db.DeleteIndex(databaseName, rowIndex);
// Removes a specific row from the database (by index).
// Does nothing if the row is empty or index is out of range.


db.EditIndex(databaseName, newValue, rowIndex, fieldIndex);
// Edits a specific field of a row.
// Decrypts the row, modifies the field, then re-encrypts and saves it.


db.GetValueByIndex(databaseName, rowIndex, fieldIndex);
// Returns the decrypted value of a specific field.
// Returns an empty string if the index is invalid.


db.GetLibraryVersion();
// Returns the current version of the NGFS library.
