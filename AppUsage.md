NGFS CONSOLE COMMAND GUI
__________________________
Before using any database commands, you must first set the main directory where all .ngfsdata files will be stored. The console prompt uses the format:

command /parameter1 /parameter2 /parameter3 ...

The placeholder %root% refers to the application’s current working directory.

Also, all commands containing database can be written as db, example: create-database can be written as create-db

DEFINE ROOT DIRECTORY
---
Command:
define /path

Description:
Defines the main directory used to store databases. This must be executed before any other command. Supports the placeholder %root% which is replaced with the application's startup directory.

Example:
define /%root%/databases

DATABASE MANAGEMENT COMMANDS
---
CREATE DATABASE
--
Command:
create-database /databaseName

Description:
Creates a new empty database file named databaseName.ngfsdata in the defined directory. If the file already exists, an error is displayed.

Example:
create-database /users

DELETE DATABASE
---
Command:
delete-database /databaseName

Description:
Deletes the specified .ngfsdata file. If the database does not exist, an error is displayed.

Example:
delete-database /users

RESET DATABASE
----
Command:
reset-database /databaseName

Description:
Deletes the database and immediately recreates an empty version of it.

Example:
reset-database /users

ENTRY MANAGEMENT COMMANDS
--

ADD NEW ENTRY
--
Command:
add-to-database /databaseName /value1, value2, value3 ...

Description:
Adds a new row to the database. Fields must be separated by commas. Spaces around values are automatically trimmed.

Example:
add-to-database /users /Bob, 17, USA

This produces a new row:
Bob | 17 | USA

ADD ENTRY AT SPECIFIC INDEX
---
Command:
add-to-database-index /databaseName /value1, value2, value3 ... /index

Description:
Same as add-to-database, but inserts the row at the specified index position.

Example:
add-to-database-index /users /Alex, 25, UK /0

This inserts at the top of the database.

DELETE ROW BY INDEX
---
Command:
delete-at-index /databaseName /index

Description:
Deletes the entire row located at the given index.

Example:
delete-at-index /users /2

EDIT SPECIFIC FIELD
----
Command:
edit-at-index /databaseName /newValue /rowIndex /fieldIndex

Description:
Edits a specific field inside a row.

newValue = value to write into the field

rowIndex = which row to target

fieldIndex = which field inside the row

Example:
edit-at-index /users /Charlie /0 /1

This changes field 1 in row 0 to "Charlie".

DATABASE READING COMMANDS
---

LIST DATABASES
--
Command:
get-database-list

Description:
Displays all .ngfsdata files inside the defined directory.

READ ENTIRE DATABASE
--
Command:
get-database /databaseName

Description:
Prints all rows and their fields, fully decrypted.

Example:
get-database /users

Output format example:
0. Bob / 17 / USA

Alex / 25 / UK

SEARCH COMMAND
--

SEARCH BY FIELD VALUE
--
Command:
search-in-database /databaseName /searchValue /fieldIndex

Description:
Searches for rows where field value of field at field index matches searchValue.
Returns array of index in int

Example:
search-in-database /users /Bob /0

Meaning:
Find row where field 0 equals "Bob", return the first match.

UTILITY COMMANDS
--

CLEAR CONSOLE
--
Command:
cls

Description:
Clears the screen.

HELP
--
Command:
help
help /link

Description:
Displays help information.
help /link opens the GitHub documentation in the browser.

EXIT
--
Command:
exit

Description:
Exits the app.
Closes the application.

VERSION
--
Command:
version /app
version /library

Description:
Check app, and library version.
