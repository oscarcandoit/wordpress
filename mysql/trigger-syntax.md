---
url: https://dev.mysql.com/doc/refman/8.0/en/trigger-syntax.html
scraped_at: 2025-10-20T03:05:48.501Z
---

[Skip to Main Content](https://dev.mysql.com/doc/refman/8.0/en/trigger-syntax.html#main)

[Hide Sidebar](https://dev.mysql.com/doc/refman/8.0/en/trigger-syntax.html "Hide Sidebar")

[Previous: Using Triggers](https://dev.mysql.com/doc/refman/8.0/en/triggers.html "Previous: Using Triggers")[Start](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start")[Up: Using Triggers](https://dev.mysql.com/doc/refman/8.0/en/triggers.html "Up: Using Triggers")[Next: Trigger Metadata](https://dev.mysql.com/doc/refman/8.0/en/trigger-metadata.html "Next: Trigger Metadata")

[Documentation Home](https://dev.mysql.com/doc/)

* * *

MySQL 8.0 Reference Manual

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/trigger-syntax.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/trigger-syntax.html)

[PDF (US Ltr)](https://downloads.mysql.com/docs/refman-8.0-en.pdf)
\- 43.3Mb

[PDF (A4)](https://downloads.mysql.com/docs/refman-8.0-en.a4.pdf)
\- 43.4Mb

[Man Pages (TGZ)](https://downloads.mysql.com/docs/refman-8.0-en.man-gpl.tar.gz)
\- 297.2Kb

[Man Pages (Zip)](https://downloads.mysql.com/docs/refman-8.0-en.man-gpl.zip)
\- 402.4Kb

[Info (Gzip)](https://downloads.mysql.com/docs/mysql-8.0.info.gz)
\- 4.3Mb

[Info (Zip)](https://downloads.mysql.com/docs/mysql-8.0.info.zip)
\- 4.3Mb

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/trigger-syntax.html)

[MySQL Backup and Recovery](https://dev.mysql.com/doc/mysql-backup-excerpt/8.0/en/)

[MySQL Globalization](https://dev.mysql.com/doc/mysql-g11n-excerpt/8.0/en/)

[MySQL Information Schema](https://dev.mysql.com/doc/mysql-infoschema-excerpt/8.0/en/)

[MySQL Installation Guide](https://dev.mysql.com/doc/mysql-installation-excerpt/8.0/en/)

[Security in MySQL](https://dev.mysql.com/doc/mysql-security-excerpt/8.0/en/)

[Starting and Stopping MySQL](https://dev.mysql.com/doc/mysql-startstop-excerpt/8.0/en/)

[MySQL and Linux/Unix](https://dev.mysql.com/doc/mysql-linuxunix-excerpt/8.0/en/)

[MySQL and Windows](https://dev.mysql.com/doc/mysql-windows-excerpt/8.0/en/)

[MySQL and macOS](https://dev.mysql.com/doc/mysql-macos-excerpt/8.0/en/)

[MySQL and Solaris](https://dev.mysql.com/doc/mysql-solaris-excerpt/8.0/en/)

[Building MySQL from Source](https://dev.mysql.com/doc/mysql-sourcebuild-excerpt/8.0/en/)

[MySQL Restrictions and Limitations](https://dev.mysql.com/doc/mysql-reslimits-excerpt/8.0/en/)

[MySQL Partitioning](https://dev.mysql.com/doc/mysql-partitioning-excerpt/8.0/en/)

[MySQL Tutorial](https://dev.mysql.com/doc/mysql-tutorial-excerpt/8.0/en/)

[MySQL Performance Schema](https://dev.mysql.com/doc/mysql-perfschema-excerpt/8.0/en/)

[MySQL Replication](https://dev.mysql.com/doc/mysql-replication-excerpt/8.0/en/)

[Using the MySQL Yum Repository](https://dev.mysql.com/doc/mysql-repo-excerpt/8.0/en/)

[MySQL NDB Cluster 8.0](https://dev.mysql.com/doc/mysql-cluster-excerpt/8.0/en/)

[version 8.0](https://dev.mysql.com/doc/refman/8.0/en/trigger-syntax.html)

[9.4](https://dev.mysql.com/doc/refman/9.4/en/trigger-syntax.html)

[9.3](https://dev.mysql.com/doc/refman/9.3/en/trigger-syntax.html)

[9.2](https://dev.mysql.com/doc/refman/9.2/en/trigger-syntax.html)

[9.1](https://dev.mysql.com/doc/refman/9.1/en/trigger-syntax.html)

[9.0](https://dev.mysql.com/doc/refman/9.0/en/trigger-syntax.html)

[8.4\\
current](https://dev.mysql.com/doc/refman/8.4/en/trigger-syntax.html)

[5.7](https://dev.mysql.com/doc/refman/5.7/en/trigger-syntax.html)

[8.0 \\
Japanese](https://dev.mysql.com/doc/refman/8.0/ja/trigger-syntax.html)

[Show Sidebar](https://dev.mysql.com/doc/refman/8.0/en/trigger-syntax.html "Show Sidebar")

[MySQL 8.0 Reference Manual](https://dev.mysql.com/doc/refman/8.0/en/)  /
[...](https://dev.mysql.com/doc/refman/8.0/en/trigger-syntax.html)  / [Stored Objects](https://dev.mysql.com/doc/refman/8.0/en/stored-objects.html)  /
[Using Triggers](https://dev.mysql.com/doc/refman/8.0/en/triggers.html)  /

Trigger Syntax and Examples


### 27.3.1 Trigger Syntax and Examples

To create a trigger or drop a trigger, use the
[`CREATE TRIGGER`](https://dev.mysql.com/doc/refman/8.0/en/create-trigger.html "15.1.22 CREATE TRIGGER Statement") or
[`DROP TRIGGER`](https://dev.mysql.com/doc/refman/8.0/en/drop-trigger.html "15.1.34 DROP TRIGGER Statement") statement, described
in [Section 15.1.22, “CREATE TRIGGER Statement”](https://dev.mysql.com/doc/refman/8.0/en/create-trigger.html "15.1.22 CREATE TRIGGER Statement"), and
[Section 15.1.34, “DROP TRIGGER Statement”](https://dev.mysql.com/doc/refman/8.0/en/drop-trigger.html "15.1.34 DROP TRIGGER Statement").


Here is a simple example that associates a trigger with a table,
to activate for [`INSERT`](https://dev.mysql.com/doc/refman/8.0/en/insert.html "15.2.7 INSERT Statement") operations.
The trigger acts as an accumulator, summing the values inserted
into one of the columns of the table.


```sql
mysql> CREATE TABLE account (acct_num INT, amount DECIMAL(10,2));
Query OK, 0 rows affected (0.03 sec)

mysql> CREATE TRIGGER ins_sum BEFORE INSERT ON account
       FOR EACH ROW SET @sum = @sum + NEW.amount;
Query OK, 0 rows affected (0.01 sec)
```

The [`CREATE TRIGGER`](https://dev.mysql.com/doc/refman/8.0/en/create-trigger.html "15.1.22 CREATE TRIGGER Statement") statement
creates a trigger named `ins_sum` that is
associated with the `account` table. It also
includes clauses that specify the trigger action time, the
triggering event, and what to do when the trigger activates:

- The keyword `BEFORE` indicates the trigger
action time. In this case, the trigger activates before each
row inserted into the table. The other permitted keyword here
is `AFTER`.


- The keyword `INSERT` indicates the trigger
event; that is, the type of operation that activates the
trigger. In the example, [`INSERT`](https://dev.mysql.com/doc/refman/8.0/en/insert.html "15.2.7 INSERT Statement")
operations cause trigger activation. You can also create
triggers for [`DELETE`](https://dev.mysql.com/doc/refman/8.0/en/delete.html "15.2.2 DELETE Statement") and
[`UPDATE`](https://dev.mysql.com/doc/refman/8.0/en/update.html "15.2.17 UPDATE Statement") operations.


- The statement following `FOR EACH ROW`
defines the trigger body; that is, the statement to execute
each time the trigger activates, which occurs once for each
row affected by the triggering event. In the example, the
trigger body is a simple
[`SET`](https://dev.mysql.com/doc/refman/8.0/en/set-variable.html "15.7.6.1 SET Syntax for Variable Assignment")
that accumulates into a user variable the values inserted into
the `amount` column. The statement refers to
the column as `NEW.amount` which means
“the value of the `amount` column to be
inserted into the new row.”


To use the trigger, set the accumulator variable to zero, execute
an [`INSERT`](https://dev.mysql.com/doc/refman/8.0/en/insert.html "15.2.7 INSERT Statement") statement, and then see
what value the variable has afterward:


```sql
mysql> SET @sum = 0;
mysql> INSERT INTO account VALUES(137,14.98),(141,1937.50),(97,-100.00);
mysql> SELECT @sum AS 'Total amount inserted';
+-----------------------+
| Total amount inserted |
+-----------------------+
|               1852.48 |
+-----------------------+
```

In this case, the value of `@sum` after the
[`INSERT`](https://dev.mysql.com/doc/refman/8.0/en/insert.html "15.2.7 INSERT Statement") statement has executed is
`14.98 + 1937.50 - 100`, or
`1852.48`.


To destroy the trigger, use a [`DROP\\
      TRIGGER`](https://dev.mysql.com/doc/refman/8.0/en/drop-trigger.html "15.1.34 DROP TRIGGER Statement") statement. You must specify the schema name if
the trigger is not in the default schema:


```sql
mysql> DROP TRIGGER test.ins_sum;
```

If you drop a table, any triggers for the table are also dropped.


Trigger names exist in the schema namespace, meaning that all
triggers must have unique names within a schema. Triggers in
different schemas can have the same name.


It is possible to define multiple triggers for a given table that
have the same trigger event and action time. For example, you can
have two `BEFORE UPDATE` triggers for a table. By
default, triggers that have the same trigger event and action time
activate in the order they were created. To affect trigger order,
specify a clause after `FOR EACH ROW` that
indicates `FOLLOWS` or
`PRECEDES` and the name of an existing trigger
that also has the same trigger event and action time. With
`FOLLOWS`, the new trigger activates after the
existing trigger. With `PRECEDES`, the new
trigger activates before the existing trigger.


For example, the following trigger definition defines another
`BEFORE INSERT` trigger for the
`account` table:


```sql
mysql> CREATE TRIGGER ins_transaction BEFORE INSERT ON account
       FOR EACH ROW PRECEDES ins_sum
       SET
       @deposits = @deposits + IF(NEW.amount>0,NEW.amount,0),
       @withdrawals = @withdrawals + IF(NEW.amount<0,-NEW.amount,0);
Query OK, 0 rows affected (0.01 sec)
```

This trigger, `ins_transaction`, is similar to
`ins_sum` but accumulates deposits and
withdrawals separately. It has a `PRECEDES`
clause that causes it to activate before
`ins_sum`; without that clause, it would activate
after `ins_sum` because it is created after
`ins_sum`.


Within the trigger body, the `OLD` and
`NEW` keywords enable you to access columns in
the rows affected by a trigger. `OLD` and
`NEW` are MySQL extensions to triggers; they are
not case-sensitive.


In an `INSERT` trigger, only
`NEW.col_name` can be
used; there is no old row. In a `DELETE` trigger,
only `OLD.col_name`
can be used; there is no new row. In an `UPDATE`
trigger, you can use
`OLD.col_name` to
refer to the columns of a row before it is updated and
`NEW.col_name` to
refer to the columns of the row after it is updated.


A column named with `OLD` is read only. You can
refer to it (if you have the [`SELECT`](https://dev.mysql.com/doc/refman/8.0/en/select.html "15.2.13 SELECT Statement")
privilege), but not modify it. You can refer to a column named
with `NEW` if you have the
[`SELECT`](https://dev.mysql.com/doc/refman/8.0/en/privileges-provided.html#priv_select) privilege for it. In a
`BEFORE` trigger, you can also change its value
with `SET NEW.col_name =
      value` if you have the
[`UPDATE`](https://dev.mysql.com/doc/refman/8.0/en/privileges-provided.html#priv_update) privilege for it. This means
you can use a trigger to modify the values to be inserted into a
new row or used to update a row. (Such a `SET`
statement has no effect in an `AFTER` trigger
because the row change has already occurred.)


In a `BEFORE` trigger, the `NEW`
value for an `AUTO_INCREMENT` column is 0, not
the sequence number that is generated automatically when the new
row actually is inserted.


By using the [`BEGIN ...\\
      END`](https://dev.mysql.com/doc/refman/8.0/en/begin-end.html "15.6.1 BEGIN ... END Compound Statement") construct, you can define a trigger that executes
multiple statements. Within the `BEGIN` block,
you also can use other syntax that is permitted within stored
routines such as conditionals and loops. However, just as for
stored routines, if you use the [**mysql**](https://dev.mysql.com/doc/refman/8.0/en/mysql.html "6.5.1 mysql — The MySQL Command-Line Client") program
to define a trigger that executes multiple statements, it is
necessary to redefine the [**mysql**](https://dev.mysql.com/doc/refman/8.0/en/mysql.html "6.5.1 mysql — The MySQL Command-Line Client") statement
delimiter so that you can use the `;` statement
delimiter within the trigger definition. The following example
illustrates these points. It defines an `UPDATE`
trigger that checks the new value to be used for updating each
row, and modifies the value to be within the range from 0 to 100.
This must be a `BEFORE` trigger because the value
must be checked before it is used to update the row:


```sql
mysql> delimiter //
mysql> CREATE TRIGGER upd_check BEFORE UPDATE ON account
       FOR EACH ROW
       BEGIN
           IF NEW.amount < 0 THEN
               SET NEW.amount = 0;
           ELSEIF NEW.amount > 100 THEN
               SET NEW.amount = 100;
           END IF;
       END;//
mysql> delimiter ;
```

It can be easier to define a stored procedure separately and then
invoke it from the trigger using a simple
[`CALL`](https://dev.mysql.com/doc/refman/8.0/en/call.html "15.2.1 CALL Statement") statement. This is also
advantageous if you want to execute the same code from within
several triggers.


There are limitations on what can appear in statements that a
trigger executes when activated:

- The trigger cannot use the [`CALL`](https://dev.mysql.com/doc/refman/8.0/en/call.html "15.2.1 CALL Statement")
statement to invoke stored procedures that return data to the
client or that use dynamic SQL. (Stored procedures are
permitted to return data to the trigger through
`OUT` or `INOUT`
parameters.)


- The trigger cannot use statements that explicitly or
implicitly begin or end a transaction, such as
[`START\\
            TRANSACTION`](https://dev.mysql.com/doc/refman/8.0/en/commit.html "15.3.1 START TRANSACTION, COMMIT, and ROLLBACK Statements"), [`COMMIT`](https://dev.mysql.com/doc/refman/8.0/en/commit.html "15.3.1 START TRANSACTION, COMMIT, and ROLLBACK Statements"),
or [`ROLLBACK`](https://dev.mysql.com/doc/refman/8.0/en/commit.html "15.3.1 START TRANSACTION, COMMIT, and ROLLBACK Statements").
( [`ROLLBACK to\\
            SAVEPOINT`](https://dev.mysql.com/doc/refman/8.0/en/commit.html "15.3.1 START TRANSACTION, COMMIT, and ROLLBACK Statements") is permitted because it does not end a
transaction.).


See also [Section 27.8, “Restrictions on Stored Programs”](https://dev.mysql.com/doc/refman/8.0/en/stored-program-restrictions.html "27.8 Restrictions on Stored Programs").


MySQL handles errors during trigger execution as follows:

- If a `BEFORE` trigger fails, the operation on
the corresponding row is not performed.


- A `BEFORE` trigger is activated by the
_attempt_ to insert or modify the row,
regardless of whether the attempt subsequently succeeds.


- An `AFTER` trigger is executed only if any
`BEFORE` triggers and the row operation
execute successfully.


- An error during either a `BEFORE` or
`AFTER` trigger results in failure of the
entire statement that caused trigger invocation.


- For transactional tables, failure of a statement should cause
rollback of all changes performed by the statement. Failure of
a trigger causes the statement to fail, so trigger failure
also causes rollback. For nontransactional tables, such
rollback cannot be done, so although the statement fails, any
changes performed prior to the point of the error remain in
effect.


Triggers can contain direct references to tables by name, such as
the trigger named `testref` shown in this
example:


```sql
CREATE TABLE test1(a1 INT);
CREATE TABLE test2(a2 INT);
CREATE TABLE test3(a3 INT NOT NULL AUTO_INCREMENT PRIMARY KEY);
CREATE TABLE test4(
  a4 INT NOT NULL AUTO_INCREMENT PRIMARY KEY,
  b4 INT DEFAULT 0
);

delimiter |

CREATE TRIGGER testref BEFORE INSERT ON test1
  FOR EACH ROW
  BEGIN
    INSERT INTO test2 SET a2 = NEW.a1;
    DELETE FROM test3 WHERE a3 = NEW.a1;
    UPDATE test4 SET b4 = b4 + 1 WHERE a4 = NEW.a1;
  END;
|

delimiter ;

INSERT INTO test3 (a3) VALUES
  (NULL), (NULL), (NULL), (NULL), (NULL),
  (NULL), (NULL), (NULL), (NULL), (NULL);

INSERT INTO test4 (a4) VALUES
  (0), (0), (0), (0), (0), (0), (0), (0), (0), (0);
```

Suppose that you insert the following values into table
`test1` as shown here:


```sql
mysql> INSERT INTO test1 VALUES
       (1), (3), (1), (7), (1), (8), (4), (4);
Query OK, 8 rows affected (0.01 sec)
Records: 8  Duplicates: 0  Warnings: 0
```

As a result, the four tables contain the following data:


```sql
mysql> SELECT * FROM test1;
+------+
| a1   |
+------+
|    1 |
|    3 |
|    1 |
|    7 |
|    1 |
|    8 |
|    4 |
|    4 |
+------+
8 rows in set (0.00 sec)

mysql> SELECT * FROM test2;
+------+
| a2   |
+------+
|    1 |
|    3 |
|    1 |
|    7 |
|    1 |
|    8 |
|    4 |
|    4 |
+------+
8 rows in set (0.00 sec)

mysql> SELECT * FROM test3;
+----+
| a3 |
+----+
|  2 |
|  5 |
|  6 |
|  9 |
| 10 |
+----+
5 rows in set (0.00 sec)

mysql> SELECT * FROM test4;
+----+------+
| a4 | b4   |
+----+------+
|  1 |    3 |
|  2 |    0 |
|  3 |    1 |
|  4 |    2 |
|  5 |    0 |
|  6 |    0 |
|  7 |    1 |
|  8 |    1 |
|  9 |    0 |
| 10 |    0 |
+----+------+
10 rows in set (0.00 sec)
```

[PREV](https://dev.mysql.com/doc/refman/8.0/en/triggers.html "Previous: Using Triggers") [HOME](https://dev.mysql.com/doc/refman/8.0/en/index.html "Start") [UP](https://dev.mysql.com/doc/refman/8.0/en/triggers.html "Up: Using Triggers") [NEXT](https://dev.mysql.com/doc/refman/8.0/en/trigger-metadata.html "Next: Trigger Metadata")

[Related Documentation](https://dev.mysql.com/doc/refman/8.0/en/trigger-syntax.html)

[MySQL 8.0 Release Notes](https://dev.mysql.com/doc/relnotes/mysql/8.0/en/)

[MySQL 8.0 Source Code Documentation](https://dev.mysql.com/doc/dev/mysql-server/latest/)

[Download\\
this Manual](https://dev.mysql.com/doc/refman/8.0/en/trigger-syntax.html)

[PDF (US Ltr)](https://downloads.mysql.com/docs/refman-8.0-en.pdf)
\- 43.3Mb

[PDF (A4)](https://downloads.mysql.com/docs/refman-8.0-en.a4.pdf)
\- 43.4Mb

[Man Pages (TGZ)](https://downloads.mysql.com/docs/refman-8.0-en.man-gpl.tar.gz)
\- 297.2Kb

[Man Pages (Zip)](https://downloads.mysql.com/docs/refman-8.0-en.man-gpl.zip)
\- 402.4Kb

[Info (Gzip)](https://downloads.mysql.com/docs/mysql-8.0.info.gz)
\- 4.3Mb

[Info (Zip)](https://downloads.mysql.com/docs/mysql-8.0.info.zip)
\- 4.3Mb

[Excerpts from this Manual](https://dev.mysql.com/doc/refman/8.0/en/trigger-syntax.html)

[MySQL Backup and Recovery](https://dev.mysql.com/doc/mysql-backup-excerpt/8.0/en/)

[MySQL Globalization](https://dev.mysql.com/doc/mysql-g11n-excerpt/8.0/en/)

[MySQL Information Schema](https://dev.mysql.com/doc/mysql-infoschema-excerpt/8.0/en/)

[MySQL Installation Guide](https://dev.mysql.com/doc/mysql-installation-excerpt/8.0/en/)

[Security in MySQL](https://dev.mysql.com/doc/mysql-security-excerpt/8.0/en/)

[Starting and Stopping MySQL](https://dev.mysql.com/doc/mysql-startstop-excerpt/8.0/en/)

[MySQL and Linux/Unix](https://dev.mysql.com/doc/mysql-linuxunix-excerpt/8.0/en/)

[MySQL and Windows](https://dev.mysql.com/doc/mysql-windows-excerpt/8.0/en/)

[MySQL and macOS](https://dev.mysql.com/doc/mysql-macos-excerpt/8.0/en/)

[MySQL and Solaris](https://dev.mysql.com/doc/mysql-solaris-excerpt/8.0/en/)

[Building MySQL from Source](https://dev.mysql.com/doc/mysql-sourcebuild-excerpt/8.0/en/)

[MySQL Restrictions and Limitations](https://dev.mysql.com/doc/mysql-reslimits-excerpt/8.0/en/)

[MySQL Partitioning](https://dev.mysql.com/doc/mysql-partitioning-excerpt/8.0/en/)

[MySQL Tutorial](https://dev.mysql.com/doc/mysql-tutorial-excerpt/8.0/en/)

[MySQL Performance Schema](https://dev.mysql.com/doc/mysql-perfschema-excerpt/8.0/en/)

[MySQL Replication](https://dev.mysql.com/doc/mysql-replication-excerpt/8.0/en/)

[Using the MySQL Yum Repository](https://dev.mysql.com/doc/mysql-repo-excerpt/8.0/en/)

[MySQL NDB Cluster 8.0](https://dev.mysql.com/doc/mysql-cluster-excerpt/8.0/en/)