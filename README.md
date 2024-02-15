# fuzzy-doodle-01
a practice project for development with Fulcro RAD

# Goals
Demonstrating Fulcro RAD development from scratch using best practices 

## Simply (?)
List items from Database 1 on DB1 Page

Each item on DB1 Page should have a button

When an item's button is pressed on DB1 Page
- that item no longer appears on DB1 Page
- that item should be added to Database 2
- that item's Database 1 record is updated to show "sent to DB2"

List items from Database 2 on DB2 Page

Each item on DB2 Page should have a button

When an item's button is pressed on DB2 Page
- that item no longer appears on DB2 Page
- that item's record has a status on Database 1 that shows "processed on DB2"

## Version 2
Items on DB2 Page can be sent back to DB1 Page
- records are removed from Database 2
- records on Database 1 appear as if they had never gone to Database 1

DB1 Page and DB2 Page options
- add an option to page through all items and see their status on the database for that page

All items page 
- shows items in order of ID and their status on both databases
- can search for item by ID
