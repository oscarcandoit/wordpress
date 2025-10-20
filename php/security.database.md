---
url: https://www.php.net/manual/en/security.database.php
scraped_at: 2025-10-20T02:38:07.445Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# Database Security [¶](https://www.php.net/manual/en/security.database.php\#security.database)

## Table of Contents [¶](https://www.php.net/manual/en/security.database.php\#security.database)

- [Designing Databases](https://www.php.net/manual/en/security.database.design.php)
- [Connecting to Database](https://www.php.net/manual/en/security.database.connection.php)
- [Encrypted Storage Model](https://www.php.net/manual/en/security.database.storage.php)
- [SQL Injection](https://www.php.net/manual/en/security.database.sql-injection.php)

Nowadays, databases are cardinal components of any web based application by
enabling websites to provide varying dynamic content. Since very sensitive
or secret information can be stored in a database, you should strongly
consider protecting your databases.


To retrieve or to store any information you need to connect to the database,
send a legitimate query, fetch the result, and close the connection.
Nowadays, the commonly used query language in this interaction is the
Structured Query Language (SQL). See how an attacker can [tamper with an SQL query](https://www.php.net/manual/en/security.database.sql-injection.php).


As you can surmise, PHP cannot protect your database by itself. The
following sections aim to be an introduction into the very basics of how to
access and manipulate databases within PHP scripts.


Keep in mind this simple rule: defense in depth. The more places you
take action to increase the protection of your database, the less
probability of an attacker succeeding in exposing or abusing any stored
information. Good design of the database schema and the application
deals with your greatest fears.


### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/security/database.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Fsecurity.database%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=security.database&repo=en&redirect=https://www.php.net/manual/en/security.database.php)

### User Contributed Notes 1 note

[up](https://www.php.net/manual/vote-note.php?id=129917&page=security.database&vote=up "Vote up!")

[down](https://www.php.net/manual/vote-note.php?id=129917&page=security.database&vote=down "Vote down!")

1


[**_gabe dot aust at gmail dot com_**](https://www.php.net/manual/en/security.database.php#129917) [¶](https://www.php.net/manual/en/security.database.php#129917)

**10 months ago**

`The most significant way to protect databases is to simply use authentication! There are production systems online with null and default administrator credentials. See the recent  "The Real World" hack...
Rule 1: Simply use authentication instead of not using it... Obviously do not save the credentials in a public-readable file.
Rule 2: Create a subsidiary account with access only to the live schema being used by your PHP app, i.e. never use the global DBMS admin account as a service login.
Rule 3: Block access at the DBMS end to only allow the web server to access the API. Most access is network based so that will involve filtering by IP.
Rule 4: You can obfuscate a bit more by setting a non-standard port but this may require code changes in the API calls you coded.
The above are some simple steps anyone can perform. More serious securing would likely involve setting up SSL connectivity.`

[＋add a note](https://www.php.net/manual/add-note.php?sect=security.database&repo=en&redirect=https://www.php.net/manual/en/security.database.php)

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google