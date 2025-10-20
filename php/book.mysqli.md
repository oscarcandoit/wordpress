---
url: https://www.php.net/manual/en/book.mysqli.php
scraped_at: 2025-10-20T02:47:15.753Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# MySQL Improved Extension [¶](https://www.php.net/manual/en/book.mysqli.php\#book.mysqli)

- [Introduction](https://www.php.net/manual/en/intro.mysqli.php)
- [Overview](https://www.php.net/manual/en/mysqli.overview.php)
- [Quick start guide](https://www.php.net/manual/en/mysqli.quickstart.php)
  - [Dual procedural and object-oriented interface](https://www.php.net/manual/en/mysqli.quickstart.dual-interface.php)
  - [Connections](https://www.php.net/manual/en/mysqli.quickstart.connections.php)
  - [Executing statements](https://www.php.net/manual/en/mysqli.quickstart.statements.php)
  - [Prepared Statements](https://www.php.net/manual/en/mysqli.quickstart.prepared-statements.php)
  - [Stored Procedures](https://www.php.net/manual/en/mysqli.quickstart.stored-procedures.php)
  - [Multiple Statements](https://www.php.net/manual/en/mysqli.quickstart.multiple-statement.php)
  - [API support for transactions](https://www.php.net/manual/en/mysqli.quickstart.transactions.php)
  - [Metadata](https://www.php.net/manual/en/mysqli.quickstart.metadata.php)
- [Installing/Configuring](https://www.php.net/manual/en/mysqli.setup.php)
  - [Requirements](https://www.php.net/manual/en/mysqli.requirements.php)
  - [Installation](https://www.php.net/manual/en/mysqli.installation.php)
  - [Runtime Configuration](https://www.php.net/manual/en/mysqli.configuration.php)
- [The mysqli Extension and Persistent Connections](https://www.php.net/manual/en/mysqli.persistconns.php)
- [Predefined Constants](https://www.php.net/manual/en/mysqli.constants.php)
- [Notes](https://www.php.net/manual/en/mysqli.notes.php)
- [The MySQLi Extension Function Summary](https://www.php.net/manual/en/mysqli.summary.php)
- [mysqli](https://www.php.net/manual/en/class.mysqli.php) — The mysqli class
  - [mysqli::$affected\_rows](https://www.php.net/manual/en/mysqli.affected-rows.php) — Gets the number of affected rows in a previous MySQL operation
  - [mysqli::autocommit](https://www.php.net/manual/en/mysqli.autocommit.php) — Turns on or off auto-committing database modifications
  - [mysqli::begin\_transaction](https://www.php.net/manual/en/mysqli.begin-transaction.php) — Starts a transaction
  - [mysqli::change\_user](https://www.php.net/manual/en/mysqli.change-user.php) — Changes the user of the database connection
  - [mysqli::character\_set\_name](https://www.php.net/manual/en/mysqli.character-set-name.php) — Returns the current character set of the database connection
  - [mysqli::close](https://www.php.net/manual/en/mysqli.close.php) — Closes a previously opened database connection
  - [mysqli::commit](https://www.php.net/manual/en/mysqli.commit.php) — Commits the current transaction
  - [mysqli::$connect\_errno](https://www.php.net/manual/en/mysqli.connect-errno.php) — Returns the error code from last connect call
  - [mysqli::$connect\_error](https://www.php.net/manual/en/mysqli.connect-error.php) — Returns a description of the last connection error
  - [mysqli::\_\_construct](https://www.php.net/manual/en/mysqli.construct.php) — Open a new connection to the MySQL server
  - [mysqli::debug](https://www.php.net/manual/en/mysqli.debug.php) — Performs debugging operations
  - [mysqli::dump\_debug\_info](https://www.php.net/manual/en/mysqli.dump-debug-info.php) — Dump debugging information into the log
  - [mysqli::$errno](https://www.php.net/manual/en/mysqli.errno.php) — Returns the error code for the most recent function call
  - [mysqli::$error](https://www.php.net/manual/en/mysqli.error.php) — Returns a string description of the last error
  - [mysqli::$error\_list](https://www.php.net/manual/en/mysqli.error-list.php) — Returns a list of errors from the last command executed
  - [mysqli::execute\_query](https://www.php.net/manual/en/mysqli.execute-query.php) — Prepares, binds parameters, and executes SQL statement
  - [mysqli::$field\_count](https://www.php.net/manual/en/mysqli.field-count.php) — Returns the number of columns for the most recent query
  - [mysqli::get\_charset](https://www.php.net/manual/en/mysqli.get-charset.php) — Returns a character set object
  - [mysqli::$client\_info](https://www.php.net/manual/en/mysqli.get-client-info.php) — Get MySQL client info
  - [mysqli::$client\_version](https://www.php.net/manual/en/mysqli.get-client-version.php) — Returns the MySQL client version as an integer
  - [mysqli::get\_connection\_stats](https://www.php.net/manual/en/mysqli.get-connection-stats.php) — Returns statistics about the client connection
  - [mysqli::$host\_info](https://www.php.net/manual/en/mysqli.get-host-info.php) — Returns a string representing the type of connection used
  - [mysqli::$protocol\_version](https://www.php.net/manual/en/mysqli.get-proto-info.php) — Returns the version of the MySQL protocol used
  - [mysqli::$server\_info](https://www.php.net/manual/en/mysqli.get-server-info.php) — Returns the version of the MySQL server
  - [mysqli::$server\_version](https://www.php.net/manual/en/mysqli.get-server-version.php) — Returns the version of the MySQL server as an integer
  - [mysqli::get\_warnings](https://www.php.net/manual/en/mysqli.get-warnings.php) — Get result of SHOW WARNINGS
  - [mysqli::$info](https://www.php.net/manual/en/mysqli.info.php) — Retrieves information about the most recently executed query
  - [mysqli::init](https://www.php.net/manual/en/mysqli.init.php) — Initializes MySQLi and returns an object for use with mysqli\_real\_connect()
  - [mysqli::$insert\_id](https://www.php.net/manual/en/mysqli.insert-id.php) — Returns the value generated for an AUTO\_INCREMENT column by the last query
  - [mysqli::kill](https://www.php.net/manual/en/mysqli.kill.php) — Asks the server to kill a MySQL thread
  - [mysqli::more\_results](https://www.php.net/manual/en/mysqli.more-results.php) — Check if there are any more query results from a multi query
  - [mysqli::multi\_query](https://www.php.net/manual/en/mysqli.multi-query.php) — Performs one or more queries on the database
  - [mysqli::next\_result](https://www.php.net/manual/en/mysqli.next-result.php) — Prepare next result from multi\_query
  - [mysqli::options](https://www.php.net/manual/en/mysqli.options.php) — Set options
  - [mysqli::ping](https://www.php.net/manual/en/mysqli.ping.php) — Pings a server connection, or tries to reconnect if the connection has gone down
  - [mysqli::poll](https://www.php.net/manual/en/mysqli.poll.php) — Poll connections
  - [mysqli::prepare](https://www.php.net/manual/en/mysqli.prepare.php) — Prepares an SQL statement for execution
  - [mysqli::query](https://www.php.net/manual/en/mysqli.query.php) — Performs a query on the database
  - [mysqli::real\_connect](https://www.php.net/manual/en/mysqli.real-connect.php) — Opens a connection to a mysql server
  - [mysqli::real\_escape\_string](https://www.php.net/manual/en/mysqli.real-escape-string.php) — Escapes special characters in a string for use in an SQL statement, taking into account the current charset of the connection
  - [mysqli::real\_query](https://www.php.net/manual/en/mysqli.real-query.php) — Execute an SQL query
  - [mysqli::reap\_async\_query](https://www.php.net/manual/en/mysqli.reap-async-query.php) — Get result from async query
  - [mysqli::refresh](https://www.php.net/manual/en/mysqli.refresh.php) — Refreshes
  - [mysqli::release\_savepoint](https://www.php.net/manual/en/mysqli.release-savepoint.php) — Removes the named savepoint from the set of savepoints of the current transaction
  - [mysqli::rollback](https://www.php.net/manual/en/mysqli.rollback.php) — Rolls back current transaction
  - [mysqli::savepoint](https://www.php.net/manual/en/mysqli.savepoint.php) — Set a named transaction savepoint
  - [mysqli::select\_db](https://www.php.net/manual/en/mysqli.select-db.php) — Selects the default database for database queries
  - [mysqli::set\_charset](https://www.php.net/manual/en/mysqli.set-charset.php) — Sets the client character set
  - [mysqli::$sqlstate](https://www.php.net/manual/en/mysqli.sqlstate.php) — Returns the SQLSTATE error from previous MySQL operation
  - [mysqli::ssl\_set](https://www.php.net/manual/en/mysqli.ssl-set.php) — Used for establishing secure connections using SSL
  - [mysqli::stat](https://www.php.net/manual/en/mysqli.stat.php) — Gets the current system status
  - [mysqli::stmt\_init](https://www.php.net/manual/en/mysqli.stmt-init.php) — Initializes a statement and returns an object for use with mysqli\_stmt\_prepare
  - [mysqli::store\_result](https://www.php.net/manual/en/mysqli.store-result.php) — Transfers a result set from the last query
  - [mysqli::$thread\_id](https://www.php.net/manual/en/mysqli.thread-id.php) — Returns the thread ID for the current connection
  - [mysqli::thread\_safe](https://www.php.net/manual/en/mysqli.thread-safe.php) — Returns whether thread safety is given or not
  - [mysqli::use\_result](https://www.php.net/manual/en/mysqli.use-result.php) — Initiate a result set retrieval
  - [mysqli::$warning\_count](https://www.php.net/manual/en/mysqli.warning-count.php) — Returns the number of warnings generated by the most recently executed query
- [mysqli\_stmt](https://www.php.net/manual/en/class.mysqli-stmt.php) — The mysqli\_stmt class
  - [mysqli\_stmt::$affected\_rows](https://www.php.net/manual/en/mysqli-stmt.affected-rows.php) — Returns the total number of rows changed, deleted, inserted, or
     matched by the last statement executed
  - [mysqli\_stmt::attr\_get](https://www.php.net/manual/en/mysqli-stmt.attr-get.php) — Used to get the current value of a statement attribute
  - [mysqli\_stmt::attr\_set](https://www.php.net/manual/en/mysqli-stmt.attr-set.php) — Used to modify the behavior of a prepared statement
  - [mysqli\_stmt::bind\_param](https://www.php.net/manual/en/mysqli-stmt.bind-param.php) — Binds variables to a prepared statement as parameters
  - [mysqli\_stmt::bind\_result](https://www.php.net/manual/en/mysqli-stmt.bind-result.php) — Binds variables to a prepared statement for result storage
  - [mysqli\_stmt::close](https://www.php.net/manual/en/mysqli-stmt.close.php) — Closes a prepared statement
  - [mysqli\_stmt::\_\_construct](https://www.php.net/manual/en/mysqli-stmt.construct.php) — Constructs a new mysqli\_stmt object
  - [mysqli\_stmt::data\_seek](https://www.php.net/manual/en/mysqli-stmt.data-seek.php) — Adjusts the result pointer to an arbitrary row in the buffered result
  - [mysqli\_stmt::$errno](https://www.php.net/manual/en/mysqli-stmt.errno.php) — Returns the error code for the most recent statement call
  - [mysqli\_stmt::$error](https://www.php.net/manual/en/mysqli-stmt.error.php) — Returns a string description for last statement error
  - [mysqli\_stmt::$error\_list](https://www.php.net/manual/en/mysqli-stmt.error-list.php) — Returns a list of errors from the last statement executed
  - [mysqli\_stmt::execute](https://www.php.net/manual/en/mysqli-stmt.execute.php) — Executes a prepared statement
  - [mysqli\_stmt::fetch](https://www.php.net/manual/en/mysqli-stmt.fetch.php) — Fetch results from a prepared statement into the bound variables
  - [mysqli\_stmt::$field\_count](https://www.php.net/manual/en/mysqli-stmt.field-count.php) — Returns the number of columns in the given statement
  - [mysqli\_stmt::free\_result](https://www.php.net/manual/en/mysqli-stmt.free-result.php) — Frees stored result memory for the given statement handle
  - [mysqli\_stmt::get\_result](https://www.php.net/manual/en/mysqli-stmt.get-result.php) — Gets a result set from a prepared statement as a mysqli\_result object
  - [mysqli\_stmt::get\_warnings](https://www.php.net/manual/en/mysqli-stmt.get-warnings.php) — Get result of SHOW WARNINGS
  - [mysqli\_stmt::$insert\_id](https://www.php.net/manual/en/mysqli-stmt.insert-id.php) — Get the ID generated from the previous INSERT operation
  - [mysqli\_stmt::more\_results](https://www.php.net/manual/en/mysqli-stmt.more-results.php) — Check if there are more query results from a multiple query
  - [mysqli\_stmt::next\_result](https://www.php.net/manual/en/mysqli-stmt.next-result.php) — Reads the next result from a multiple query
  - [mysqli\_stmt::$num\_rows](https://www.php.net/manual/en/mysqli-stmt.num-rows.php) — Returns the number of rows fetched from the server
  - [mysqli\_stmt::$param\_count](https://www.php.net/manual/en/mysqli-stmt.param-count.php) — Returns the number of parameters for the given statement
  - [mysqli\_stmt::prepare](https://www.php.net/manual/en/mysqli-stmt.prepare.php) — Prepares an SQL statement for execution
  - [mysqli\_stmt::reset](https://www.php.net/manual/en/mysqli-stmt.reset.php) — Resets a prepared statement
  - [mysqli\_stmt::result\_metadata](https://www.php.net/manual/en/mysqli-stmt.result-metadata.php) — Returns result set metadata from a prepared statement
  - [mysqli\_stmt::send\_long\_data](https://www.php.net/manual/en/mysqli-stmt.send-long-data.php) — Send data in blocks
  - [mysqli\_stmt::$sqlstate](https://www.php.net/manual/en/mysqli-stmt.sqlstate.php) — Returns SQLSTATE error from previous statement operation
  - [mysqli\_stmt::store\_result](https://www.php.net/manual/en/mysqli-stmt.store-result.php) — Stores a result set in an internal buffer
- [mysqli\_result](https://www.php.net/manual/en/class.mysqli-result.php) — The mysqli\_result class
  - [mysqli\_result::\_\_construct](https://www.php.net/manual/en/mysqli-result.construct.php) — Constructs a mysqli\_result object
  - [mysqli\_result::$current\_field](https://www.php.net/manual/en/mysqli-result.current-field.php) — Get current field offset of a result pointer
  - [mysqli\_result::data\_seek](https://www.php.net/manual/en/mysqli-result.data-seek.php) — Adjusts the result pointer to an arbitrary row in the result
  - [mysqli\_result::fetch\_all](https://www.php.net/manual/en/mysqli-result.fetch-all.php) — Fetch all result rows as an associative array, a numeric array, or both
  - [mysqli\_result::fetch\_array](https://www.php.net/manual/en/mysqli-result.fetch-array.php) — Fetch the next row of a result set as an associative, a numeric array, or both
  - [mysqli\_result::fetch\_assoc](https://www.php.net/manual/en/mysqli-result.fetch-assoc.php) — Fetch the next row of a result set as an associative array
  - [mysqli\_result::fetch\_column](https://www.php.net/manual/en/mysqli-result.fetch-column.php) — Fetch a single column from the next row of a result set
  - [mysqli\_result::fetch\_field](https://www.php.net/manual/en/mysqli-result.fetch-field.php) — Returns the next field in the result set
  - [mysqli\_result::fetch\_field\_direct](https://www.php.net/manual/en/mysqli-result.fetch-field-direct.php) — Fetch meta-data for a single field
  - [mysqli\_result::fetch\_fields](https://www.php.net/manual/en/mysqli-result.fetch-fields.php) — Returns an array of objects representing the fields in a result set
  - [mysqli\_result::fetch\_object](https://www.php.net/manual/en/mysqli-result.fetch-object.php) — Fetch the next row of a result set as an object
  - [mysqli\_result::fetch\_row](https://www.php.net/manual/en/mysqli-result.fetch-row.php) — Fetch the next row of a result set as an enumerated array
  - [mysqli\_result::$field\_count](https://www.php.net/manual/en/mysqli-result.field-count.php) — Gets the number of fields in the result set
  - [mysqli\_result::field\_seek](https://www.php.net/manual/en/mysqli-result.field-seek.php) — Set result pointer to a specified field offset
  - [mysqli\_result::free](https://www.php.net/manual/en/mysqli-result.free.php) — Frees the memory associated with a result
  - [mysqli\_result::getIterator](https://www.php.net/manual/en/mysqli-result.getiterator.php) — Retrieve an external iterator
  - [mysqli\_result::$lengths](https://www.php.net/manual/en/mysqli-result.lengths.php) — Returns the lengths of the columns of the current row in the result set
  - [mysqli\_result::$num\_rows](https://www.php.net/manual/en/mysqli-result.num-rows.php) — Gets the number of rows in the result set
- [mysqli\_driver](https://www.php.net/manual/en/class.mysqli-driver.php) — The mysqli\_driver class
  - [mysqli\_driver::embedded\_server\_end](https://www.php.net/manual/en/mysqli-driver.embedded-server-end.php) — Stop embedded server
  - [mysqli\_driver::embedded\_server\_start](https://www.php.net/manual/en/mysqli-driver.embedded-server-start.php) — Initialize and start embedded server
  - [mysqli\_driver::$report\_mode](https://www.php.net/manual/en/mysqli-driver.report-mode.php) — Sets mysqli error reporting mode
- [mysqli\_warning](https://www.php.net/manual/en/class.mysqli-warning.php) — The mysqli\_warning class
  - [mysqli\_warning::\_\_construct](https://www.php.net/manual/en/mysqli-warning.construct.php) — Private constructor to disallow direct instantiation
  - [mysqli\_warning::next](https://www.php.net/manual/en/mysqli-warning.next.php) — Fetch next warning
- [mysqli\_sql\_exception](https://www.php.net/manual/en/class.mysqli-sql-exception.php) — The mysqli\_sql\_exception class
  - [mysqli\_sql\_exception::getSqlState](https://www.php.net/manual/en/mysqli-sql-exception.getsqlstate.php) — Returns the SQLSTATE error code
- [Aliases and deprecated Mysqli Functions](https://www.php.net/manual/en/ref.mysqli.php)
  - [mysqli\_connect](https://www.php.net/manual/en/function.mysqli-connect.php) — Alias of mysqli::\_\_construct
  - [mysqli::escape\_string](https://www.php.net/manual/en/function.mysqli-escape-string.php) — Alias of mysqli\_real\_escape\_string
  - [mysqli\_execute](https://www.php.net/manual/en/function.mysqli-execute.php) — Alias of mysqli\_stmt\_execute
  - [mysqli\_get\_client\_stats](https://www.php.net/manual/en/function.mysqli-get-client-stats.php) — Returns client per-process statistics
  - [mysqli\_get\_links\_stats](https://www.php.net/manual/en/function.mysqli-get-links-stats.php) — Return information about open and cached links
  - [mysqli\_report](https://www.php.net/manual/en/function.mysqli-report.php) — Alias of mysqli\_driver->report\_mode
  - [mysqli::set\_opt](https://www.php.net/manual/en/function.mysqli-set-opt.php) — Alias of mysqli\_options
- [Changelog](https://www.php.net/manual/en/changelog.mysqli.php)

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/mysqli/book.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Fbook.mysqli%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=book.mysqli&repo=en&redirect=https://www.php.net/manual/en/book.mysqli.php)

### User Contributed Notes

There are no user contributed notes for this page.

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google