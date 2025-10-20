---
url: https://www.php.net/manual/en/function.sqlsrv-rollback.php
scraped_at: 2025-10-20T02:59:59.180Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# sqlsrv\_rollback

(No version information available, might only be in Git)

sqlsrv\_rollback — Rolls back a transaction that was begun with
[sqlsrv\_begin\_transaction()](https://www.php.net/manual/en/function.sqlsrv-begin-transaction.php)

### Description [¶](https://www.php.net/manual/en/function.sqlsrv-rollback.php\#refsect1-function.sqlsrv-rollback-description)

**sqlsrv\_rollback**([resource](https://www.php.net/manual/en/language.types.resource.php) `$conn`): [bool](https://www.php.net/manual/en/language.types.boolean.php)

Rolls back a transaction that was begun with [sqlsrv\_begin\_transaction()](https://www.php.net/manual/en/function.sqlsrv-begin-transaction.php)
and returns the connection to auto-commit mode.


### Parameters [¶](https://www.php.net/manual/en/function.sqlsrv-rollback.php\#refsect1-function.sqlsrv-rollback-parameters)

`conn`

The connection resource returned by a call to [sqlsrv\_connect()](https://www.php.net/manual/en/function.sqlsrv-connect.php).


### Return Values [¶](https://www.php.net/manual/en/function.sqlsrv-rollback.php\#refsect1-function.sqlsrv-rollback-returnvalues)

Returns **`[true](https://www.php.net/manual/en/reserved.constants.php#constant.true)`** on success or **`[false](https://www.php.net/manual/en/reserved.constants.php#constant.false)`** on failure.


### Examples [¶](https://www.php.net/manual/en/function.sqlsrv-rollback.php\#refsect1-function.sqlsrv-rollback-examples)

**Example #1 **sqlsrv\_rollback()** example**

The following example demonstrates how to use [sqlsrv\_begin\_transaction()](https://www.php.net/manual/en/function.sqlsrv-begin-transaction.php)
together with [sqlsrv\_commit()](https://www.php.net/manual/en/function.sqlsrv-commit.php) and **sqlsrv\_rollback()**.


`<?php
$serverName = "serverName\sqlexpress";
$connectionInfo = array( "Database"=>"dbName", "UID"=>"userName", "PWD"=>"password");
$conn = sqlsrv_connect( $serverName, $connectionInfo);
if( $conn === false ) {
    die( print_r( sqlsrv_errors(), true ));
}
/* Begin the transaction. */
if ( sqlsrv_begin_transaction( $conn ) === false ) {
     die( print_r( sqlsrv_errors(), true ));
}
/* Initialize parameter values. */
$orderId = 1; $qty = 10; $productId = 100;
/* Set up and execute the first query. */
$sql1 = "INSERT INTO OrdersTable (ID, Quantity, ProductID)
         VALUES (?, ?, ?)";
$params1 = array( $orderId, $qty, $productId );
$stmt1 = sqlsrv_query( $conn, $sql1, $params1 );
/* Set up and execute the second query. */
$sql2 = "UPDATE InventoryTable
         SET Quantity = (Quantity - ?)
         WHERE ProductID = ?";
$params2 = array($qty, $productId);
$stmt2 = sqlsrv_query( $conn, $sql2, $params2 );
/* If both queries were successful, commit the transaction. */
/* Otherwise, rollback the transaction. */
if( $stmt1 && $stmt2 ) {
     sqlsrv_commit( $conn );
     echo "Transaction committed.<br />";
} else {
     sqlsrv_rollback( $conn );
     echo "Transaction rolled back.<br />";
}
?>`

### See Also [¶](https://www.php.net/manual/en/function.sqlsrv-rollback.php\#refsect1-function.sqlsrv-rollback-seealso)

- [sqlsrv\_begin\_transaction()](https://www.php.net/manual/en/function.sqlsrv-begin-transaction.php) \- Begins a database transaction
- [sqlsrv\_commit()](https://www.php.net/manual/en/function.sqlsrv-commit.php) \- Commits a transaction that was begun with sqlsrv\_begin\_transaction

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/sqlsrv/functions/sqlsrv-rollback.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Ffunction.sqlsrv-rollback%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=function.sqlsrv-rollback&repo=en&redirect=https://www.php.net/manual/en/function.sqlsrv-rollback.php)

### User Contributed Notes

There are no user contributed notes for this page.

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google