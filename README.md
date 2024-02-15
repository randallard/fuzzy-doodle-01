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

## setup
I started a docker container for PostgreSQL as described at https://www.commandprompt.com/education/how-to-create-a-postgresql-database-in-docker/

I created a database named "demo" and a database named "demo2"

I tested with the following :main in src/shared/config/defaults.edn

       {:main {:flyway/migrate?          false
           :flyway/migrations        ["classpath:config/sql_migrations"]
           :hikaricp/config          {"dataSourceClassName"     "org.postgresql.ds.PGSimpleDataSource"
                                      "dataSource.serverName"   "localhost"
                                      "dataSource.user"         "postgres"
                                      "dataSource.password"         "pass123"
                                      "dataSource.databaseName" "demo2"}
           :sql/vendor               :postgresql
           :sql/auto-create-missing? true
           :sql/schema               :production}}

the only difference for "demo" being 

      "dataSource.databaseName" "demo2"

For each database - I started the CLJ REPL and ran the migration


