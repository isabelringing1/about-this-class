- How to visualize a SQL database:
	- The entire database is an Excel spreadsheet
	- Individual tables are sheets within the spreadsheet
	- Each table (i.e. sheet) can have its own fields (column names), 
	and you can also have cross-table references

- Useful commands for exploring your SQL database:
	- `sqlite3 foo.db` - enters the interactive shell for the database called `foo.db`
	- `.exit` - quits the interactive shell
	- `.schema` - shows the schema for the database's tables
	- `.tables` - lists the tables in the database

- For this assignment:
	- Make sure that you're creating the questions in a folder that doesn't currently exist. For example, I'd run `./cpsc213sqlhw create-questions jlb325 questions` as long as `questions` didn't exist.
	- If everything looks about right but the tests aren't passing, 
	make sure that you're sorting the results in the right order
	- Don't forget the semicolon at the end of each SQL command!
	- Committing your work to git after each part will help prevent 
	tragic mistakes 
