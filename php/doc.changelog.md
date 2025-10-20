---
url: https://www.php.net/manual/en/doc.changelog.php
scraped_at: 2025-10-20T02:31:36.116Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# Changelog [¶](https://www.php.net/manual/en/doc.changelog.php\#doc.changelog)

The following changes have been made to functions of bundled extensions.

| Version | Function | Description |
| --- | --- | --- |
| 8.5.0 | [get\_defined\_functions](https://www.php.net/manual/en/function.get-defined-functions.php) | The exclude\_disabled parameter has been deprecated,<br> as it no longer has any effect. |
|  | [xml\_parser\_free](https://www.php.net/manual/en/function.xml-parser-free.php) | This function has been deprecated. |
| 8.4.0 | [DOMDocument::registerNodeClass](https://www.php.net/manual/en/domdocument.registernodeclass.php) | DOMDocument::registerNodeClass<br> now has a tentative return of true. |
|  | [DOMImplementation::createDocument](https://www.php.net/manual/en/domimplementation.createdocument.php) | The function now has the tentative return type DOMDocument. |
|  | [DOMXPath::registerPhpFunctions](https://www.php.net/manual/en/domxpath.registerphpfunctions.php) | It is now possible to use callables for callbacks<br> when using restrict with array<br> entries. |
|  |  | Invalid callback names now throws a<br> ValueError.<br> Passing a non-callable entry now throws a<br> TypeError. |
|  | [bcpow](https://www.php.net/manual/en/function.bcpow.php) | Negative powers of 0 previously returned 0, but now throw a DivisionByZeroError<br> exception. |
|  | [bind\_textdomain\_codeset](https://www.php.net/manual/en/function.bind-textdomain-codeset.php) | Now throws a ValueError if domain<br> is the empty string. |
|  | [bind\_textdomain\_codeset](https://www.php.net/manual/en/function.bind-textdomain-codeset.php) | codeset is optional now.<br> Previously, the parameter always had to be specified. |
|  | [bindtextdomain](https://www.php.net/manual/en/function.bindtextdomain.php) | directory is optional now.<br> Previously, the parameter always had to be specified. |
|  | [curl\_getinfo](https://www.php.net/manual/en/function.curl-getinfo.php) | Introduced CURLINFO\_POSTTRANSFER\_TIME\_T constant and posttransfer\_time\_us (Curl 8.10.0 or later). |
|  | [curl\_multi\_select](https://www.php.net/manual/en/function.curl-multi-select.php) | Now throws a ValueError if timeout<br> is less than 0 or greater than PHP\_INT\_MAX. |
|  | [curl\_setopt](https://www.php.net/manual/en/function.curl-setopt.php) | CURLOPT\_DNS\_USE\_GLOBAL\_CACHE no longer has any effect,<br> and enabling it on thread-safe PHP builds no longer triggers a warning. |
|  | [curl\_version](https://www.php.net/manual/en/function.curl-version.php) | features\_list added. |
|  | [dba\_close](https://www.php.net/manual/en/function.dba-close.php) | The dba parameter expects a Dba\\Connection<br> instance now; previously, a valid dba resource was expected. |
|  | [dba\_delete](https://www.php.net/manual/en/function.dba-delete.php) | The dba parameter expects a Dba\\Connection<br> instance now; previously, a valid dba resource was expected. |
|  | [dba\_exists](https://www.php.net/manual/en/function.dba-exists.php) | The dba parameter expects a Dba\\Connection<br> instance now; previously, a valid dba resource was expected. |
|  | [dba\_fetch](https://www.php.net/manual/en/function.dba-fetch.php) | The dba parameter expects a Dba\\Connection<br> instance now; previously, a valid dba resource was expected. |
|  | [dba\_firstkey](https://www.php.net/manual/en/function.dba-firstkey.php) | The dba parameter expects a Dba\\Connection<br> instance now; previously, a valid dba resource was expected. |
|  | [dba\_insert](https://www.php.net/manual/en/function.dba-insert.php) | The dba parameter expects a Dba\\Connection<br> instance now; previously, a valid dba resource was expected. |
|  | [dba\_key\_split](https://www.php.net/manual/en/function.dba-key-split.php) | Passing null or false to key<br> is now deprecated. |
|  | [dba\_nextkey](https://www.php.net/manual/en/function.dba-nextkey.php) | The dba parameter expects a Dba\\Connection<br> instance now; previously, a valid dba resource was expected. |
|  | [dba\_open](https://www.php.net/manual/en/function.dba-open.php) | Returns a Dba\\Connection instance now;<br> previously, a resource was returned. |
|  | [dba\_optimize](https://www.php.net/manual/en/function.dba-optimize.php) | The dba parameter expects a Dba\\Connection<br> instance now; previously, a valid dba resource was expected. |
|  | [dba\_popen](https://www.php.net/manual/en/function.dba-popen.php) | Returns a Dba\\Connection instance now;<br> previously, a resource was returned. |
|  | [dba\_replace](https://www.php.net/manual/en/function.dba-replace.php) | The dba parameter expects a Dba\\Connection<br> instance now; previously, a valid dba resource was expected. |
|  | [dba\_sync](https://www.php.net/manual/en/function.dba-sync.php) | The dba parameter expects a Dba\\Connection<br> instance now; previously, a valid dba resource was expected. |
|  | [dgettext](https://www.php.net/manual/en/function.dgettext.php) | Now throws a ValueError if domain<br> is the empty string. |
|  | [dngettext](https://www.php.net/manual/en/function.dngettext.php) | Now throws a ValueError if domain<br> is the empty string. |
|  | [exit](https://www.php.net/manual/en/function.exit.php) | exit is now a proper function,<br> therefore it follows the usual<br> type juggling semantics<br> is affected by the<br> strict\_types<br> declare, can be called with named arguments, and be a<br> variable functions. |
|  | [fgetcsv](https://www.php.net/manual/en/function.fgetcsv.php) | Relying on the default value of escape is now<br> deprecated. |
|  | [flush](https://www.php.net/manual/en/function.flush.php) | Flushing headers without a body will now succeed in FastCGI. |
|  | [fputcsv](https://www.php.net/manual/en/function.fputcsv.php) | Relying on the default value of escape is now<br> deprecated. |
|  | [hash\_init](https://www.php.net/manual/en/function.hash-init.php) | Passing options of a wrong type is now deprecated. |
|  | [hash\_update](https://www.php.net/manual/en/function.hash-update.php) | Now has a return type of true instead of<br> bool. |
|  | [highlight\_string](https://www.php.net/manual/en/function.highlight-string.php) | Return type changed from stringbool to stringtrue. |
|  | [imageavif](https://www.php.net/manual/en/function.imageavif.php) | Now throws a ValueError if quality<br> or speed is invalid. |
|  | [imagefilter](https://www.php.net/manual/en/function.imagefilter.php) | Now throws a ValueError<br> if sub or plus would cause over-/underflow<br> with the IMG\_FILTER\_SCATTER filter. |
|  | [imagejpeg](https://www.php.net/manual/en/function.imagejpeg.php) | Now throws a ValueError if quality is invalid. |
|  | [imagepng](https://www.php.net/manual/en/function.imagepng.php) | Now throws a ValueError if quality is invalid. |
|  | [imagescale](https://www.php.net/manual/en/function.imagescale.php) | Now throws a ValueError if width<br> or height would cause over-/underflow. |
|  | [imagescale](https://www.php.net/manual/en/function.imagescale.php) | Now throws a ValueError if mode is invalid. |
|  | [imagewebp](https://www.php.net/manual/en/function.imagewebp.php) | Now throws a ValueError if quality is invalid. |
|  | [lcg\_value](https://www.php.net/manual/en/function.lcg-value.php) | This function has been deprecated. |
|  | [libxml\_set\_streams\_context](https://www.php.net/manual/en/function.libxml-set-streams-context.php) | libxml\_set\_streams\_context now throws a<br> TypeError when a non-stream resource is passed<br> to context, instead of throwing later when the<br> context is used. |
|  | [long2ip](https://www.php.net/manual/en/function.long2ip.php) | Return type changed from stringfalse to string. |
|  | [mb\_decode\_numericentity](https://www.php.net/manual/en/function.mb-decode-numericentity.php) | mb\_decode\_numericentity now throws a<br> ValueError if map<br> is not a list of ints. |
|  | [mb\_encode\_numericentity](https://www.php.net/manual/en/function.mb-encode-numericentity.php) | mb\_encode\_numericentity now throws a<br> ValueError if map<br> is not a list of ints. |
|  | [mb\_http\_input](https://www.php.net/manual/en/function.mb-http-input.php) | mb\_http\_input now throws a<br> ValueError if type<br> is invalid. |
|  | [mb\_http\_output](https://www.php.net/manual/en/function.mb-http-output.php) | mb\_http\_output now throws a<br> ValueError if encoding<br> contains null bytes. |
|  | [odbc\_autocommit](https://www.php.net/manual/en/function.odbc-autocommit.php) | odbc expects an Odbc\\Connection<br> instance now; previously, a resource was expected. |
|  | [odbc\_binmode](https://www.php.net/manual/en/function.odbc-binmode.php) | statement expects an Odbc\\Result<br> instance now; previously, a resource was expected. |
|  | [odbc\_close](https://www.php.net/manual/en/function.odbc-close.php) | odbc expects an Odbc\\Connection<br> instance now; previously, a resource was expected. |
|  | [odbc\_columnprivileges](https://www.php.net/manual/en/function.odbc-columnprivileges.php) | odbc expects an Odbc\\Connection<br> instance now; previously, a resource was expected. |
|  | [odbc\_columns](https://www.php.net/manual/en/function.odbc-columns.php) | odbc expects an Odbc\\Connection<br> instance now; previously, a resource was expected. |
|  | [odbc\_commit](https://www.php.net/manual/en/function.odbc-commit.php) | odbc expects an Odbc\\Connection<br> instance now; previously, a resource was expected. |
|  | [odbc\_connect](https://www.php.net/manual/en/function.odbc-connect.php) | odbc expects an Odbc\\Connection<br> instance now; previously, a resource was expected. |
|  | [odbc\_connect](https://www.php.net/manual/en/function.odbc-connect.php) | This function returns a Odbc\\Connection instance now;<br> previously, a resource was returned. |
|  | [odbc\_connect](https://www.php.net/manual/en/function.odbc-connect.php) | user and password are now nullable,<br> they are now also optional and default to null. |
|  | [odbc\_connect](https://www.php.net/manual/en/function.odbc-connect.php) | Previously, using an empty string for password would not include<br> pwd in the generated connection string for dsn.<br> It is now generated to include a pwd which has an empty string as its value.<br> To restore the previous behaviour password can now be set to null. |
|  | [odbc\_connect](https://www.php.net/manual/en/function.odbc-connect.php) | Previously, if dsn contained uid or pwd<br> both user and password parameters were ignored.<br> Now user is only ignored if dsn contains<br> uid, and password is only ignored if<br> dsn contains pwd. |
|  | [odbc\_cursor](https://www.php.net/manual/en/function.odbc-cursor.php) | statement expects an Odbc\\Result<br> instance now; previously, a resource was expected. |
|  | [odbc\_data\_source](https://www.php.net/manual/en/function.odbc-data-source.php) | odbc expects an Odbc\\Connection<br> instance now; previously, a resource was expected. |
|  | [odbc\_error](https://www.php.net/manual/en/function.odbc-error.php) | odbc expects an Odbc\\Connection<br> instance now; previously, a resource was expected. |
|  | [odbc\_errormsg](https://www.php.net/manual/en/function.odbc-errormsg.php) | odbc expects an Odbc\\Connection<br> instance now; previously, a resource was expected. |
|  | [odbc\_exec](https://www.php.net/manual/en/function.odbc-exec.php) | odbc expects an Odbc\\Connection<br> instance now; previously, a resource was expected. |
|  | [odbc\_exec](https://www.php.net/manual/en/function.odbc-exec.php) | This function returns an Odbc\\Result<br> instance now; previously, a resource was returned. |
|  | [odbc\_execute](https://www.php.net/manual/en/function.odbc-execute.php) | This function returns an Odbc\\Result<br> instance now; previously, a resource was returned. |
|  | [odbc\_fetch\_array](https://www.php.net/manual/en/function.odbc-fetch-array.php) | statement expects an Odbc\\Result<br> instance now; previously, a resource was expected. |
|  | [odbc\_fetch\_array](https://www.php.net/manual/en/function.odbc-fetch-array.php) | row is now nullable. |
|  | [odbc\_fetch\_into](https://www.php.net/manual/en/function.odbc-fetch-into.php) | statement expects an Odbc\\Result<br> instance now; previously, a resource was expected. |
|  | [odbc\_fetch\_into](https://www.php.net/manual/en/function.odbc-fetch-into.php) | row is now nullable. |
|  | [odbc\_fetch\_object](https://www.php.net/manual/en/function.odbc-fetch-object.php) | statement expects an Odbc\\Result<br> instance now; previously, a resource was expected. |
|  | [odbc\_fetch\_object](https://www.php.net/manual/en/function.odbc-fetch-object.php) | row is now nullable. |
|  | [odbc\_fetch\_row](https://www.php.net/manual/en/function.odbc-fetch-row.php) | statement expects an Odbc\\Result<br> instance now; previously, a resource was expected. |
|  | [odbc\_fetch\_row](https://www.php.net/manual/en/function.odbc-fetch-row.php) | An E\_WARNING is now emitted when row<br> is equal or less than zero. |
|  | [odbc\_field\_len](https://www.php.net/manual/en/function.odbc-field-len.php) | statement expects an Odbc\\Result<br> instance now; previously, a resource was expected. |
|  | [odbc\_field\_name](https://www.php.net/manual/en/function.odbc-field-name.php) | statement expects an Odbc\\Result<br> instance now; previously, a resource was expected. |
|  | [odbc\_field\_num](https://www.php.net/manual/en/function.odbc-field-num.php) | statement expects an Odbc\\Result<br> instance now; previously, a resource was expected. |
|  | [odbc\_field\_scale](https://www.php.net/manual/en/function.odbc-field-scale.php) | statement expects an Odbc\\Result<br> instance now; previously, a resource was expected. |
|  | [odbc\_field\_type](https://www.php.net/manual/en/function.odbc-field-type.php) | statement expects an Odbc\\Result<br> instance now; previously, a resource was expected. |
|  | [odbc\_foreignkeys](https://www.php.net/manual/en/function.odbc-foreignkeys.php) | odbc expects an Odbc\\Connection<br> instance now; previously, a resource was expected. |
|  | [odbc\_foreignkeys](https://www.php.net/manual/en/function.odbc-foreignkeys.php) | This function returns an Odbc\\Result<br> instance now; previously, a resource was returned. |
|  | [odbc\_free\_result](https://www.php.net/manual/en/function.odbc-free-result.php) | statement expects an Odbc\\Result<br> instance now; previously, a resource was expected. |
|  | [odbc\_gettypeinfo](https://www.php.net/manual/en/function.odbc-gettypeinfo.php) | odbc expects an Odbc\\Connection<br> instance now; previously, a resource was expected. |
|  | [odbc\_gettypeinfo](https://www.php.net/manual/en/function.odbc-gettypeinfo.php) | This function returns an Odbc\\Result<br> instance now; previously, a resource was returned. |
|  | [odbc\_longreadlen](https://www.php.net/manual/en/function.odbc-longreadlen.php) | statement expects an Odbc\\Result<br> instance now; previously, a resource was expected. |
|  | [odbc\_next\_result](https://www.php.net/manual/en/function.odbc-next-result.php) | statement expects an Odbc\\Result<br> instance now; previously, a resource was expected. |
|  | [odbc\_num\_fields](https://www.php.net/manual/en/function.odbc-num-fields.php) | statement expects an Odbc\\Result<br> instance now; previously, a resource was expected. |
|  | [odbc\_num\_rows](https://www.php.net/manual/en/function.odbc-num-rows.php) | statement expects an Odbc\\Result<br> instance now; previously, a resource was expected. |
|  | [odbc\_pconnect](https://www.php.net/manual/en/function.odbc-pconnect.php) | odbc expects an Odbc\\Connection<br> instance now; previously, a resource was expected. |
|  | [odbc\_pconnect](https://www.php.net/manual/en/function.odbc-pconnect.php) | This function returns a Odbc\\Connection instance now;<br> previously, a resource was returned. |
|  | [odbc\_pconnect](https://www.php.net/manual/en/function.odbc-pconnect.php) | user and password are now nullable,<br> they are now also optional and default to null. |
|  | [odbc\_pconnect](https://www.php.net/manual/en/function.odbc-pconnect.php) | Previously, using an empty string for password would not include<br> pwd in the generated connection string for dsn.<br> It is now generated to include a pwd which has an empty string as its value.<br> To restore the previous behaviour password can now be set to null. |
|  | [odbc\_pconnect](https://www.php.net/manual/en/function.odbc-pconnect.php) | Previously, if dsn contained uid or pwd<br> both user and password parameters were ignored.<br> Now user is only ignored if dsn contains<br> uid, and password is only ignored if<br> dsn contains pwd. |
|  | [odbc\_prepare](https://www.php.net/manual/en/function.odbc-prepare.php) | odbc expects an Odbc\\Connection<br> instance now; previously, a resource was expected. |
|  | [odbc\_prepare](https://www.php.net/manual/en/function.odbc-prepare.php) | This function returns an Odbc\\Result<br> instance now; previously, a resource was returned. |
|  | [odbc\_primarykeys](https://www.php.net/manual/en/function.odbc-primarykeys.php) | odbc expects an Odbc\\Connection<br> instance now; previously, a resource was expected. |
|  | [odbc\_primarykeys](https://www.php.net/manual/en/function.odbc-primarykeys.php) | This function returns an Odbc\\Result<br> instance now; previously, a resource was returned. |
|  | [odbc\_procedurecolumns](https://www.php.net/manual/en/function.odbc-procedurecolumns.php) | odbc expects an Odbc\\Connection<br> instance now; previously, a resource was expected. |
|  | [odbc\_procedurecolumns](https://www.php.net/manual/en/function.odbc-procedurecolumns.php) | This function returns an Odbc\\Result<br> instance now; previously, a resource was returned. |
|  | [odbc\_procedures](https://www.php.net/manual/en/function.odbc-procedures.php) | odbc expects an Odbc\\Connection<br> instance now; previously, a resource was expected. |
|  | [odbc\_procedures](https://www.php.net/manual/en/function.odbc-procedures.php) | This function returns an Odbc\\Result<br> instance now; previously, a resource was returned. |
|  | [odbc\_result](https://www.php.net/manual/en/function.odbc-result.php) | statement expects an Odbc\\Result<br> instance now; previously, a resource was expected. |
|  | [odbc\_result\_all](https://www.php.net/manual/en/function.odbc-result-all.php) | statement expects an Odbc\\Result<br> instance now; previously, a resource was expected. |
|  | [odbc\_rollback](https://www.php.net/manual/en/function.odbc-rollback.php) | odbc expects an Odbc\\Connection<br> instance now; previously, a resource was expected. |
|  | [odbc\_setoption](https://www.php.net/manual/en/function.odbc-setoption.php) | odbc expects an Odbc\\Connection<br> or an Odbc\\Result instance now; previously, a<br> resource was expected. |
|  | [odbc\_specialcolumns](https://www.php.net/manual/en/function.odbc-specialcolumns.php) | odbc expects an Odbc\\Connection<br> instance now; previously, a resource was expected. |
|  | [odbc\_specialcolumns](https://www.php.net/manual/en/function.odbc-specialcolumns.php) | This function returns an Odbc\\Result<br> instance now; previously, a resource was returned. |
|  | [odbc\_statistics](https://www.php.net/manual/en/function.odbc-statistics.php) | odbc expects an Odbc\\Connection<br> instance now; previously, a resource was expected. |
|  | [odbc\_statistics](https://www.php.net/manual/en/function.odbc-statistics.php) | This function returns an Odbc\\Result<br> instance now; previously, a resource was returned. |
|  | [odbc\_tableprivileges](https://www.php.net/manual/en/function.odbc-tableprivileges.php) | odbc expects an Odbc\\Connection<br> instance now; previously, a resource was expected. |
|  | [odbc\_tableprivileges](https://www.php.net/manual/en/function.odbc-tableprivileges.php) | This function returns an Odbc\\Result<br> instance now; previously, a resource was returned. |
|  | [odbc\_tables](https://www.php.net/manual/en/function.odbc-tables.php) | odbc expects an Odbc\\Connection<br> instance now; previously, a resource was expected. |
|  | [odbc\_tables](https://www.php.net/manual/en/function.odbc-tables.php) | This function returns an Odbc\\Result<br> instance now; previously, a resource was returned. |
|  | [openssl\_csr\_new](https://www.php.net/manual/en/function.openssl-csr-new.php) | The distinguished\_names associative array now supports arrays as values,<br> allowing multiple values to be specified for a single attribute. |
|  | [openssl\_csr\_new](https://www.php.net/manual/en/function.openssl-csr-new.php) | The extra\_attributes parameter now correctly sets the CSR attributes,<br> rather than modifying the subject's Distinguished Name as it previously did incorrectly. |
|  | [openssl\_csr\_sign](https://www.php.net/manual/en/function.openssl-csr-sign.php) | The serial\_hex parameter is added. |
|  | [openssl\_pkey\_get\_details](https://www.php.net/manual/en/function.openssl-pkey-get-details.php) | Added support for Curve25519 and Curve448 based keys.<br> Specifically the x25519, ed25519,<br> x448 and ed448 fields have been introduced. |
|  | [openssl\_pkey\_new](https://www.php.net/manual/en/function.openssl-pkey-new.php) | Added support for Curve25519 and Curve448 based keys with the introduction of the<br> x25519, ed25519, x448,<br> and ed448 fields. |
|  | [openssl\_x509\_parse](https://www.php.net/manual/en/function.openssl-x509-parse.php) | Parsing certificate with no seconds in UTCTime is no longer allowed for any OpenSSL version.<br> It was already disallowed for OpenSSL version 3.3+. |
|  | [password\_hash](https://www.php.net/manual/en/function.password-hash.php) | The default value of the cost option of the<br> PASSWORD\_BCRYPT algorithm was increased from<br> 10 to 12. |
|  | [pcntl\_sigprocmask](https://www.php.net/manual/en/function.pcntl-sigprocmask.php) | A ValueError is thrown if signal<br> is empty. |
|  | [pcntl\_sigprocmask](https://www.php.net/manual/en/function.pcntl-sigprocmask.php) | A TypeError is thrown if signal<br> value is not an int. |
|  | [pcntl\_sigprocmask](https://www.php.net/manual/en/function.pcntl-sigprocmask.php) | A ValueError is thrown if signal<br> value is invalid. |
|  | [pcntl\_sigprocmask](https://www.php.net/manual/en/function.pcntl-sigprocmask.php) | A ValueError is thrown if mode<br> value is not SIG\_BLOCK, SIG\_UNBLOCK or<br> SIG\_SETMASK. |
|  | [pcntl\_sigtimedwait](https://www.php.net/manual/en/function.pcntl-sigtimedwait.php) | A ValueError is thrown if signal<br> is empty. |
|  | [pcntl\_sigtimedwait](https://www.php.net/manual/en/function.pcntl-sigtimedwait.php) | A TypeError is thrown if signal<br> value is not an int. |
|  | [pcntl\_sigtimedwait](https://www.php.net/manual/en/function.pcntl-sigtimedwait.php) | A ValueError is thrown if signal<br> value is invalid. |
|  | [pcntl\_sigtimedwait](https://www.php.net/manual/en/function.pcntl-sigtimedwait.php) | A ValueError is thrown if seconds<br> value is less than 0. |
|  | [pcntl\_sigtimedwait](https://www.php.net/manual/en/function.pcntl-sigtimedwait.php) | A ValueError is thrown if nanoseconds<br> value is less than 0. |
|  | [pcntl\_sigtimedwait](https://www.php.net/manual/en/function.pcntl-sigtimedwait.php) | A ValueError is thrown if both seconds and<br> nanoseconds values are 0. |
|  | [pcntl\_sigwaitinfo](https://www.php.net/manual/en/function.pcntl-sigwaitinfo.php) | A ValueError is thrown if signal<br> is empty. |
|  | [pcntl\_sigwaitinfo](https://www.php.net/manual/en/function.pcntl-sigwaitinfo.php) | A TypeError is thrown if signal<br> value is not an int. |
|  | [pcntl\_sigwaitinfo](https://www.php.net/manual/en/function.pcntl-sigwaitinfo.php) | A ValueError is thrown if signal<br> value is invalid. |
|  | [pg\_select](https://www.php.net/manual/en/function.pg-select.php) | conditions is now optional. |
|  | [php\_uname](https://www.php.net/manual/en/function.php-uname.php) | Throws a ValueError when an invalid<br> mode is specified. |
|  | [posix\_isatty](https://www.php.net/manual/en/function.posix-isatty.php) | Set errno (error number) to EBADF when the<br> file descriptor/stream passed is invalid. |
|  | [pow](https://www.php.net/manual/en/function.pow.php) | Raising 0 to a negative<br> exponent is now deprecated. |
|  | [print\_r](https://www.php.net/manual/en/function.print-r.php) | Return type changed from stringbool to stringtrue. |
|  | [round](https://www.php.net/manual/en/function.round.php) | Four new rounding modes have been added. |
|  | [round](https://www.php.net/manual/en/function.round.php) | Now throws a ValueError if<br> mode is invalid. |
|  | [simplexml\_import\_dom](https://www.php.net/manual/en/function.simplexml-import-dom.php) | Added support for Dom\\Document. |
|  | [simplexml\_import\_dom](https://www.php.net/manual/en/function.simplexml-import-dom.php) | This function now throws a TypeError instead of<br> a ValueError when passed a<br> non-XML or non-HTML node. |
|  | [socket\_create\_listen](https://www.php.net/manual/en/function.socket-create-listen.php) | The default value of is now SOMAXCONN.<br> Previously it was 128. |
|  | [str\_getcsv](https://www.php.net/manual/en/function.str-getcsv.php) | Relying on the default value of escape is now<br> deprecated. |
|  | [str\_getcsv](https://www.php.net/manual/en/function.str-getcsv.php) | Now throws a ValueError if<br> separator, enclosure,<br> or escape is invalid.<br> This mimics the behavior of fgetcsv and<br> fputcsv. |
|  | [strcspn](https://www.php.net/manual/en/function.strcspn.php) | Prior to PHP 8.4.0, when characters was the empty string,<br> the search would incorrectly stop at the first null byte in string. |
|  | [stream\_bucket\_append](https://www.php.net/manual/en/function.stream-bucket-append.php) | bucket expects a StreamBucket instance now; previously, an stdClass was expected. |
|  | [stream\_bucket\_make\_writeable](https://www.php.net/manual/en/function.stream-bucket-make-writeable.php) | This function returns a StreamBucket instance now; previously, an stdClass was returned. |
|  | [stream\_bucket\_new](https://www.php.net/manual/en/function.stream-bucket-new.php) | This function returns a StreamBucket instance now; previously, an stdClass was returned. |
|  | [stream\_bucket\_prepend](https://www.php.net/manual/en/function.stream-bucket-prepend.php) | bucket expects a StreamBucket instance now; previously, an stdClass was expected. |
|  | [stream\_context\_set\_option](https://www.php.net/manual/en/function.stream-context-set-option.php) | The alternative 2-parameter signature is now deprecated.<br> Use stream\_context\_set\_options instead. |
|  | [textdomain](https://www.php.net/manual/en/function.textdomain.php) | Now throws a ValueError if domain<br> is the empty string. |
|  | [textdomain](https://www.php.net/manual/en/function.textdomain.php) | domain is optional now.<br> Previously, the parameter always had to be specified. |
|  | [trigger\_error](https://www.php.net/manual/en/function.trigger-error.php) | Passing E\_USER\_ERROR as the<br> error\_level is now deprecated.<br> Throw an Exception or<br> call exit instead. |
|  | [trigger\_error](https://www.php.net/manual/en/function.trigger-error.php) | The function now has a return type of true<br> instead of bool. |
|  | [unserialize](https://www.php.net/manual/en/function.unserialize.php) | Now throws TypeErrors and<br> ValueErrors if the allowed\_classes<br> element of options is not an array of class names. |
|  | [xml\_parser\_set\_option](https://www.php.net/manual/en/function.xml-parser-set-option.php) | Added the option XML\_OPTION\_PARSE\_HUGE. |
|  | [xml\_set\_character\_data\_handler](https://www.php.net/manual/en/function.xml-set-character-data-handler.php) | Passing a non-callable string to<br> handler is now deprecated,<br> use a proper callable for methods, or null to reset the handler. |
|  | [xml\_set\_character\_data\_handler](https://www.php.net/manual/en/function.xml-set-character-data-handler.php) | The validity of handler as a callable<br> is now checked when setting the handler instead of checking when calling it. |
|  | [xml\_set\_default\_handler](https://www.php.net/manual/en/function.xml-set-default-handler.php) | Passing a non-callable string to<br> handler is now deprecated,<br> use a proper callable for methods, or null to reset the handler. |
|  | [xml\_set\_default\_handler](https://www.php.net/manual/en/function.xml-set-default-handler.php) | The validity of handler as a callable<br> is now checked when setting the handler instead of checking when calling it. |
|  | [xml\_set\_element\_handler](https://www.php.net/manual/en/function.xml-set-element-handler.php) | Passing a non-callable string to<br> handler is now deprecated,<br> use a proper callable for methods, or null to reset the handler. |
|  | [xml\_set\_element\_handler](https://www.php.net/manual/en/function.xml-set-element-handler.php) | The validity of handler as a callable<br> is now checked when setting the handler instead of checking when calling it. |
|  | [xml\_set\_end\_namespace\_decl\_handler](https://www.php.net/manual/en/function.xml-set-end-namespace-decl-handler.php) | Passing a non-callable string to<br> handler is now deprecated,<br> use a proper callable for methods, or null to reset the handler. |
|  | [xml\_set\_end\_namespace\_decl\_handler](https://www.php.net/manual/en/function.xml-set-end-namespace-decl-handler.php) | The validity of handler as a callable<br> is now checked when setting the handler instead of checking when calling it. |
|  | [xml\_set\_external\_entity\_ref\_handler](https://www.php.net/manual/en/function.xml-set-external-entity-ref-handler.php) | Passing a non-callable string to<br> handler is now deprecated,<br> use a proper callable for methods, or null to reset the handler. |
|  | [xml\_set\_external\_entity\_ref\_handler](https://www.php.net/manual/en/function.xml-set-external-entity-ref-handler.php) | The validity of handler as a callable<br> is now checked when setting the handler instead of checking when calling it. |
|  | [xml\_set\_notation\_decl\_handler](https://www.php.net/manual/en/function.xml-set-notation-decl-handler.php) | Passing a non-callable string to<br> handler is now deprecated,<br> use a proper callable for methods, or null to reset the handler. |
|  | [xml\_set\_notation\_decl\_handler](https://www.php.net/manual/en/function.xml-set-notation-decl-handler.php) | The validity of handler as a callable<br> is now checked when setting the handler instead of checking when calling it. |
|  | [xml\_set\_object](https://www.php.net/manual/en/function.xml-set-object.php) | This function is now deprecated,<br> instead pass proper callable values to<br> xml\_set\_ |
|  | [xml\_set\_processing\_instruction\_handler](https://www.php.net/manual/en/function.xml-set-processing-instruction-handler.php) | Passing a non-callable string to<br> handler is now deprecated,<br> use a proper callable for methods, or null to reset the handler. |
|  | [xml\_set\_processing\_instruction\_handler](https://www.php.net/manual/en/function.xml-set-processing-instruction-handler.php) | The validity of handler as a callable<br> is now checked when setting the handler instead of checking when calling it. |
|  | [xml\_set\_start\_namespace\_decl\_handler](https://www.php.net/manual/en/function.xml-set-start-namespace-decl-handler.php) | Passing a non-callable string to<br> handler is now deprecated,<br> use a proper callable for methods, or null to reset the handler. |
|  | [xml\_set\_start\_namespace\_decl\_handler](https://www.php.net/manual/en/function.xml-set-start-namespace-decl-handler.php) | The validity of handler as a callable<br> is now checked when setting the handler instead of checking when calling it. |
|  | [xml\_set\_unparsed\_entity\_decl\_handler](https://www.php.net/manual/en/function.xml-set-unparsed-entity-decl-handler.php) | Passing a non-callable string to<br> handler is now deprecated,<br> use a proper callable for methods, or null to reset the handler. |
|  | [xml\_set\_unparsed\_entity\_decl\_handler](https://www.php.net/manual/en/function.xml-set-unparsed-entity-decl-handler.php) | The validity of handler as a callable<br> is now checked when setting the handler instead of checking when calling it. |
|  | [IntlCalendar::set](https://www.php.net/manual/en/intlcalendar.set.php) | This had been deprecated in favor of the methods<br> IntlCalendar::setDate and<br> IntlCalendar::setDateTime. |
|  | [IntlDateFormatter::create](https://www.php.net/manual/en/intldateformatter.create.php) | A ValueError is thrown if<br> locale is invalid. |
|  | [IntlGregorianCalendar::\_\_construct](https://www.php.net/manual/en/intlgregoriancalendar.construct.php) | This had been deprecated in favor of the methods<br> IntlGregorianCalendar::createFromDate and<br> IntlGregorianCalendar::createFromDateTime. |
|  | [mysqli::kill](https://www.php.net/manual/en/mysqli.kill.php) | Both mysqli::kill and<br> mysqli\_kill are now deprecated. Use the<br> KILL SQL command instead. |
|  | [mysqli::ping](https://www.php.net/manual/en/mysqli.ping.php) | Both mysqli::ping and<br> mysqli\_ping are now deprecated.<br> The reconnect feature has not been available<br> as of PHP 8.2.0, making this function obsolete. |
|  | [mysqli::refresh](https://www.php.net/manual/en/mysqli.refresh.php) | Both mysqli::refresh and<br> mysqli\_refresh are now deprecated.<br> Use FLUSH SQL commands instead. |
|  | [mysqli::store\_result](https://www.php.net/manual/en/mysqli.store-result.php) | Passing the mode parameter is now deprecated.<br> The parameter has had no effect as of PHP 8.1.0. |
|  | [NumberFormatter::create](https://www.php.net/manual/en/numberformatter.create.php) | A ValueError is thrown if<br> locale is invalid. |
|  | [Phar::setAlias](https://www.php.net/manual/en/phar.setalias.php) | Phar::setAlias<br> now has a tentative return of true. |
|  | [Phar::setDefaultStub](https://www.php.net/manual/en/phar.setdefaultstub.php) | Phar::setDefaultStub<br> now has a tentative return of true. |
|  | [PDO\_ODBC DSN](https://www.php.net/manual/en/ref.pdo-odbc.connection.php) | When passing an empty string to the password argument in the PDO constructor, pwd<br> was not included in the connection string created until now, but the behavior has been changed to include<br> it as an empty string. Passing null for the password argument in the PDO constructor results in the same<br> behavior as before. |
|  | [PDO\_ODBC DSN](https://www.php.net/manual/en/ref.pdo-odbc.connection.php) | Changed the behavior to ignore the user name argument and the password argument in the PDO constructor<br> separately when the DSN contains uid or pwd.<br> Previously, if included only either uid or pwd in the DSN,<br> both the user name argument and the password argument in the PDO constructor were ignored. |
|  | [ReflectionClassConstant::\_\_toString](https://www.php.net/manual/en/reflectionclassconstant.tostring.php) | The attached doc comment is now included. |
|  | [ReflectionGenerator::getFunction](https://www.php.net/manual/en/reflectiongenerator.getfunction.php) | ReflectionGenerator::getFunction<br> may now be called after the generator finished executing. |
|  | [ReflectionProperty::\_\_toString](https://www.php.net/manual/en/reflectionproperty.tostring.php) | The attached doc comment is now included. |
|  | [ResourceBundle::get](https://www.php.net/manual/en/resourcebundle.get.php) | A TypeError is thrown if<br> the offset type is invalid.<br> A ValueError is thrown if<br> if index is a string<br> and is empty or is a int and does not<br> fit into a 32 bit integer type. |
|  | [SplFileObject::fgetcsv](https://www.php.net/manual/en/splfileobject.fgetcsv.php) | Relying on the default value of escape is now<br> deprecated. |
|  | [SplFileObject::fputcsv](https://www.php.net/manual/en/splfileobject.fputcsv.php) | Relying on the default value of escape is now<br> deprecated. |
|  | [SplFileObject::setCsvControl](https://www.php.net/manual/en/splfileobject.setcsvcontrol.php) | Relying on the default value of escape is now<br> deprecated. |
|  | [SplFixedArray::setSize](https://www.php.net/manual/en/splfixedarray.setsize.php) | SplFixedArray::setSize<br> now has a tentative return of true. |
|  | [SplFixedArray::\_\_wakeup](https://www.php.net/manual/en/splfixedarray.wakeup.php) | This method is now deprecated, use<br> SplFixedArray::\_\_unserialize<br> instead. |
|  | [SplHeap::insert](https://www.php.net/manual/en/splheap.insert.php) | SplHeap::insert<br> now has a tentative return of true. |
|  | [SplHeap::recoverFromCorruption](https://www.php.net/manual/en/splheap.recoverfromcorruption.php) | SplHeap::recoverFromCorruption<br> now has a tentative return of true. |
|  | [SplPriorityQueue::insert](https://www.php.net/manual/en/splpriorityqueue.insert.php) | SplPriorityQueue::insert<br> now has a tentative return of true. |
|  | [SplPriorityQueue::recoverFromCorruption](https://www.php.net/manual/en/splpriorityqueue.recoverfromcorruption.php) | SplPriorityQueue::recoverFromCorruption<br> now has a tentative return of true. |
|  | [tidy::\_\_construct](https://www.php.net/manual/en/tidy.construct.php) | Failures when executing the constructor now throw instead of silently<br> creating an unusable object. |
|  | [XMLReader::open](https://www.php.net/manual/en/xmlreader.open.php) | Passing an invalid encoding will now throw a<br> ValueError. |
|  | [XMLReader::XML](https://www.php.net/manual/en/xmlreader.xml.php) | Passing an invalid encoding will now throw a<br> ValueError. |
|  | [XMLWriter::startDocument](https://www.php.net/manual/en/xmlwriter.startdocument.php) | Passing an encoding containing null bytes will<br> now throw a ValueError. |
|  | [XSLTProcessor::importStylesheet](https://www.php.net/manual/en/xsltprocessor.importstylesheet.php) | Added support for Dom\\Document. |
|  | [XSLTProcessor::importStylesheet](https://www.php.net/manual/en/xsltprocessor.importstylesheet.php) | Now throws a TypeError instead of a<br> ValueError if<br> stylesheet is not an XML object. |
|  | [XSLTProcessor::registerPHPFunctions](https://www.php.net/manual/en/xsltprocessor.registerphpfunctions.php) | Invalid callback names now throws a<br> ValueError.<br> Passing a non-callable entry now throws a<br> TypeError. |
|  | [XSLTProcessor::registerPHPFunctions](https://www.php.net/manual/en/xsltprocessor.registerphpfunctions.php) | It is now possible to use callables for callbacks<br> when using functions with array<br> entries. |
|  | [XSLTProcessor::setParameter](https://www.php.net/manual/en/xsltprocessor.setparameter.php) | Now throws a ValueError if any of the<br> arguments contain null bytes instead of silently truncating. |
|  | [XSLTProcessor::setParameter](https://www.php.net/manual/en/xsltprocessor.setparameter.php) | It is now possible to set a parameter value containing both single and<br> double quotes. Prior to PHP 8.4.0, this resulted in a warning. |
|  | [XSLTProcessor::transformToDoc](https://www.php.net/manual/en/xsltprocessor.transformtodoc.php) | Now throws an Error if the callback<br> cannot be invoked, instead of emitting a warning. |
|  | [XSLTProcessor::transformToDoc](https://www.php.net/manual/en/xsltprocessor.transformtodoc.php) | Added support for Dom\\Document. |
|  | [XSLTProcessor::transformToUri](https://www.php.net/manual/en/xsltprocessor.transformtouri.php) | Now throws an Error if the callback<br> cannot be invoked, instead of emitting a warning. |
|  | [XSLTProcessor::transformToUri](https://www.php.net/manual/en/xsltprocessor.transformtouri.php) | Added support for Dom\\Document. |
|  | [XSLTProcessor::transformToXml](https://www.php.net/manual/en/xsltprocessor.transformtoxml.php) | Now throws an Error if the callback<br> cannot be invoked, instead of emitting a warning. |
|  | [XSLTProcessor::transformToXml](https://www.php.net/manual/en/xsltprocessor.transformtoxml.php) | Added support for Dom\\Document. |
| 8.3.0 | [DateInterval::\_\_construct](https://www.php.net/manual/en/dateinterval.construct.php) | Now throws<br> DateMalformedIntervalStringException<br> instead of Exception. |
|  | [DateInterval::createFromDateString](https://www.php.net/manual/en/dateinterval.createfromdatestring.php) | DateInterval::createFromDateString now throws<br> DateMalformedStringException if an<br> invalid string is passed. Previously, it returned false,<br> and a warning was emitted.<br> date\_interval\_create\_from\_date\_string has not been<br> changed. |
|  | [DatePeriod::\_\_construct](https://www.php.net/manual/en/dateperiod.construct.php) | Now throws<br> DateMalformedPeriodStringException<br> instead of Exception. |
|  | [DateTime::\_\_construct](https://www.php.net/manual/en/datetime.construct.php) | Now throws<br> DateMalformedStringException if an<br> invalid string is passed, instead of<br> Exception. |
|  | [DateTimeInterface::getTimestamp](https://www.php.net/manual/en/datetime.gettimestamp.php) | The out-of-range exception is now<br> DateRangeError. |
|  | [DateTime::modify](https://www.php.net/manual/en/datetime.modify.php) | DateTime::modify now throws<br> DateMalformedStringException if an<br> invalid string is passed. Previously, it returned false,<br> and a warning was emitted.<br> date\_modify has not been changed. |
|  | [DateTime::sub](https://www.php.net/manual/en/datetime.sub.php) | Now throws a<br> DateInvalidOperationException with<br> DateTime::sub, instead of<br> a warning when an unsupported operation is attempted.<br> date\_sub has not been changed. |
|  | [DateTimeImmutable::\_\_construct](https://www.php.net/manual/en/datetimeimmutable.construct.php) | Now throws<br> DateMalformedStringException if an<br> invalid string is passed, instead of<br> Exception. |
|  | [DateTimeImmutable::modify](https://www.php.net/manual/en/datetimeimmutable.modify.php) | DateTimeImmutable::modify now throws<br> DateMalformedStringException if an<br> invalid string is passed. Previously, it returned false,<br> and a warning was emitted. |
|  | [DateTimeImmutable::sub](https://www.php.net/manual/en/datetimeimmutable.sub.php) | Now throws a<br> DateInvalidOperationException instead of<br> a warning when an unsupported operation is attempted. |
|  | [DateTimeZone::\_\_construct](https://www.php.net/manual/en/datetimezone.construct.php) | Invalid values now return a<br> DateInvalidTimeZoneException instead of<br> a generic Exception. |
|  | [DOMCharacterData::after](https://www.php.net/manual/en/domcharacterdata.after.php) | Calling this method on a node without a parent is now a no-op to align the behaviour with the DOM specification.<br> Previously this threw a<br> DOMException with code<br> DOM\_HIERARCHY\_REQUEST\_ERR. |
|  | [DOMCharacterData::after](https://www.php.net/manual/en/domcharacterdata.after.php) | Calling this method on a node without an owner document now works.<br> Previously this threw a<br> DOMException with code<br> DOM\_HIERARCHY\_REQUEST\_ERR. |
|  | [DOMCharacterData::appendData](https://www.php.net/manual/en/domcharacterdata.appenddata.php) | This function now has a tentative true return type. |
|  | [DOMCharacterData::before](https://www.php.net/manual/en/domcharacterdata.before.php) | Calling this method on a node without a parent is now a no-op to align the behaviour with the DOM specification.<br> Previously this threw a<br> DOMException with code<br> DOM\_HIERARCHY\_REQUEST\_ERR. |
|  | [DOMCharacterData::replaceWith](https://www.php.net/manual/en/domcharacterdata.replacewith.php) | Calling this method on a node without a parent is now a no-op to align the behaviour with the DOM specification.<br> Previously this threw a<br> DOMException with code<br> DOM\_HIERARCHY\_REQUEST\_ERR. |
|  | [DOMChildNode::after](https://www.php.net/manual/en/domchildnode.after.php) | Calling this method on a node without a parent is now a no-op to align the behaviour with the DOM specification.<br> Previously this threw a<br> DOMException with code<br> DOM\_HIERARCHY\_REQUEST\_ERR. |
|  | [DOMChildNode::after](https://www.php.net/manual/en/domchildnode.after.php) | Calling this method on a node without an owner document now works.<br> Previously this threw a<br> DOMException with code<br> DOM\_HIERARCHY\_REQUEST\_ERR. |
|  | [DOMChildNode::before](https://www.php.net/manual/en/domchildnode.before.php) | Calling this method on a node without a parent is now a no-op to align the behaviour with the DOM specification.<br> Previously this threw a<br> DOMException with code<br> DOM\_HIERARCHY\_REQUEST\_ERR. |
|  | [DOMChildNode::replaceWith](https://www.php.net/manual/en/domchildnode.replacewith.php) | Calling this method on a node without a parent is now a no-op to align the behaviour with the DOM specification.<br> Previously this threw a<br> DOMException with code<br> DOM\_HIERARCHY\_REQUEST\_ERR. |
|  | [DOMDocument::append](https://www.php.net/manual/en/domdocument.append.php) | Calling this method on a node without an owner document now works.<br> Previously this threw a<br> DOMException with code<br> DOM\_HIERARCHY\_REQUEST\_ERR. |
|  | [DOMDocument::createAttributeNS](https://www.php.net/manual/en/domdocument.createattributens.php) | Calling this method without specifying a prefix will now choose a prefix instead of assuming the default namespace.<br> Previously this would create an attribute without a prefix and incorrectly apply the namespace<br> to the owner element because default namespaces don't apply on attributes. |
|  | [DOMDocument::createAttributeNS](https://www.php.net/manual/en/domdocument.createattributens.php) | Calling this method using a prefix that was already declared on the owner element with a different namespace URI<br> will now change the new prefix to avoid creating namespace conflicts. This aligns the behaviour with the DOM specification.<br> Previously this threw a DOMException with code DOM\_NAMESPACE\_ERR. |
|  | [DOMDocument::load](https://www.php.net/manual/en/domdocument.load.php) | This function now has a tentative bool return type. |
|  | [DOMDocument::loadHTML](https://www.php.net/manual/en/domdocument.loadhtml.php) | This function now has a tentative bool return type. |
|  | [DOMDocument::loadHTMLFile](https://www.php.net/manual/en/domdocument.loadhtmlfile.php) | This function now has a tentative bool return type. |
|  | [DOMDocument::loadXML](https://www.php.net/manual/en/domdocument.loadxml.php) | This function now has a tentative bool return type. |
|  | [DOMDocument::prepend](https://www.php.net/manual/en/domdocument.prepend.php) | Calling this method on a node without an owner document now works.<br> Previously this threw a<br> DOMException with code<br> DOM\_HIERARCHY\_REQUEST\_ERR. |
|  | [DOMDocument::replaceChildren](https://www.php.net/manual/en/domdocument.replacechildren.php) | Calling this method on a node without an owner document now works.<br> Previously this threw a<br> DOMException with code<br> DOM\_HIERARCHY\_REQUEST\_ERR. |
|  | [DOMDocument::saveXML](https://www.php.net/manual/en/domdocument.savexml.php) | LIBXML\_NOXMLDECL is now supported. |
|  | [DOMDocumentFragment::append](https://www.php.net/manual/en/domdocumentfragment.append.php) | Calling this method on a node without an owner document now works.<br> Previously this threw a<br> DOMException with code<br> DOM\_HIERARCHY\_REQUEST\_ERR. |
|  | [DOMDocumentFragment::prepend](https://www.php.net/manual/en/domdocumentfragment.prepend.php) | Calling this method on a node without an owner document now works.<br> Previously this threw a<br> DOMException with code<br> DOM\_HIERARCHY\_REQUEST\_ERR. |
|  | [DOMDocumentFragment::replaceChildren](https://www.php.net/manual/en/domdocumentfragment.replacechildren.php) | Calling this method on a node without an owner document now works.<br> Previously this threw a<br> DOMException with code<br> DOM\_HIERARCHY\_REQUEST\_ERR. |
|  | [DOMElement::after](https://www.php.net/manual/en/domelement.after.php) | Calling this method on a node without a parent is now a no-op to align the behaviour with the DOM specification.<br> Previously this threw a<br> DOMException with code<br> DOM\_HIERARCHY\_REQUEST\_ERR. |
|  | [DOMElement::after](https://www.php.net/manual/en/domelement.after.php) | Calling this method on a node without an owner document now works.<br> Previously this threw a<br> DOMException with code<br> DOM\_HIERARCHY\_REQUEST\_ERR. |
|  | [DOMElement::append](https://www.php.net/manual/en/domelement.append.php) | Calling this method on a node without an owner document now works.<br> Previously this threw a<br> DOMException with code<br> DOM\_HIERARCHY\_REQUEST\_ERR. |
|  | [DOMElement::before](https://www.php.net/manual/en/domelement.before.php) | Calling this method on a node without a parent is now a no-op to align the behaviour with the DOM specification.<br> Previously this threw a<br> DOMException with code<br> DOM\_HIERARCHY\_REQUEST\_ERR. |
|  | [DOMElement::prepend](https://www.php.net/manual/en/domelement.prepend.php) | Calling this method on a node without an owner document now works.<br> Previously this threw a<br> DOMException with code<br> DOM\_HIERARCHY\_REQUEST\_ERR. |
|  | [DOMElement::replaceChildren](https://www.php.net/manual/en/domelement.replacechildren.php) | Calling this method on a node without an owner document now works.<br> Previously this threw a<br> DOMException with code<br> DOM\_HIERARCHY\_REQUEST\_ERR. |
|  | [DOMElement::replaceWith](https://www.php.net/manual/en/domelement.replacewith.php) | Calling this method on a node without a parent is now a no-op to align the behaviour with the DOM specification.<br> Previously this threw a<br> DOMException with code<br> DOM\_HIERARCHY\_REQUEST\_ERR. |
|  | [DOMParentNode::append](https://www.php.net/manual/en/domparentnode.append.php) | Calling this method on a node without an owner document now works.<br> Previously this threw a<br> DOMException with code<br> DOM\_HIERARCHY\_REQUEST\_ERR. |
|  | [DOMParentNode::prepend](https://www.php.net/manual/en/domparentnode.prepend.php) | Calling this method on a node without an owner document now works.<br> Previously this threw a<br> DOMException with code<br> DOM\_HIERARCHY\_REQUEST\_ERR. |
|  | [DOMParentNode::replaceChildren](https://www.php.net/manual/en/domparentnode.replacechildren.php) | Calling this method on a node without an owner document now works.<br> Previously this threw a<br> DOMException with code<br> DOM\_HIERARCHY\_REQUEST\_ERR. |
|  | [FFI::cast](https://www.php.net/manual/en/ffi.cast.php) | Calling FFI::cast statically is now deprecated. |
|  | [FFI::cdef](https://www.php.net/manual/en/ffi.cdef.php) | C functions returning void return a PHP null<br> instead of FFI\\CType::TYPE\_VOID. |
|  | [FFI::load](https://www.php.net/manual/en/ffi.load.php) | FFI::load is now allowed in<br> preload scripts when the<br> current system user is the same as the one defined in the<br> opcache.preload\_user configuration directive. |
|  | [FFI::new](https://www.php.net/manual/en/ffi.new.php) | Calling FFI::new statically is now deprecated. |
|  | [FFI::type](https://www.php.net/manual/en/ffi.type.php) | Calling FFI::type statically is now deprecated. |
|  | [array\_pad](https://www.php.net/manual/en/function.array-pad.php) | Prior to 8.3, only 1048576 elements could be added at once.<br> Now it is limited only by the maximum size of an array instead. |
|  | [array\_product](https://www.php.net/manual/en/function.array-product.php) | Now emits E\_WARNING when array values<br> cannot be converted to int or float.<br> Previously arrays and objects where ignored whilst every other value was cast to int.<br> Moreover, objects that define a numeric cast (e.g. GMP) are now cast instead of ignored. |
|  | [array\_sum](https://www.php.net/manual/en/function.array-sum.php) | Now emits E\_WARNING when array values<br> cannot be converted to int or float.<br> Previously arrays and objects where ignored whilst every other value was cast to int.<br> Moreover, objects that define a numeric cast (e.g. GMP) are now cast instead of ignored. |
|  | [assert](https://www.php.net/manual/en/function.assert.php) | All assert. INI settings have been deprecated. |
|  | [assert\_options](https://www.php.net/manual/en/function.assert-options.php) | assert\_option is now deprecated. |
|  | [class\_alias](https://www.php.net/manual/en/function.class-alias.php) | class\_alias now supports creating an alias of an internal class. |
|  | [curl\_getinfo](https://www.php.net/manual/en/function.curl-getinfo.php) | Introduced CURLINFO\_CAINFO<br> and CURLINFO\_CAPATH. |
|  | [dba\_fetch](https://www.php.net/manual/en/function.dba-fetch.php) | Calling dba\_fetch with dba as<br> the 3rd argument is now deprecated. |
|  | [easter\_date](https://www.php.net/manual/en/function.easter-date.php) | On 64-bit systems, the year parameter now accepts values within the range of 1970 to 2,000,000,000. |
|  | [fgetcsv](https://www.php.net/manual/en/function.fgetcsv.php) | An empty string is returned instead of a string with a single<br> null byte for the last field if it contains only an unterminated<br> enclosure. |
|  | [file](https://www.php.net/manual/en/function.file.php) | ValueError is thrown for any<br> invalid values of flags. |
|  | [gc\_status](https://www.php.net/manual/en/function.gc-status.php) | gc\_status now returns the following additional fields:<br> "running", "protected",<br> "full", "buffer\_size",<br> "application\_time", "collector\_time",<br> "destructor\_time", and "free\_time". |
|  | [get\_class](https://www.php.net/manual/en/function.get-class.php) | Calling get\_class without an argument now emits an<br> E\_DEPRECATED warning;<br> previously, calling this function inside a class returned the name of that class. |
|  | [get\_parent\_class](https://www.php.net/manual/en/function.get-parent-class.php) | Calling get\_parent\_class without an argument now emits an<br> E\_DEPRECATED warning;<br> previously, calling this function inside a class returned the name of that class. |
|  | [highlight\_file](https://www.php.net/manual/en/function.highlight-file.php) | The resulting HTML has changed. |
|  | [highlight\_string](https://www.php.net/manual/en/function.highlight-string.php) | The resulting HTML has changed. |
|  | [imagerotate](https://www.php.net/manual/en/function.imagerotate.php) | The unused ignore\_transparent has been completely removed. |
|  | [ldap\_connect](https://www.php.net/manual/en/function.ldap-connect.php) | Calling ldap\_connect with separate<br> hostname and port<br> is now deprecated. |
|  | [mb\_convert\_case](https://www.php.net/manual/en/function.mb-convert-case.php) | Implemented conditional casing rules for the Greek letter sigma<br> which only apply to MB\_CASE\_LOWER<br> and MB\_CASE\_TITLE modes, not<br> to MB\_CASE\_LOWER\_SIMPLE and<br> MB\_CASE\_TITLE\_SIMPLE. |
|  | [mb\_decode\_mimeheader](https://www.php.net/manual/en/function.mb-decode-mimeheader.php) | Underscores are converted to spaces as specified by<br> RFC 2047. |
|  | [mb\_encode\_mimeheader](https://www.php.net/manual/en/function.mb-encode-mimeheader.php) | NUL (0) bytes are no longer dropped when encoded<br> using Quoted-Printable encoding, but encoded as =00. |
|  | [mb\_strimwidth](https://www.php.net/manual/en/function.mb-strimwidth.php) | Passing a negative width to<br> mb\_strimwidth is now deprecated. |
|  | [mb\_strtolower](https://www.php.net/manual/en/function.mb-strtolower.php) | Implemented conditional casing rules for the Greek letter sigma. |
|  | [mt\_srand](https://www.php.net/manual/en/function.mt-srand.php) | seed is now nullable. |
|  | [number\_format](https://www.php.net/manual/en/function.number-format.php) | Added handling of negative values for decimals. |
|  | [odbc\_autocommit](https://www.php.net/manual/en/function.odbc-autocommit.php) | enable is now nullable. |
|  | [openssl\_pkey\_new](https://www.php.net/manual/en/function.openssl-pkey-new.php) | Added support for generation EC keys with custom EC parameters.<br> Specifically with the introduction of the EC options:<br> p, a, b, seed,<br> generator, g\_x, g\_y,<br> cofactor, and order. |
|  | [password\_hash](https://www.php.net/manual/en/function.password-hash.php) | password\_hash now sets the underlying<br> Random\\RandomException as the<br> Exception::$previous exception when a<br> ValueError is thrown due to a failure<br> in the salt generation. |
|  | [pg\_convert](https://www.php.net/manual/en/function.pg-convert.php) | Now throws a ValueError or TypeError error<br> when the value or type of field does not match properly with a PostgreSQL's type;<br> previously an E\_WARNING was emitted. |
|  | [pg\_fetch\_object](https://www.php.net/manual/en/function.pg-fetch-object.php) | Now throws a ValueError exception when<br> the constructor\_args is non-empty with the class not having constructor;<br> previously an Exception was thrown. |
|  | [pg\_fetch\_result](https://www.php.net/manual/en/function.pg-fetch-result.php) | row is now nullable. |
|  | [pg\_field\_is\_null](https://www.php.net/manual/en/function.pg-field-is-null.php) | row is now nullable. |
|  | [pg\_field\_prtlen](https://www.php.net/manual/en/function.pg-field-prtlen.php) | row is now nullable. |
|  | [pg\_insert](https://www.php.net/manual/en/function.pg-insert.php) | Now throws a ValueError error when the specified table is invalid;<br> previously an E\_WARNING was emitted. |
|  | [pg\_insert](https://www.php.net/manual/en/function.pg-insert.php) | Now throws a ValueError or TypeError error<br> when the value or type of field does not match properly with a PostgreSQL's type;<br> previously an E\_WARNING was emitted. |
|  | [pg\_trace](https://www.php.net/manual/en/function.pg-trace.php) | trace\_mode has been added. |
|  | [posix\_eaccess](https://www.php.net/manual/en/function.posix-eaccess.php) | Checks the effective user/group for a file, differing<br> from posix\_access which checks<br> from the real user/group. |
|  | [posix\_getrlimit](https://www.php.net/manual/en/function.posix-getrlimit.php) | The optional resource parameter has been added. |
|  | [posix\_isatty](https://www.php.net/manual/en/function.posix-isatty.php) | Type error E\_WARNINGs are now raised for integer<br> coercions following the usual PHP type coercion semantics. |
|  | [posix\_ttyname](https://www.php.net/manual/en/function.posix-ttyname.php) | Type error E\_WARNINGs are now raised for integer<br> coercions following the usual PHP type coercion semantics. |
|  | [posix\_ttyname](https://www.php.net/manual/en/function.posix-ttyname.php) | On invalid file\_descriptor integer values<br> an E\_WARNING is now raised. |
|  | [proc\_get\_status](https://www.php.net/manual/en/function.proc-get-status.php) | The "cached" entry has been added to the returned<br> array. Prior to PHP 8.3.0, only the first call returned the real exit<br> code. The "cached" entry indicates that the exit code<br> was cached. |
|  | [proc\_open](https://www.php.net/manual/en/function.proc-open.php) | A ValueError will be thrown if<br> command is an array without at least one<br> non-empty element. |
|  | [range](https://www.php.net/manual/en/function.range.php) | If both start and end<br> are strings then range will now always produce<br> an array of bytes.<br> Previously if one of the boundary values was a numeric string,<br> then the other boundary value was implicitly cast to int. |
|  | [range](https://www.php.net/manual/en/function.range.php) | An E\_WARNING is now emitted if<br> start or end<br> is a string that is implicitly cast to int<br> because the other boundary value is a number. |
|  | [range](https://www.php.net/manual/en/function.range.php) | An E\_WARNING is now emitted if<br> start or end<br> is a non-numeric string with more than one byte. |
|  | [range](https://www.php.net/manual/en/function.range.php) | An E\_WARNING is now emitted if<br> start or end<br> is the empty string. |
|  | [range](https://www.php.net/manual/en/function.range.php) | If step is a float with no<br> fractional part, it will be interpreted as an int. |
|  | [range](https://www.php.net/manual/en/function.range.php) | A ValueError is now thrown if<br> step is negative when producing an increasing<br> range. |
|  | [range](https://www.php.net/manual/en/function.range.php) | A ValueError is now thrown if<br> step is not finite. |
|  | [range](https://www.php.net/manual/en/function.range.php) | A TypeError is now thrown if<br> start or end<br> is an array, object, or resource.<br> Previously they were implicitly cast to int. |
|  | [srand](https://www.php.net/manual/en/function.srand.php) | seed is now nullable. |
|  | [str\_getcsv](https://www.php.net/manual/en/function.str-getcsv.php) | An empty string is returned instead of a string with a single<br> null byte for the last field if it contains only an unterminated<br> enclosure. |
|  | [stream\_notification\_callback](https://www.php.net/manual/en/function.stream-notification-callback.php) | Support for STREAM\_NOTIFY\_COMPLETED implemented,<br> earlier PHP versions would never trigger this notification. |
|  | [strrchr](https://www.php.net/manual/en/function.strrchr.php) | The before\_needle parameter was added. |
|  | [strtok](https://www.php.net/manual/en/function.strtok.php) | Now emits E\_WARNING when token is not provided. |
|  | [unserialize](https://www.php.net/manual/en/function.unserialize.php) | Now emits E\_WARNING when the input string has unconsumed data. |
|  | [unserialize](https://www.php.net/manual/en/function.unserialize.php) | Now emits E\_WARNING when the passed string is not unserializeable;<br> previously E\_NOTICE was emitted. |
|  | [xml\_parser\_get\_option](https://www.php.net/manual/en/function.xml-parser-get-option.php) | The function now returns a boolean for boolean options. |
|  | [xml\_parser\_set\_option](https://www.php.net/manual/en/function.xml-parser-set-option.php) | The value parameter now also accepts booleans.<br> The options XML\_OPTION\_CASE\_FOLDING and XML\_OPTION\_SKIP\_WHITE<br> are now boolean options. |
|  | [IntlBreakIterator::setText](https://www.php.net/manual/en/intlbreakiterator.settext.php) | This method now returns false on failure; previously it returns null. |
|  | [IntlChar::enumCharNames](https://www.php.net/manual/en/intlchar.enumcharnames.php) | This method now returns false on failure; previously it returns null. |
|  | [IntlDateFormatter::setTimeZone](https://www.php.net/manual/en/intldateformatter.settimezone.php) | This function now returns true on success; previously it returns null. |
|  | [mysqli\_result::fetch\_object](https://www.php.net/manual/en/mysqli-result.fetch-object.php) | Now throws a ValueError exception when<br> the constructor\_args is non-empty with the class not having constructor;<br> previously an Exception was thrown. |
|  | [mysqli::poll](https://www.php.net/manual/en/mysqli.poll.php) | Now throws a ValueError exception when neither<br> the read nor error arguments are passed. |
|  | [Phar::setStub](https://www.php.net/manual/en/phar.setstub.php) | Calling Phar::setStub with a<br> resource and a length<br> is now deprecated. Such calls should be replaced by:<br> $phar->setStub(stream\_get\_contents($resource)); |
|  | [ReflectionClass::getStaticProperties](https://www.php.net/manual/en/reflectionclass.getstaticproperties.php) | The return type of ReflectionClass::getStaticProperties<br> has been changed to array from ?array. |
|  | [ReflectionProperty::setValue](https://www.php.net/manual/en/reflectionproperty.setvalue.php) | Calling this method with a single argument is deprecated,<br> instead use ReflectionProperty::setValue(null, $value)<br> for static properties. |
|  | [SQLite3::enableExceptions](https://www.php.net/manual/en/sqlite3.enableexceptions.php) | Calling SQLite3::enableExceptions with enable<br> as false will trigger a E\_DEPRECATED warning. |
|  | [ZipArchive::addFile](https://www.php.net/manual/en/ziparchive.addfile.php) | ZipArchive::FL\_OPEN\_FILE\_NOW was added. |
|  | [ZipArchive::addFile](https://www.php.net/manual/en/ziparchive.addfile.php) | ZipArchive::LENGTH\_TO\_END and ZipArchive::LENGTH\_UNCHECKED were added. |
|  | [ZipArchive::addGlob](https://www.php.net/manual/en/ziparchive.addglob.php) | ZipArchive::FL\_OPEN\_FILE\_NOW was added. |
|  | [ZipArchive::replaceFile](https://www.php.net/manual/en/ziparchive.replacefile.php) | ZipArchive::FL\_OPEN\_FILE\_NOW was added. |
|  | [ZipArchive::replaceFile](https://www.php.net/manual/en/ziparchive.replacefile.php) | ZipArchive::LENGTH\_TO\_END and ZipArchive::LENGTH\_UNCHECKED were added. |
| 8.2.9 | [DateTimeImmutable::createFromFormat](https://www.php.net/manual/en/datetimeimmutable.createfromformat.php) | The (space) specifier now also supports NBSP<br> (U+A0) and NNBSP (U+202F) characters. |
| 8.2.1 | [SplFileObject::\_\_toString](https://www.php.net/manual/en/splfileobject.tostring.php) | Changed from an alias of SplFileObject::fgets<br> to an implementation of SplFileObject::current<br> which returns a CSV string when the<br> SplFileObject::READ\_CSV flag is set. |
| 8.2.0 | [ArrayIterator::asort](https://www.php.net/manual/en/arrayiterator.asort.php) | The return type is true now; previously, it was bool. |
|  | [ArrayIterator::ksort](https://www.php.net/manual/en/arrayiterator.ksort.php) | The return type is true now; previously, it was bool. |
|  | [ArrayIterator::natcasesort](https://www.php.net/manual/en/arrayiterator.natcasesort.php) | The return type is true now; previously, it was bool. |
|  | [ArrayIterator::natsort](https://www.php.net/manual/en/arrayiterator.natsort.php) | The return type is true now; previously, it was bool. |
|  | [ArrayIterator::uasort](https://www.php.net/manual/en/arrayiterator.uasort.php) | The return type is true now; previously, it was bool. |
|  | [ArrayIterator::uksort](https://www.php.net/manual/en/arrayiterator.uksort.php) | The return type is true now; previously, it was bool. |
|  | [ArrayObject::asort](https://www.php.net/manual/en/arrayobject.asort.php) | The return type is true now; previously, it was bool. |
|  | [ArrayObject::ksort](https://www.php.net/manual/en/arrayobject.ksort.php) | The return type is true now; previously, it was bool. |
|  | [ArrayObject::natcasesort](https://www.php.net/manual/en/arrayobject.natcasesort.php) | The return type is true now; previously, it was bool. |
|  | [ArrayObject::natsort](https://www.php.net/manual/en/arrayobject.natsort.php) | The return type is true now; previously, it was bool. |
|  | [ArrayObject::uasort](https://www.php.net/manual/en/arrayobject.uasort.php) | The return type is true now; previously, it was bool. |
|  | [ArrayObject::uksort](https://www.php.net/manual/en/arrayobject.uksort.php) | The return type is true now; previously, it was bool. |
|  | [DateInterval::\_\_construct](https://www.php.net/manual/en/dateinterval.construct.php) | Only the y to f,<br> invert, and days will be visible,<br> including a new from\_string boolean property. |
|  | [DateInterval::createFromDateString](https://www.php.net/manual/en/dateinterval.createfromdatestring.php) | Only the from\_string and<br> date\_string properties will be visible when a<br> DateInterval is created with this method. |
|  | [DatePeriod::\_\_construct](https://www.php.net/manual/en/dateperiod.construct.php) | The DatePeriod::INCLUDE\_END\_DATE constant has been added. |
|  | [DateTime::createFromFormat](https://www.php.net/manual/en/datetime.createfromformat.php) | Now throws ValueError when NULL-bytes<br> are passed into datetime, which previously was silently<br> ignored. |
|  | [DateTimeInterface::format](https://www.php.net/manual/en/datetime.format.php) | The format characters X and x<br> have been added. |
|  | [DateTimeImmutable::createFromFormat](https://www.php.net/manual/en/datetimeimmutable.createfromformat.php) | The X and x<br> format specifiers have been added. |
|  | [DateTimeImmutable::createFromFormat](https://www.php.net/manual/en/datetimeimmutable.createfromformat.php) | Now throws ValueError when NULL-bytes<br> are passed into datetime, which previously was silently<br> ignored. |
|  | [DateTimeImmutable::getLastErrors](https://www.php.net/manual/en/datetimeimmutable.getlasterrors.php) | Before PHP 8.2.0, this function did not return false<br> when there were no warnings or errors. Instead, it would always<br> return the documented array structure. |
|  | [FilesystemIterator::\_\_construct](https://www.php.net/manual/en/filesystemiterator.construct.php) | Prior to PHP 8.2.0, FilesystemIterator::SKIP\_DOTS was<br> always set and could not be removed. |
|  | [array\_walk](https://www.php.net/manual/en/function.array-walk.php) | The return type is true now; previously, it was bool. |
|  | [array\_walk\_recursive](https://www.php.net/manual/en/function.array-walk-recursive.php) | The return type is true now; previously, it was bool. |
|  | [arsort](https://www.php.net/manual/en/function.arsort.php) | The return type is true now; previously, it was bool. |
|  | [asort](https://www.php.net/manual/en/function.asort.php) | The return type is true now; previously, it was bool. |
|  | [curl\_getinfo](https://www.php.net/manual/en/function.curl-getinfo.php) | Introduced CURLINFO\_PROXY\_ERROR,<br> CURLINFO\_REFERER,<br> CURLINFO\_RETRY\_AFTER. |
|  | [curl\_multi\_setopt](https://www.php.net/manual/en/function.curl-multi-setopt.php) | Introduced CURLMOPT\_MAX\_CONCURRENT\_STREAMS. |
|  | [date\_parse\_from\_format](https://www.php.net/manual/en/function.date-parse-from-format.php) | Now throws ValueError when NULL-bytes<br> are passed into datetime, which previously was silently<br> ignored. |
|  | [dba\_fetch](https://www.php.net/manual/en/function.dba-fetch.php) | dba\_fetch's optional skip argument is now at the end<br> in line with PHP userland semantics. The previously overloaded signature<br> is still accepted but discouraged. |
|  | [dba\_open](https://www.php.net/manual/en/function.dba-open.php) | flags is added. |
|  | [dba\_open](https://www.php.net/manual/en/function.dba-open.php) | handler is now nullable. |
|  | [dba\_popen](https://www.php.net/manual/en/function.dba-popen.php) | flags is added. |
|  | [getimagesize](https://www.php.net/manual/en/function.getimagesize.php) | Now returns the actual image dimensions, bits and channels of AVIF images;<br> previously, the dimensions were reported as 0x0,<br> and bits and channels were not reported at all. |
|  | [idate](https://www.php.net/manual/en/function.idate.php) | Adds the N (ISO-8601 day of the week) and<br> o (ISO-8601 year) format characters. |
|  | [iterator\_count](https://www.php.net/manual/en/function.iterator-count.php) | The type of iterator has been widened from<br> Traversable to<br> Traversablearray. |
|  | [iterator\_to\_array](https://www.php.net/manual/en/function.iterator-to-array.php) | The type of iterator has been widened from<br> Traversable to<br> Traversablearray. |
|  | [krsort](https://www.php.net/manual/en/function.krsort.php) | The return type is true now; previously, it was bool. |
|  | [krsort](https://www.php.net/manual/en/function.krsort.php) | This function now does numeric string comparison under<br> SORT\_REGULAR using the standard PHP 8 rules. |
|  | [ksort](https://www.php.net/manual/en/function.ksort.php) | The return type is true now; previously, it was bool. |
|  | [ksort](https://www.php.net/manual/en/function.ksort.php) | This function now does numeric string comparison under<br> SORT\_REGULAR using the standard PHP 8 rules. |
|  | [lcfirst](https://www.php.net/manual/en/function.lcfirst.php) | Case conversion no longer depends on the locale set with<br> setlocale. Only ASCII characters will be converted. |
|  | [mb\_convert\_encoding](https://www.php.net/manual/en/function.mb-convert-encoding.php) | mb\_convert\_encoding will no longer return<br> the following non text encodings:<br> "Base64", "QPrint",<br> "UUencode", "HTML entities",<br> "7 bit" and "8 bit". |
|  | [mb\_convert\_kana](https://www.php.net/manual/en/function.mb-convert-kana.php) | A ValueError is now thrown if the<br> combination of different modes is invalid. |
|  | [mb\_detect\_encoding](https://www.php.net/manual/en/function.mb-detect-encoding.php) | mb\_detect\_encoding will no longer return<br> the following non text encodings:<br> "Base64", "QPrint",<br> "UUencode", "HTML entities",<br> "7 bit" and "8 bit". |
|  | [natcasesort](https://www.php.net/manual/en/function.natcasesort.php) | The return type is true now; previously, it was bool. |
|  | [natsort](https://www.php.net/manual/en/function.natsort.php) | The return type is true now; previously, it was bool. |
|  | [openlog](https://www.php.net/manual/en/function.openlog.php) | The function now always returns true. Previously it returned false on failure. |
|  | [pg\_close](https://www.php.net/manual/en/function.pg-close.php) | The return type is true now; previously, it was bool. |
|  | [pg\_untrace](https://www.php.net/manual/en/function.pg-untrace.php) | The return type is true now; previously, it was bool. |
|  | [random\_bytes](https://www.php.net/manual/en/function.random-bytes.php) | In case of a CSPRNG failure, this function will now throw a<br> Random\\RandomException. Previously a plain<br> Exception was thrown. |
|  | [random\_int](https://www.php.net/manual/en/function.random-int.php) | In case of a CSPRNG failure, this function will now throw a<br> Random\\RandomException. Previously a plain<br> Exception was thrown. |
|  | [rsort](https://www.php.net/manual/en/function.rsort.php) | The return type is true now; previously, it was bool. |
|  | [setcookie](https://www.php.net/manual/en/function.setcookie.php) | The date format of the cookie is now 'D, d M Y H:i:s \\G\\M\\T';<br> previously it was 'D, d-M-Y H:i:s T'. |
|  | [snmp\_set\_enum\_print](https://www.php.net/manual/en/function.snmp-set-enum-print.php) | The return type is true now; previously, it was bool. |
|  | [snmp\_set\_oid\_output\_format](https://www.php.net/manual/en/function.snmp-set-oid-output-format.php) | The return type is true now; previously, it was bool. |
|  | [snmp\_set\_quick\_print](https://www.php.net/manual/en/function.snmp-set-quick-print.php) | The return type is true now; previously, it was bool. |
|  | [snmp\_set\_valueretrieval](https://www.php.net/manual/en/function.snmp-set-valueretrieval.php) | The return type is true now; previously, it was bool. |
|  | [sort](https://www.php.net/manual/en/function.sort.php) | The return type is true now; previously, it was bool. |
|  | [str\_ireplace](https://www.php.net/manual/en/function.str-ireplace.php) | Case folding no longer depends on the locale set with<br> setlocale. Only ASCII case folding will be done.<br> Non-ASCII bytes will be compared by their byte value. |
|  | [str\_split](https://www.php.net/manual/en/function.str-split.php) | If string is empty an empty array is now returned.<br> Previously an array containing a single empty string was returned. |
|  | [strcasecmp](https://www.php.net/manual/en/function.strcasecmp.php) | This function is no longer guaranteed to return<br> strlen($string1) - strlen($string2) when string lengths<br> are not equal, but may now return -1 or<br> 1 instead. |
|  | [strcmp](https://www.php.net/manual/en/function.strcmp.php) | This function is no longer guaranteed to return<br> strlen($string1) - strlen($string2) when string lengths<br> are not equal, but may now return -1 or<br> 1 instead. |
|  | [stripos](https://www.php.net/manual/en/function.stripos.php) | Case folding no longer depends on the locale set with<br> setlocale. Only ASCII case folding will be done.<br> Non-ASCII bytes will be compared by their byte value. |
|  | [stristr](https://www.php.net/manual/en/function.stristr.php) | Case folding no longer depends on the locale set with<br> setlocale. Only ASCII case folding will be done.<br> Non-ASCII bytes will be compared by their byte value. |
|  | [strnatcasecmp](https://www.php.net/manual/en/function.strnatcasecmp.php) | This function is no longer guaranteed to return<br> strlen($string1) - strlen($string2) when string lengths<br> are not equal, but may now return -1 or<br> 1 instead. |
|  | [strnatcmp](https://www.php.net/manual/en/function.strnatcmp.php) | This function is no longer guaranteed to return<br> strlen($string1) - strlen($string2) when string lengths<br> are not equal, but may now return -1 or<br> 1 instead. |
|  | [strncasecmp](https://www.php.net/manual/en/function.strncasecmp.php) | This function is no longer guaranteed to return<br> strlen($string1) - strlen($string2) when string lengths<br> are not equal, but may now return -1 or<br> 1 instead. |
|  | [strncmp](https://www.php.net/manual/en/function.strncmp.php) | This function is no longer guaranteed to return<br> strlen($string1) - strlen($string2) when string lengths<br> are not equal, but may now return -1 or<br> 1 instead. |
|  | [strripos](https://www.php.net/manual/en/function.strripos.php) | Case folding no longer depends on the locale set with<br> setlocale. Only ASCII case folding will be done.<br> Non-ASCII bytes will be compared by their byte value. |
|  | [strtolower](https://www.php.net/manual/en/function.strtolower.php) | Case conversion no longer depends on the locale set with<br> setlocale. Only ASCII characters will be converted. |
|  | [strtoupper](https://www.php.net/manual/en/function.strtoupper.php) | Case conversion no longer depends on the locale set with<br> setlocale. Only ASCII characters will be converted. |
|  | [substr\_compare](https://www.php.net/manual/en/function.substr-compare.php) | This function is no longer guaranteed to return<br> strlen($string1) - strlen($string2) when string lengths<br> are not equal, but may now return -1 or<br> 1 instead. |
|  | [uasort](https://www.php.net/manual/en/function.uasort.php) | The return type is true now; previously, it was bool. |
|  | [ucfirst](https://www.php.net/manual/en/function.ucfirst.php) | Case conversion no longer depends on the locale set with<br> setlocale. Only ASCII characters will be converted. |
|  | [ucwords](https://www.php.net/manual/en/function.ucwords.php) | Case conversion no longer depends on the locale set with<br> setlocale. Only ASCII characters will be converted. |
|  | [uksort](https://www.php.net/manual/en/function.uksort.php) | The return type is true now; previously, it was bool. |
|  | [usort](https://www.php.net/manual/en/function.usort.php) | The return type is true now; previously, it was bool. |
|  | [utf8\_decode](https://www.php.net/manual/en/function.utf8-decode.php) | This function has been deprecated. |
|  | [utf8\_encode](https://www.php.net/manual/en/function.utf8-encode.php) | This function has been deprecated. |
|  | [var\_export](https://www.php.net/manual/en/function.var-export.php) | Exported class names are now fully qualified; previously, the leading<br> backslash was ommitted. |
|  | [IntlCalendar::clear](https://www.php.net/manual/en/intlcalendar.clear.php) | The return type is true now; previously, it was bool. |
|  | [IntlCalendar::set](https://www.php.net/manual/en/intlcalendar.set.php) | The return type is true now; previously, it was bool. |
|  | [IntlCalendar::setFirstDayOfWeek](https://www.php.net/manual/en/intlcalendar.setfirstdayofweek.php) | The return type is true now; previously, it was bool. |
|  | [IntlCalendar::setLenient](https://www.php.net/manual/en/intlcalendar.setlenient.php) | The return type is true now; previously, it was bool. |
|  | [IntlCalendar::setRepeatedWallTimeOption](https://www.php.net/manual/en/intlcalendar.setrepeatedwalltimeoption.php) | The return type is true now; previously, it was bool. |
|  | [IntlCalendar::setSkippedWallTimeOption](https://www.php.net/manual/en/intlcalendar.setskippedwalltimeoption.php) | The return type is true now; previously, it was bool. |
|  | [ReflectionEnum::getBackingType](https://www.php.net/manual/en/reflectionenum.getbackingtype.php) | The return type is now declared as ?ReflectionNamedType. Previously,<br> ?ReflectionType was declared. |
| 8.1.14 | [SplFileObject::\_\_toString](https://www.php.net/manual/en/splfileobject.tostring.php) | Changed from an alias of SplFileObject::fgets<br> to an implementation of SplFileObject::current<br> which returns a CSV string when the<br> SplFileObject::READ\_CSV flag is set. |
| 8.1.8 | [DateTime::createFromFormat](https://www.php.net/manual/en/datetime.createfromformat.php) | Now throws ValueError when NULL-bytes<br> are passed into datetime, which previously was silently<br> ignored. |
|  | [DateTimeImmutable::createFromFormat](https://www.php.net/manual/en/datetimeimmutable.createfromformat.php) | Now throws ValueError when NULL-bytes<br> are passed into datetime, which previously was silently<br> ignored. |
|  | [date\_parse\_from\_format](https://www.php.net/manual/en/function.date-parse-from-format.php) | Now throws ValueError when NULL-bytes<br> are passed into datetime, which previously was silently<br> ignored. |
| 8.1.0 | [DateTime::setTime](https://www.php.net/manual/en/datetime.settime.php) | The behaviour with double existing hours (during the fall-back<br> DST transition) changed. Previously PHP would pick the second occurrence<br> (after the DST transition), instead of the first occurrence (before DST<br> transition). |
|  | [DateTimeImmutable::setTime](https://www.php.net/manual/en/datetimeimmutable.settime.php) | The behaviour with double existing hours (during the fall-back<br> DST transition) changed. Previously PHP would pick the second occurrence<br> (after the DST transition), instead of the first occurrence (before DST<br> transition). |
|  | [DirectoryIterator::key](https://www.php.net/manual/en/directoryiterator.key.php) | When the iterator is uninitialized, an Error is<br> thrown now. Previously, the method returned false. |
|  | [DOMDocument::createComment](https://www.php.net/manual/en/domdocument.createcomment.php) | In case of an error, a DomException is thrown now.<br> Previously, false was returned. |
|  | [DOMDocument::createDocumentFragment](https://www.php.net/manual/en/domdocument.createdocumentfragment.php) | In case of an error, a DomException is thrown now.<br> Previously, false was returned. |
|  | [DOMDocument::createTextNode](https://www.php.net/manual/en/domdocument.createtextnode.php) | In case of an error, a DomException is thrown now.<br> Previously, false was returned. |
|  | [current](https://www.php.net/manual/en/function.current.php) | Calling this function on objects is deprecated.<br> Either convert the object to an array using get\_mangled\_object\_vars first, or use the methods<br> provided by a class that implements Iterator, such as ArrayIterator, instead. |
|  | [date\_sunrise](https://www.php.net/manual/en/function.date-sunrise.php) | This function has been deprecated in favor of date\_sun\_info. |
|  | [date\_sunset](https://www.php.net/manual/en/function.date-sunset.php) | This function has been deprecated in favor of date\_sun\_info. |
|  | [dba\_popen](https://www.php.net/manual/en/function.dba-popen.php) | handler is now nullable. |
|  | [define](https://www.php.net/manual/en/function.define.php) | value can now be an object. |
|  | [end](https://www.php.net/manual/en/function.end.php) | Calling this function on objects is deprecated.<br> Either convert the object to an array using get\_mangled\_object\_vars first, or use the methods<br> provided by a class that implements Iterator, such as ArrayIterator, instead. |
|  | [exif\_imagetype](https://www.php.net/manual/en/function.exif-imagetype.php) | Added AVIF support. |
|  | [finfo\_buffer](https://www.php.net/manual/en/function.finfo-buffer.php) | The finfo parameter expects an finfo<br> instance now; previously, a resource was expected. |
|  | [finfo\_close](https://www.php.net/manual/en/function.finfo-close.php) | The finfo parameter expects an finfo<br> instance now; previously, a resource was expected. |
|  | [finfo\_file](https://www.php.net/manual/en/function.finfo-file.php) | The finfo parameter expects an finfo<br> instance now; previously, a resource was expected. |
|  | [finfo\_open](https://www.php.net/manual/en/function.finfo-open.php) | Returns an finfo instance now;<br> previously, a resource was returned. |
|  | [finfo\_set\_flags](https://www.php.net/manual/en/function.finfo-set-flags.php) | The finfo parameter expects an finfo<br> instance now; previously, a resource was expected. |
|  | [fputcsv](https://www.php.net/manual/en/function.fputcsv.php) | The optional eol parameter has been added. |
|  | [ftp\_alloc](https://www.php.net/manual/en/function.ftp-alloc.php) | The ftp parameter expects an FTP\\Connection<br> instance now; previously, a resource was expected. |
|  | [ftp\_append](https://www.php.net/manual/en/function.ftp-append.php) | The ftp parameter expects an FTP\\Connection<br> instance now; previously, a resource was expected. |
|  | [ftp\_cdup](https://www.php.net/manual/en/function.ftp-cdup.php) | The ftp parameter expects an FTP\\Connection<br> instance now; previously, a resource was expected. |
|  | [ftp\_chdir](https://www.php.net/manual/en/function.ftp-chdir.php) | The ftp parameter expects an FTP\\Connection<br> instance now; previously, a resource was expected. |
|  | [ftp\_chmod](https://www.php.net/manual/en/function.ftp-chmod.php) | The ftp parameter expects an FTP\\Connection<br> instance now; previously, a resource was expected. |
|  | [ftp\_close](https://www.php.net/manual/en/function.ftp-close.php) | The ftp parameter expects an FTP\\Connection<br> instance now; previously, a resource was expected. |
|  | [ftp\_connect](https://www.php.net/manual/en/function.ftp-connect.php) | Returns an FTP\\Connection instance now;<br> previously, a resource was returned. |
|  | [ftp\_delete](https://www.php.net/manual/en/function.ftp-delete.php) | The ftp parameter expects an FTP\\Connection<br> instance now; previously, a resource was expected. |
|  | [ftp\_exec](https://www.php.net/manual/en/function.ftp-exec.php) | The ftp parameter expects an FTP\\Connection<br> instance now; previously, a resource was expected. |
|  | [ftp\_fget](https://www.php.net/manual/en/function.ftp-fget.php) | The ftp parameter expects an FTP\\Connection<br> instance now; previously, a resource was expected. |
|  | [ftp\_fput](https://www.php.net/manual/en/function.ftp-fput.php) | The ftp parameter expects an FTP\\Connection<br> instance now; previously, a resource was expected. |
|  | [ftp\_get](https://www.php.net/manual/en/function.ftp-get.php) | The ftp parameter expects an FTP\\Connection<br> instance now; previously, a resource was expected. |
|  | [ftp\_get\_option](https://www.php.net/manual/en/function.ftp-get-option.php) | The ftp parameter expects an FTP\\Connection<br> instance now; previously, a resource was expected. |
|  | [ftp\_login](https://www.php.net/manual/en/function.ftp-login.php) | The ftp parameter expects an FTP\\Connection<br> instance now; previously, a resource was expected. |
|  | [ftp\_mdtm](https://www.php.net/manual/en/function.ftp-mdtm.php) | The ftp parameter expects an FTP\\Connection<br> instance now; previously, a resource was expected. |
|  | [ftp\_mkdir](https://www.php.net/manual/en/function.ftp-mkdir.php) | The ftp parameter expects an FTP\\Connection<br> instance now; previously, a resource was expected. |
|  | [ftp\_mlsd](https://www.php.net/manual/en/function.ftp-mlsd.php) | The ftp parameter expects an FTP\\Connection<br> instance now; previously, a resource was expected. |
|  | [ftp\_nb\_continue](https://www.php.net/manual/en/function.ftp-nb-continue.php) | The ftp parameter expects an FTP\\Connection<br> instance now; previously, a resource was expected. |
|  | [ftp\_nb\_fget](https://www.php.net/manual/en/function.ftp-nb-fget.php) | The ftp parameter expects an FTP\\Connection<br> instance now; previously, a resource was expected. |
|  | [ftp\_nb\_fput](https://www.php.net/manual/en/function.ftp-nb-fput.php) | The ftp parameter expects an FTP\\Connection<br> instance now; previously, a resource was expected. |
|  | [ftp\_nb\_get](https://www.php.net/manual/en/function.ftp-nb-get.php) | The ftp parameter expects an FTP\\Connection<br> instance now; previously, a resource was expected. |
|  | [ftp\_nb\_put](https://www.php.net/manual/en/function.ftp-nb-put.php) | The ftp parameter expects an FTP\\Connection<br> instance now; previously, a resource was expected. |
|  | [ftp\_nlist](https://www.php.net/manual/en/function.ftp-nlist.php) | The ftp parameter expects an FTP\\Connection<br> instance now; previously, a resource was expected. |
|  | [ftp\_pasv](https://www.php.net/manual/en/function.ftp-pasv.php) | The ftp parameter expects an FTP\\Connection<br> instance now; previously, a resource was expected. |
|  | [ftp\_put](https://www.php.net/manual/en/function.ftp-put.php) | The ftp parameter expects an FTP\\Connection<br> instance now; previously, a resource was expected. |
|  | [ftp\_pwd](https://www.php.net/manual/en/function.ftp-pwd.php) | The ftp parameter expects an FTP\\Connection<br> instance now; previously, a resource was expected. |
|  | [ftp\_raw](https://www.php.net/manual/en/function.ftp-raw.php) | The ftp parameter expects an FTP\\Connection<br> instance now; previously, a resource was expected. |
|  | [ftp\_rawlist](https://www.php.net/manual/en/function.ftp-rawlist.php) | The ftp parameter expects an FTP\\Connection<br> instance now; previously, a resource was expected. |
|  | [ftp\_rename](https://www.php.net/manual/en/function.ftp-rename.php) | The ftp parameter expects an FTP\\Connection<br> instance now; previously, a resource was expected. |
|  | [ftp\_rmdir](https://www.php.net/manual/en/function.ftp-rmdir.php) | The ftp parameter expects an FTP\\Connection<br> instance now; previously, a resource was expected. |
|  | [ftp\_set\_option](https://www.php.net/manual/en/function.ftp-set-option.php) | The ftp parameter expects an FTP\\Connection<br> instance now; previously, a resource was expected. |
|  | [ftp\_site](https://www.php.net/manual/en/function.ftp-site.php) | The ftp parameter expects an FTP\\Connection<br> instance now; previously, a resource was expected. |
|  | [ftp\_size](https://www.php.net/manual/en/function.ftp-size.php) | The ftp parameter expects an FTP\\Connection<br> instance now; previously, a resource was expected. |
|  | [ftp\_ssl\_connect](https://www.php.net/manual/en/function.ftp-ssl-connect.php) | Returns an FTP\\Connection instance now;<br> previously, a resource was returned. |
|  | [ftp\_systype](https://www.php.net/manual/en/function.ftp-systype.php) | The ftp parameter expects an FTP\\Connection<br> instance now; previously, a resource was expected. |
|  | [get\_html\_translation\_table](https://www.php.net/manual/en/function.get-html-translation-table.php) | flags changed from ENT\_COMPAT to ENT\_QUOTES \| ENT\_SUBSTITUTE \| ENT\_HTML401. |
|  | [gmp\_init](https://www.php.net/manual/en/function.gmp-init.php) | Support for explicit octal prefixes 0o and<br> 0o has been added for num strings.<br> Interpretation of such prefixes when base is<br> 0 has also been added. |
|  | [hash](https://www.php.net/manual/en/function.hash.php) | The options parameter has been added. |
|  | [hash\_algos](https://www.php.net/manual/en/function.hash-algos.php) | Support for MurmurHash3 and xxHash algorithms has been added. |
|  | [hash\_file](https://www.php.net/manual/en/function.hash-file.php) | The options parameter has been added. |
|  | [hash\_init](https://www.php.net/manual/en/function.hash-init.php) | The options parameter has been added. |
|  | [html\_entity\_decode](https://www.php.net/manual/en/function.html-entity-decode.php) | flags changed from ENT\_COMPAT to ENT\_QUOTES \| ENT\_SUBSTITUTE \| ENT\_HTML401. |
|  | [htmlentities](https://www.php.net/manual/en/function.htmlentities.php) | flags changed from ENT\_COMPAT to ENT\_QUOTES \| ENT\_SUBSTITUTE \| ENT\_HTML401. |
|  | [htmlspecialchars](https://www.php.net/manual/en/function.htmlspecialchars.php) | flags changed from ENT\_COMPAT to ENT\_QUOTES \| ENT\_SUBSTITUTE \| ENT\_HTML401. |
|  | [htmlspecialchars\_decode](https://www.php.net/manual/en/function.htmlspecialchars-decode.php) | flags changed from ENT\_COMPAT to ENT\_QUOTES \| ENT\_SUBSTITUTE \| ENT\_HTML401. |
|  | [imagechar](https://www.php.net/manual/en/function.imagechar.php) | The font parameter now accepts both an GdFont instance<br> and an int; previously only int was accepted. |
|  | [imagecharup](https://www.php.net/manual/en/function.imagecharup.php) | The font parameter now accepts both an GdFont instance<br> and an int; previously only int was accepted. |
|  | [imagefilledpolygon](https://www.php.net/manual/en/function.imagefilledpolygon.php) | The parameter num\_points has been deprecated. |
|  | [imagefontheight](https://www.php.net/manual/en/function.imagefontheight.php) | The font parameter now accepts both an GdFont instance<br> and an int; previously only int was accepted. |
|  | [imagefontwidth](https://www.php.net/manual/en/function.imagefontwidth.php) | The font parameter now accepts both an GdFont instance<br> and an int; previously only int was accepted. |
|  | [imageloadfont](https://www.php.net/manual/en/function.imageloadfont.php) | Returns an GdFont instance now;<br> previously, an int was returned. |
|  | [imageopenpolygon](https://www.php.net/manual/en/function.imageopenpolygon.php) | The parameter num\_points has been deprecated. |
|  | [imagepolygon](https://www.php.net/manual/en/function.imagepolygon.php) | The parameter num\_points has been deprecated. |
|  | [imagestring](https://www.php.net/manual/en/function.imagestring.php) | The font parameter now accepts both an GdFont instance<br> and an int; previously only int was accepted. |
|  | [imagestringup](https://www.php.net/manual/en/function.imagestringup.php) | The font parameter now accepts both an GdFont instance<br> and an int; previously only int was accepted. |
|  | [imagetypes](https://www.php.net/manual/en/function.imagetypes.php) | IMG\_AVIF added. |
|  | [ini\_set](https://www.php.net/manual/en/function.ini-set.php) | value now accepts any scalar type (including null).<br> Previously, only string values were accepted. |
|  | [key](https://www.php.net/manual/en/function.key.php) | Calling this function on objects is deprecated.<br> Either convert the object to an array using get\_mangled\_object\_vars first, or use the methods<br> provided by a class that implements Iterator, such as ArrayIterator, instead. |
|  | [ldap\_add](https://www.php.net/manual/en/function.ldap-add.php) | The ldap parameter expects an LDAP\\Connection<br> instance now; previously, a valid ldap link resource was expected. |
|  | [ldap\_add\_ext](https://www.php.net/manual/en/function.ldap-add-ext.php) | The ldap parameter expects an LDAP\\Connection<br> instance now; previously, a valid ldap link resource was expected. |
|  | [ldap\_add\_ext](https://www.php.net/manual/en/function.ldap-add-ext.php) | Returns an LDAP\\Result instance now;<br> previously, a resource was returned. |
|  | [ldap\_bind](https://www.php.net/manual/en/function.ldap-bind.php) | The ldap parameter expects an LDAP\\Connection<br> instance now; previously, a valid ldap link resource was expected. |
|  | [ldap\_bind\_ext](https://www.php.net/manual/en/function.ldap-bind-ext.php) | The ldap parameter expects an LDAP\\Connection<br> instance now; previously, a valid ldap link resource was expected. |
|  | [ldap\_bind\_ext](https://www.php.net/manual/en/function.ldap-bind-ext.php) | Returns an LDAP\\Result instance now;<br> previously, a resource was returned. |
|  | [ldap\_compare](https://www.php.net/manual/en/function.ldap-compare.php) | The ldap parameter expects an LDAP\\Connection<br> instance now; previously, a valid ldap link resource was expected. |
|  | [ldap\_connect](https://www.php.net/manual/en/function.ldap-connect.php) | Returns an LDAP\\Connection instance now;<br> previously, a resource was returned. |
|  | [ldap\_count\_entries](https://www.php.net/manual/en/function.ldap-count-entries.php) | The ldap parameter expects an LDAP\\Connection<br> instance now; previously, a valid ldap link resource was expected. |
|  | [ldap\_count\_entries](https://www.php.net/manual/en/function.ldap-count-entries.php) | The result parameter expects an LDAP\\Result<br> instance now; previously, a valid ldap result resource was expected. |
|  | [ldap\_count\_references](https://www.php.net/manual/en/function.ldap-count-references.php) | The ldap parameter expects an LDAP\\Connection<br> instance now; previously, a valid ldap link resource was expected. |
|  | [ldap\_count\_references](https://www.php.net/manual/en/function.ldap-count-references.php) | The result parameter expects an LDAP\\Result<br> instance now; previously, a valid ldap result resource was expected. |
|  | [ldap\_delete](https://www.php.net/manual/en/function.ldap-delete.php) | The ldap parameter expects an LDAP\\Connection<br> instance now; previously, a valid ldap link resource was expected. |
|  | [ldap\_delete\_ext](https://www.php.net/manual/en/function.ldap-delete-ext.php) | The ldap parameter expects an LDAP\\Connection<br> instance now; previously, a valid ldap link resource was expected. |
|  | [ldap\_delete\_ext](https://www.php.net/manual/en/function.ldap-delete-ext.php) | Returns an LDAP\\Result instance now;<br> previously, a resource was returned. |
|  | [ldap\_errno](https://www.php.net/manual/en/function.ldap-errno.php) | The ldap parameter expects an LDAP\\Connection<br> instance now; previously, a valid ldap link resource was expected. |
|  | [ldap\_error](https://www.php.net/manual/en/function.ldap-error.php) | The ldap parameter expects an LDAP\\Connection<br> instance now; previously, a valid ldap link resource was expected. |
|  | [ldap\_exop](https://www.php.net/manual/en/function.ldap-exop.php) | The ldap parameter expects an LDAP\\Connection<br> instance now; previously, a valid ldap link resource was expected. |
|  | [ldap\_exop\_passwd](https://www.php.net/manual/en/function.ldap-exop-passwd.php) | The ldap parameter expects an LDAP\\Connection<br> instance now; previously, a valid ldap link resource was expected. |
|  | [ldap\_exop\_refresh](https://www.php.net/manual/en/function.ldap-exop-refresh.php) | The ldap parameter expects an LDAP\\Connection<br> instance now; previously, a valid ldap link resource was expected. |
|  | [ldap\_exop\_whoami](https://www.php.net/manual/en/function.ldap-exop-whoami.php) | The ldap parameter expects an LDAP\\Connection<br> instance now; previously, a valid ldap link resource was expected. |
|  | [ldap\_first\_attribute](https://www.php.net/manual/en/function.ldap-first-attribute.php) | The ldap parameter expects an LDAP\\Connection<br> instance now; previously, a valid ldap link resource was expected. |
|  | [ldap\_first\_attribute](https://www.php.net/manual/en/function.ldap-first-attribute.php) | The entry parameter expects an LDAP\\ResultEntry<br> instance now; previously, a valid ldap result entry resource was expected. |
|  | [ldap\_first\_entry](https://www.php.net/manual/en/function.ldap-first-entry.php) | The ldap parameter expects an LDAP\\Connection<br> instance now; previously, a valid ldap link resource was expected. |
|  | [ldap\_first\_entry](https://www.php.net/manual/en/function.ldap-first-entry.php) | The result parameter expects an LDAP\\Result<br> instance now; previously, a valid ldap result resource was expected. |
|  | [ldap\_first\_entry](https://www.php.net/manual/en/function.ldap-first-entry.php) | Returns an LDAP\\ResultEntry instance now;<br> previously, a resource was returned. |
|  | [ldap\_free\_result](https://www.php.net/manual/en/function.ldap-free-result.php) | The result parameter expects an LDAP\\Result<br> instance now; previously, a valid ldap result resource was expected. |
|  | [ldap\_get\_attributes](https://www.php.net/manual/en/function.ldap-get-attributes.php) | The ldap parameter expects an LDAP\\Connection<br> instance now; previously, a valid ldap link resource was expected. |
|  | [ldap\_get\_attributes](https://www.php.net/manual/en/function.ldap-get-attributes.php) | The entry parameter expects an LDAP\\ResultEntry<br> instance now; previously, a valid ldap result entry resource was expected. |
|  | [ldap\_get\_dn](https://www.php.net/manual/en/function.ldap-get-dn.php) | The ldap parameter expects an LDAP\\Connection<br> instance now; previously, a valid ldap link resource was expected. |
|  | [ldap\_get\_dn](https://www.php.net/manual/en/function.ldap-get-dn.php) | The entry parameter expects an LDAP\\ResultEntry<br> instance now; previously, a valid ldap result entry resource was expected. |
|  | [ldap\_get\_entries](https://www.php.net/manual/en/function.ldap-get-entries.php) | The ldap parameter expects an LDAP\\Connection<br> instance now; previously, a valid ldap link resource was expected. |
|  | [ldap\_get\_entries](https://www.php.net/manual/en/function.ldap-get-entries.php) | The result parameter expects an LDAP\\Result<br> instance now; previously, a valid ldap result resource was expected. |
|  | [ldap\_get\_option](https://www.php.net/manual/en/function.ldap-get-option.php) | The ldap parameter expects an LDAP\\Connection<br> instance now; previously, a valid ldap link resource was expected. |
|  | [ldap\_get\_values](https://www.php.net/manual/en/function.ldap-get-values.php) | The ldap parameter expects an LDAP\\Connection<br> instance now; previously, a valid ldap link resource was expected. |
|  | [ldap\_get\_values](https://www.php.net/manual/en/function.ldap-get-values.php) | The entry parameter expects an LDAP\\ResultEntry<br> instance now; previously, a valid ldap result entry resource was expected. |
|  | [ldap\_get\_values\_len](https://www.php.net/manual/en/function.ldap-get-values-len.php) | The ldap parameter expects an LDAP\\Connection<br> instance now; previously, a valid ldap link resource was expected. |
|  | [ldap\_get\_values\_len](https://www.php.net/manual/en/function.ldap-get-values-len.php) | The entry parameter expects an LDAP\\ResultEntry<br> instance now; previously, a valid ldap result entry resource was expected. |
|  | [ldap\_list](https://www.php.net/manual/en/function.ldap-list.php) | The ldap parameter expects an LDAP\\Connection<br> instance now; previously, a valid ldap link resource was expected. |
|  | [ldap\_list](https://www.php.net/manual/en/function.ldap-list.php) | Returns an LDAP\\Result instance now;<br> previously, a resource was returned. |
|  | [ldap\_mod\_add](https://www.php.net/manual/en/function.ldap-mod-add.php) | The ldap parameter expects an LDAP\\Connection<br> instance now; previously, a valid ldap link resource was expected. |
|  | [ldap\_mod\_del](https://www.php.net/manual/en/function.ldap-mod-del.php) | The ldap parameter expects an LDAP\\Connection<br> instance now; previously, a valid ldap link resource was expected. |
|  | [ldap\_mod\_replace](https://www.php.net/manual/en/function.ldap-mod-replace.php) | The ldap parameter expects an LDAP\\Connection<br> instance now; previously, a valid ldap link resource was expected. |
|  | [ldap\_modify\_batch](https://www.php.net/manual/en/function.ldap-modify-batch.php) | The ldap parameter expects an LDAP\\Connection<br> instance now; previously, a valid ldap link resource was expected. |
|  | [ldap\_mod\_add\_ext](https://www.php.net/manual/en/function.ldap-mod_add-ext.php) | The ldap parameter expects an LDAP\\Connection<br> instance now; previously, a valid ldap link resource was expected. |
|  | [ldap\_mod\_add\_ext](https://www.php.net/manual/en/function.ldap-mod_add-ext.php) | Returns an LDAP\\Result instance now;<br> previously, a resource was returned. |
|  | [ldap\_mod\_del\_ext](https://www.php.net/manual/en/function.ldap-mod_del-ext.php) | The ldap parameter expects an LDAP\\Connection<br> instance now; previously, a valid ldap link resource was expected. |
|  | [ldap\_mod\_del\_ext](https://www.php.net/manual/en/function.ldap-mod_del-ext.php) | Returns an LDAP\\Result instance now;<br> previously, a resource was returned. |
|  | [ldap\_mod\_replace\_ext](https://www.php.net/manual/en/function.ldap-mod_replace-ext.php) | The ldap parameter expects an LDAP\\Connection<br> instance now; previously, a valid ldap link resource was expected. |
|  | [ldap\_mod\_replace\_ext](https://www.php.net/manual/en/function.ldap-mod_replace-ext.php) | Returns an LDAP\\Result instance now;<br> previously, a resource was returned. |
|  | [ldap\_next\_attribute](https://www.php.net/manual/en/function.ldap-next-attribute.php) | The ldap parameter expects an LDAP\\Connection<br> instance now; previously, a valid ldap link resource was expected. |
|  | [ldap\_next\_attribute](https://www.php.net/manual/en/function.ldap-next-attribute.php) | The entry parameter expects an LDAP\\ResultEntry<br> instance now; previously, a valid ldap result entry resource was expected. |
|  | [ldap\_next\_entry](https://www.php.net/manual/en/function.ldap-next-entry.php) | The ldap parameter expects an LDAP\\Connection<br> instance now; previously, a valid ldap link resource was expected. |
|  | [ldap\_next\_entry](https://www.php.net/manual/en/function.ldap-next-entry.php) | The entry parameter expects an LDAP\\ResultEntry<br> instance now; previously, a valid ldap result entry resource was expected. |
|  | [ldap\_next\_entry](https://www.php.net/manual/en/function.ldap-next-entry.php) | Returns an LDAP\\Result instance now;<br> previously, a resource was returned. |
|  | [ldap\_parse\_exop](https://www.php.net/manual/en/function.ldap-parse-exop.php) | The ldap parameter expects an LDAP\\Connection<br> instance now; previously, a valid ldap link resource was expected. |
|  | [ldap\_parse\_exop](https://www.php.net/manual/en/function.ldap-parse-exop.php) | The result parameter expects an LDAP\\Result<br> instance now; previously, a valid ldap result resource was expected. |
|  | [ldap\_parse\_result](https://www.php.net/manual/en/function.ldap-parse-result.php) | The ldap parameter expects an LDAP\\Connection<br> instance now; previously, a valid ldap link resource was expected. |
|  | [ldap\_parse\_result](https://www.php.net/manual/en/function.ldap-parse-result.php) | The result parameter expects an LDAP\\Result<br> instance now; previously, a valid ldap result resource was expected. |
|  | [ldap\_read](https://www.php.net/manual/en/function.ldap-read.php) | The ldap parameter expects an LDAP\\Connection<br> instance now; previously, a valid ldap link resource was expected. |
|  | [ldap\_read](https://www.php.net/manual/en/function.ldap-read.php) | Returns an LDAP\\Result instance now;<br> previously, a resource was returned. |
|  | [ldap\_rename](https://www.php.net/manual/en/function.ldap-rename.php) | The ldap parameter expects an LDAP\\Connection<br> instance now; previously, a valid ldap link resource was expected. |
|  | [ldap\_rename\_ext](https://www.php.net/manual/en/function.ldap-rename-ext.php) | The ldap parameter expects an LDAP\\Connection<br> instance now; previously, a valid ldap link resource was expected. |
|  | [ldap\_rename\_ext](https://www.php.net/manual/en/function.ldap-rename-ext.php) | Returns an LDAP\\Result instance now;<br> previously, a resource was returned. |
|  | [ldap\_sasl\_bind](https://www.php.net/manual/en/function.ldap-sasl-bind.php) | The ldap parameter expects an LDAP\\Connection<br> instance now; previously, a valid ldap link resource was expected. |
|  | [ldap\_search](https://www.php.net/manual/en/function.ldap-search.php) | The ldap parameter expects an LDAP\\Connection<br> instance now; previously, a valid ldap link resource was expected. |
|  | [ldap\_search](https://www.php.net/manual/en/function.ldap-search.php) | Returns an LDAP\\Result instance now;<br> previously, a resource was returned. |
|  | [ldap\_set\_option](https://www.php.net/manual/en/function.ldap-set-option.php) | The ldap parameter expects an LDAP\\Connection<br> instance now; previously, a valid ldap link resource was expected. |
|  | [ldap\_set\_rebind\_proc](https://www.php.net/manual/en/function.ldap-set-rebind-proc.php) | The ldap parameter expects an LDAP\\Connection<br> instance now; previously, a valid ldap link resource was expected. |
|  | [ldap\_unbind](https://www.php.net/manual/en/function.ldap-unbind.php) | The ldap parameter expects an LDAP\\Connection<br> instance now; previously, a valid ldap link resource was expected. |
|  | [mb\_check\_encoding](https://www.php.net/manual/en/function.mb-check-encoding.php) | Calling this function with null as value or without argument is deprecated. |
|  | [mhash](https://www.php.net/manual/en/function.mhash.php) | This function has been deprecated.<br> Use the hash\_\*() functions instead. |
|  | [mhash\_count](https://www.php.net/manual/en/function.mhash-count.php) | This function has been deprecated.<br> Use the hash\_\*() functions instead. |
|  | [mhash\_get\_block\_size](https://www.php.net/manual/en/function.mhash-get-block-size.php) | This function has been deprecated.<br> Use the hash\_\*() functions instead. |
|  | [mhash\_get\_hash\_name](https://www.php.net/manual/en/function.mhash-get-hash-name.php) | This function has been deprecated.<br> Use the hash\_\*() functions instead. |
|  | [mhash\_keygen\_s2k](https://www.php.net/manual/en/function.mhash-keygen-s2k.php) | This function has been deprecated.<br> Use the hash\_\*() functions instead. |
|  | [next](https://www.php.net/manual/en/function.next.php) | Calling this function on objects is deprecated.<br> Either convert the object to an array using get\_mangled\_object\_vars first, or use the methods<br> provided by a class that implements Iterator, such as ArrayIterator, instead. |
|  | [odbc\_result\_all](https://www.php.net/manual/en/function.odbc-result-all.php) | This function has been deprecated. |
|  | [openssl\_cms\_encrypt](https://www.php.net/manual/en/function.openssl-cms-encrypt.php) | The default cipher algorithm (cipher\_algo) is now<br> AES-128-CBC (OPENSSL\_CIPHER\_AES\_128\_CBC). Previously,<br> PKCS7/CMS was used (OPENSSL\_CIPHER\_RC2\_40). |
|  | [openssl\_decrypt](https://www.php.net/manual/en/function.openssl-decrypt.php) | tag is now nullable. |
|  | [openssl\_pkcs7\_encrypt](https://www.php.net/manual/en/function.openssl-pkcs7-encrypt.php) | The default cipher algorithm (cipher\_algo) is now<br> AES-128-CBC (OPENSSL\_CIPHER\_AES\_128\_CBC). Previously,<br> PKCS7/CMS was used (OPENSSL\_CIPHER\_RC2\_40). |
|  | [pg\_affected\_rows](https://www.php.net/manual/en/function.pg-affected-rows.php) | The result parameter expects an PgSql\\Result<br> instance now; previously, a resource was expected. |
|  | [pg\_cancel\_query](https://www.php.net/manual/en/function.pg-cancel-query.php) | The connection parameter expects an PgSql\\Connection<br> instance now; previously, a resource was expected. |
|  | [pg\_client\_encoding](https://www.php.net/manual/en/function.pg-client-encoding.php) | The connection parameter expects an PgSql\\Connection<br> instance now; previously, a resource was expected. |
|  | [pg\_close](https://www.php.net/manual/en/function.pg-close.php) | The connection parameter expects an PgSql\\Connection<br> instance now; previously, a resource was expected. |
|  | [pg\_connect](https://www.php.net/manual/en/function.pg-connect.php) | Returns an PgSql\\Connection instance now;<br> previously, a resource was returned. |
|  | [pg\_connect\_poll](https://www.php.net/manual/en/function.pg-connect-poll.php) | The connection parameter expects an PgSql\\Connection<br> instance now; previously, a resource was expected. |
|  | [pg\_connection\_busy](https://www.php.net/manual/en/function.pg-connection-busy.php) | The connection parameter expects an PgSql\\Connection<br> instance now; previously, a resource was expected. |
|  | [pg\_connection\_reset](https://www.php.net/manual/en/function.pg-connection-reset.php) | The connection parameter expects an PgSql\\Connection<br> instance now; previously, a resource was expected. |
|  | [pg\_connection\_status](https://www.php.net/manual/en/function.pg-connection-status.php) | The connection parameter expects an PgSql\\Connection<br> instance now; previously, a resource was expected. |
|  | [pg\_consume\_input](https://www.php.net/manual/en/function.pg-consume-input.php) | The connection parameter expects an PgSql\\Connection<br> instance now; previously, a resource was expected. |
|  | [pg\_convert](https://www.php.net/manual/en/function.pg-convert.php) | The connection parameter expects an PgSql\\Connection<br> instance now; previously, a resource was expected. |
|  | [pg\_copy\_from](https://www.php.net/manual/en/function.pg-copy-from.php) | The connection parameter expects an PgSql\\Connection<br> instance now; previously, a resource was expected. |
|  | [pg\_copy\_to](https://www.php.net/manual/en/function.pg-copy-to.php) | The connection parameter expects an PgSql\\Connection<br> instance now; previously, a resource was expected. |
|  | [pg\_dbname](https://www.php.net/manual/en/function.pg-dbname.php) | The connection parameter expects an PgSql\\Connection<br> instance now; previously, a resource was expected. |
|  | [pg\_delete](https://www.php.net/manual/en/function.pg-delete.php) | The connection parameter expects an PgSql\\Connection<br> instance now; previously, a resource was expected. |
|  | [pg\_end\_copy](https://www.php.net/manual/en/function.pg-end-copy.php) | The connection parameter expects an PgSql\\Connection<br> instance now; previously, a resource was expected. |
|  | [pg\_escape\_bytea](https://www.php.net/manual/en/function.pg-escape-bytea.php) | The connection parameter expects an PgSql\\Connection<br> instance now; previously, a resource was expected. |
|  | [pg\_escape\_identifier](https://www.php.net/manual/en/function.pg-escape-identifier.php) | The connection parameter expects an PgSql\\Connection<br> instance now; previously, a resource was expected. |
|  | [pg\_escape\_literal](https://www.php.net/manual/en/function.pg-escape-literal.php) | The connection parameter expects an PgSql\\Connection<br> instance now; previously, a resource was expected. |
|  | [pg\_escape\_string](https://www.php.net/manual/en/function.pg-escape-string.php) | The connection parameter expects an PgSql\\Connection<br> instance now; previously, a resource was expected. |
|  | [pg\_execute](https://www.php.net/manual/en/function.pg-execute.php) | Returns an PgSql\\Result instance now;<br> previously, a resource was returned. |
|  | [pg\_execute](https://www.php.net/manual/en/function.pg-execute.php) | The connection parameter expects an PgSql\\Connection<br> instance now; previously, a resource was expected. |
|  | [pg\_fetch\_all](https://www.php.net/manual/en/function.pg-fetch-all.php) | The result parameter expects an PgSql\\Result<br> instance now; previously, a resource was expected. |
|  | [pg\_fetch\_all\_columns](https://www.php.net/manual/en/function.pg-fetch-all-columns.php) | The result parameter expects an PgSql\\Result<br> instance now; previously, a resource was expected. |
|  | [pg\_fetch\_array](https://www.php.net/manual/en/function.pg-fetch-array.php) | The result parameter expects an PgSql\\Result<br> instance now; previously, a resource was expected. |
|  | [pg\_fetch\_assoc](https://www.php.net/manual/en/function.pg-fetch-assoc.php) | The result parameter expects an PgSql\\Result<br> instance now; previously, a resource was expected. |
|  | [pg\_fetch\_object](https://www.php.net/manual/en/function.pg-fetch-object.php) | The result parameter expects an PgSql\\Result<br> instance now; previously, a resource was expected. |
|  | [pg\_fetch\_result](https://www.php.net/manual/en/function.pg-fetch-result.php) | The result parameter expects an PgSql\\Result<br> instance now; previously, a resource was expected. |
|  | [pg\_fetch\_row](https://www.php.net/manual/en/function.pg-fetch-row.php) | The result parameter expects an PgSql\\Result<br> instance now; previously, a resource was expected. |
|  | [pg\_field\_is\_null](https://www.php.net/manual/en/function.pg-field-is-null.php) | The result parameter expects an PgSql\\Result<br> instance now; previously, a resource was expected. |
|  | [pg\_field\_name](https://www.php.net/manual/en/function.pg-field-name.php) | The result parameter expects an PgSql\\Result<br> instance now; previously, a resource was expected. |
|  | [pg\_field\_num](https://www.php.net/manual/en/function.pg-field-num.php) | The result parameter expects an PgSql\\Result<br> instance now; previously, a resource was expected. |
|  | [pg\_field\_prtlen](https://www.php.net/manual/en/function.pg-field-prtlen.php) | The result parameter expects an PgSql\\Result<br> instance now; previously, a resource was expected. |
|  | [pg\_field\_size](https://www.php.net/manual/en/function.pg-field-size.php) | The result parameter expects an PgSql\\Result<br> instance now; previously, a resource was expected. |
|  | [pg\_field\_table](https://www.php.net/manual/en/function.pg-field-table.php) | The result parameter expects an PgSql\\Result<br> instance now; previously, a resource was expected. |
|  | [pg\_field\_type](https://www.php.net/manual/en/function.pg-field-type.php) | The result parameter expects an PgSql\\Result<br> instance now; previously, a resource was expected. |
|  | [pg\_field\_type\_oid](https://www.php.net/manual/en/function.pg-field-type-oid.php) | The result parameter expects an PgSql\\Result<br> instance now; previously, a resource was expected. |
|  | [pg\_flush](https://www.php.net/manual/en/function.pg-flush.php) | The connection parameter expects an PgSql\\Connection<br> instance now; previously, a resource was expected. |
|  | [pg\_free\_result](https://www.php.net/manual/en/function.pg-free-result.php) | The result parameter expects an PgSql\\Result<br> instance now; previously, a resource was expected. |
|  | [pg\_get\_notify](https://www.php.net/manual/en/function.pg-get-notify.php) | The connection parameter expects an PgSql\\Connection<br> instance now; previously, a resource was expected. |
|  | [pg\_get\_pid](https://www.php.net/manual/en/function.pg-get-pid.php) | The connection parameter expects an PgSql\\Connection<br> instance now; previously, a resource was expected. |
|  | [pg\_get\_result](https://www.php.net/manual/en/function.pg-get-result.php) | Returns an PgSql\\Result instance now;<br> previously, a resource was returned. |
|  | [pg\_get\_result](https://www.php.net/manual/en/function.pg-get-result.php) | The connection parameter expects an PgSql\\Connection<br> instance now; previously, a resource was expected. |
|  | [pg\_host](https://www.php.net/manual/en/function.pg-host.php) | The connection parameter expects an PgSql\\Connection<br> instance now; previously, a resource was expected. |
|  | [pg\_insert](https://www.php.net/manual/en/function.pg-insert.php) | Returns an PgSql\\Result instance now;<br> previously, a resource was returned. |
|  | [pg\_insert](https://www.php.net/manual/en/function.pg-insert.php) | The connection parameter expects an PgSql\\Connection<br> instance now; previously, a resource was expected. |
|  | [pg\_last\_error](https://www.php.net/manual/en/function.pg-last-error.php) | The connection parameter expects an PgSql\\Connection<br> instance now; previously, a resource was expected. |
|  | [pg\_last\_notice](https://www.php.net/manual/en/function.pg-last-notice.php) | The connection parameter expects an PgSql\\Connection<br> instance now; previously, a resource was expected. |
|  | [pg\_last\_oid](https://www.php.net/manual/en/function.pg-last-oid.php) | The result parameter expects an PgSql\\Result<br> instance now; previously, a resource was expected. |
|  | [pg\_lo\_close](https://www.php.net/manual/en/function.pg-lo-close.php) | The lob parameter expects an PgSql\\Lob<br> instance now; previously, a resource was expected. |
|  | [pg\_lo\_create](https://www.php.net/manual/en/function.pg-lo-create.php) | The connection parameter expects an PgSql\\Connection<br> instance now; previously, a resource was expected. |
|  | [pg\_lo\_export](https://www.php.net/manual/en/function.pg-lo-export.php) | The connection parameter expects an PgSql\\Connection<br> instance now; previously, a resource was expected. |
|  | [pg\_lo\_import](https://www.php.net/manual/en/function.pg-lo-import.php) | The connection parameter expects an PgSql\\Connection<br> instance now; previously, a resource was expected. |
|  | [pg\_lo\_open](https://www.php.net/manual/en/function.pg-lo-open.php) | Returns an PgSql\\Lob instance now;<br> previously, a resource was returned. |
|  | [pg\_lo\_open](https://www.php.net/manual/en/function.pg-lo-open.php) | The connection parameter expects an PgSql\\Connection<br> instance now; previously, a resource was expected. |
|  | [pg\_lo\_read](https://www.php.net/manual/en/function.pg-lo-read.php) | The lob parameter expects an PgSql\\Lob<br> instance now; previously, a resource was expected. |
|  | [pg\_lo\_read\_all](https://www.php.net/manual/en/function.pg-lo-read-all.php) | The lob parameter expects an PgSql\\Lob<br> instance now; previously, a resource was expected. |
|  | [pg\_lo\_seek](https://www.php.net/manual/en/function.pg-lo-seek.php) | The lob parameter expects an PgSql\\Lob<br> instance now; previously, a resource was expected. |
|  | [pg\_lo\_tell](https://www.php.net/manual/en/function.pg-lo-tell.php) | The lob parameter expects an PgSql\\Lob<br> instance now; previously, a resource was expected. |
|  | [pg\_lo\_truncate](https://www.php.net/manual/en/function.pg-lo-truncate.php) | The lob parameter expects an PgSql\\Lob<br> instance now; previously, a resource was expected. |
|  | [pg\_lo\_unlink](https://www.php.net/manual/en/function.pg-lo-unlink.php) | The connection parameter expects an PgSql\\Connection<br> instance now; previously, a resource was expected. |
|  | [pg\_lo\_write](https://www.php.net/manual/en/function.pg-lo-write.php) | The lob parameter expects an PgSql\\Lob<br> instance now; previously, a resource was expected. |
|  | [pg\_meta\_data](https://www.php.net/manual/en/function.pg-meta-data.php) | The connection parameter expects an PgSql\\Connection<br> instance now; previously, a resource was expected. |
|  | [pg\_num\_fields](https://www.php.net/manual/en/function.pg-num-fields.php) | The result parameter expects an PgSql\\Result<br> instance now; previously, a resource was expected. |
|  | [pg\_num\_rows](https://www.php.net/manual/en/function.pg-num-rows.php) | The result parameter expects an PgSql\\Result<br> instance now; previously, a resource was expected. |
|  | [pg\_options](https://www.php.net/manual/en/function.pg-options.php) | The connection parameter expects an PgSql\\Connection<br> instance now; previously, a resource was expected. |
|  | [pg\_parameter\_status](https://www.php.net/manual/en/function.pg-parameter-status.php) | The connection parameter expects an PgSql\\Connection<br> instance now; previously, a resource was expected. |
|  | [pg\_pconnect](https://www.php.net/manual/en/function.pg-pconnect.php) | Returns a PgSql\\Connection instance now;<br> previously, a resource was returned. |
|  | [pg\_ping](https://www.php.net/manual/en/function.pg-ping.php) | The connection parameter expects an PgSql\\Connection<br> instance now; previously, a resource was expected. |
|  | [pg\_port](https://www.php.net/manual/en/function.pg-port.php) | The connection parameter expects an PgSql\\Connection<br> instance now; previously, a resource was expected. |
|  | [pg\_prepare](https://www.php.net/manual/en/function.pg-prepare.php) | Returns an PgSql\\Result instance now;<br> previously, a resource was returned. |
|  | [pg\_prepare](https://www.php.net/manual/en/function.pg-prepare.php) | The connection parameter expects an PgSql\\Connection<br> instance now; previously, a resource was expected. |
|  | [pg\_put\_line](https://www.php.net/manual/en/function.pg-put-line.php) | The connection parameter expects an PgSql\\Connection<br> instance now; previously, a resource was expected. |
|  | [pg\_query](https://www.php.net/manual/en/function.pg-query.php) | Returns an PgSql\\Result instance now;<br> previously, a resource was returned. |
|  | [pg\_query](https://www.php.net/manual/en/function.pg-query.php) | The connection parameter expects an PgSql\\Connection<br> instance now; previously, a resource was expected. |
|  | [pg\_query\_params](https://www.php.net/manual/en/function.pg-query-params.php) | Returns an PgSql\\Result instance now;<br> previously, a resource was returned. |
|  | [pg\_query\_params](https://www.php.net/manual/en/function.pg-query-params.php) | The connection parameter expects an PgSql\\Connection<br> instance now; previously, a resource was expected. |
|  | [pg\_result\_error](https://www.php.net/manual/en/function.pg-result-error.php) | The result parameter expects an PgSql\\Result<br> instance now; previously, a resource was expected. |
|  | [pg\_result\_error\_field](https://www.php.net/manual/en/function.pg-result-error-field.php) | The result parameter expects an PgSql\\Result<br> instance now; previously, a resource was expected. |
|  | [pg\_result\_seek](https://www.php.net/manual/en/function.pg-result-seek.php) | The result parameter expects an PgSql\\Result<br> instance now; previously, a resource was expected. |
|  | [pg\_result\_status](https://www.php.net/manual/en/function.pg-result-status.php) | The result parameter expects an PgSql\\Result<br> instance now; previously, a resource was expected. |
|  | [pg\_select](https://www.php.net/manual/en/function.pg-select.php) | The connection parameter expects an PgSql\\Connection<br> instance now; previously, a resource was expected. |
|  | [pg\_send\_execute](https://www.php.net/manual/en/function.pg-send-execute.php) | The connection parameter expects an PgSql\\Connection<br> instance now; previously, a resource was expected. |
|  | [pg\_send\_prepare](https://www.php.net/manual/en/function.pg-send-prepare.php) | The connection parameter expects an PgSql\\Connection<br> instance now; previously, a resource was expected. |
|  | [pg\_send\_query](https://www.php.net/manual/en/function.pg-send-query.php) | The connection parameter expects an PgSql\\Connection<br> instance now; previously, a resource was expected. |
|  | [pg\_send\_query\_params](https://www.php.net/manual/en/function.pg-send-query-params.php) | The connection parameter expects an PgSql\\Connection<br> instance now; previously, a resource was expected. |
|  | [pg\_set\_client\_encoding](https://www.php.net/manual/en/function.pg-set-client-encoding.php) | The connection parameter expects an PgSql\\Connection<br> instance now; previously, a resource was expected. |
|  | [pg\_set\_error\_verbosity](https://www.php.net/manual/en/function.pg-set-error-verbosity.php) | The connection parameter expects an PgSql\\Connection<br> instance now; previously, a resource was expected. |
|  | [pg\_socket](https://www.php.net/manual/en/function.pg-socket.php) | The connection parameter expects an PgSql\\Connection<br> instance now; previously, a resource was expected. |
|  | [pg\_trace](https://www.php.net/manual/en/function.pg-trace.php) | The connection parameter expects an PgSql\\Connection<br> instance now; previously, a resource was expected. |
|  | [pg\_transaction\_status](https://www.php.net/manual/en/function.pg-transaction-status.php) | The connection parameter expects an PgSql\\Connection<br> instance now; previously, a resource was expected. |
|  | [pg\_tty](https://www.php.net/manual/en/function.pg-tty.php) | The connection parameter expects an PgSql\\Connection<br> instance now; previously, a resource was expected. |
|  | [pg\_untrace](https://www.php.net/manual/en/function.pg-untrace.php) | The connection parameter expects an PgSql\\Connection<br> instance now; previously, a resource was expected. |
|  | [pg\_update](https://www.php.net/manual/en/function.pg-update.php) | The connection parameter expects an PgSql\\Connection<br> instance now; previously, a resource was expected. |
|  | [pg\_version](https://www.php.net/manual/en/function.pg-version.php) | The connection parameter expects an PgSql\\Connection<br> instance now; previously, a resource was expected. |
|  | [prev](https://www.php.net/manual/en/function.prev.php) | Calling this function on objects is deprecated.<br> Either convert the object to an array using get\_mangled\_object\_vars first, or use the methods<br> provided by a class that implements Iterator, such as ArrayIterator, instead. |
|  | [reset](https://www.php.net/manual/en/function.reset.php) | Calling this function on objects is deprecated.<br> Either convert the object to an array using get\_mangled\_object\_vars first, or use the methods<br> provided by a class that implements Iterator, such as ArrayIterator, instead. |
|  | [snmp3\_get](https://www.php.net/manual/en/function.snmp3-get.php) | The auth\_protocol now accepts "SHA256"<br> and "SHA512" when supported by libnetsnmp. |
|  | [snmp3\_getnext](https://www.php.net/manual/en/function.snmp3-getnext.php) | The auth\_protocol now accepts "SHA256"<br> and "SHA512" when supported by libnetsnmp. |
|  | [snmp3\_real\_walk](https://www.php.net/manual/en/function.snmp3-real-walk.php) | The auth\_protocol now accepts "SHA256"<br> and "SHA512" when supported by libnetsnmp. |
|  | [snmp3\_walk](https://www.php.net/manual/en/function.snmp3-walk.php) | The auth\_protocol now accepts "SHA256"<br> and "SHA512" when supported by libnetsnmp. |
|  | [stream\_select](https://www.php.net/manual/en/function.stream-select.php) | microseconds is now nullable. |
|  | [strptime](https://www.php.net/manual/en/function.strptime.php) | This function has been deprecated.<br> Use date\_parse\_from\_format instead (for locale-independent parsing),<br> or IntlDateFormatter::parse (for locale-dependent parsing) |
|  | [IntlDateFormatter::create](https://www.php.net/manual/en/intldateformatter.create.php) | Parameters dateType and<br> timeType are now optional. |
|  | [MultipleIterator::current](https://www.php.net/manual/en/multipleiterator.current.php) | A RuntimeException is now thrown if<br> MultipleIterator::current is called on an<br> invalid iterator. Previously, false was returned. |
|  | [MultipleIterator::key](https://www.php.net/manual/en/multipleiterator.key.php) | A RuntimeException is now thrown if<br> MultipleIterator::key is called on an<br> invalid iterator. Previously, false was returned. |
|  | [mysqli\_driver::$report\_mode](https://www.php.net/manual/en/mysqli-driver.report-mode.php) | The default value is now MYSQLI\_REPORT\_ERROR \| MYSQLI\_REPORT\_STRICT.<br> Previously, it was MYSQLI\_REPORT\_OFF. |
|  | [mysqli\_result::fetch\_all](https://www.php.net/manual/en/mysqli-result.fetch-all.php) | Now also available when linking against libmysqlclient. |
|  | [mysqli\_stmt::execute](https://www.php.net/manual/en/mysqli-stmt.execute.php) | The optional params parameter has been added. |
|  | [mysqli\_stmt::next\_result](https://www.php.net/manual/en/mysqli-stmt.next-result.php) | Now also available when linking against libmysqlclient. |
|  | [mysqli::\_\_construct](https://www.php.net/manual/en/mysqli.construct.php) | mysqli::connect now returns true instead of null on success. |
|  | [mysqli::$client\_info](https://www.php.net/manual/en/mysqli.get-client-info.php) | Calling mysqli\_get\_client\_info with the<br> mysql argument has been deprecated.<br> This function never required a parameter, but incorrectly allowed it as<br> an optional parameter. |
|  | [mysqli::$client\_info](https://www.php.net/manual/en/mysqli.get-client-info.php) | The object-oriented style mysqli::get\_client\_info<br> has been deprecated. |
|  | [mysqli::init](https://www.php.net/manual/en/mysqli.init.php) | The object-oriented style mysqli::init method<br> has been deprecated.<br> Replace calls to parent::init with<br> parent::\_\_construct. |
|  | [Phar::buildFromDirectory](https://www.php.net/manual/en/phar.buildfromdirectory.php) | Phar::buildFromDirectory no longer returns false. |
|  | [Phar::buildFromIterator](https://www.php.net/manual/en/phar.buildfromiterator.php) | Phar::buildFromIterator no longer returns false. |
|  | [PharData::buildFromDirectory](https://www.php.net/manual/en/phardata.buildfromdirectory.php) | PharData::buildFromDirectory no longer returns false. |
|  | [PharData::buildFromIterator](https://www.php.net/manual/en/phardata.buildfromiterator.php) | PharData::buildFromIterator no longer returns false. |
|  | [ReflectionFunctionAbstract::isStatic](https://www.php.net/manual/en/reflectiofunctionabstract.isstatic.php) | This method has been pulled up. Previously, it was only defined in<br> ReflectionMethod. |
|  | [ReflectionClassConstant::getName](https://www.php.net/manual/en/reflectionclassconstant.getname.php) | Throws an Error in case the name property has not been initialized.<br> Previously, the method returned false on failure. |
|  | [ReflectionExtension::\_\_clone](https://www.php.net/manual/en/reflectionextension.clone.php) | This method is no longer final. |
|  | [ReflectionFunctionAbstract::\_\_clone](https://www.php.net/manual/en/reflectionfunctionabstract.clone.php) | This method is no longer final. |
|  | [ReflectionParameter::\_\_clone](https://www.php.net/manual/en/reflectionparameter.clone.php) | This method is no longer final. |
|  | [ReflectionProperty::\_\_clone](https://www.php.net/manual/en/reflectionproperty.clone.php) | This method is no longer final. |
|  | [ReflectionProperty::getValue](https://www.php.net/manual/en/reflectionproperty.getvalue.php) | Private and protected properties can be accessed by<br> ReflectionProperty::getValue right away.<br> Previously, they needed to be made accessible by calling<br> ReflectionProperty::setAccessible; otherwise<br> a ReflectionException was thrown. |
|  | [ReflectionProperty::setValue](https://www.php.net/manual/en/reflectionproperty.setvalue.php) | Private and protected properties can be accessed by<br> ReflectionProperty::setValue right away.<br> Previously, they needed to be made accessible by calling<br> ReflectionProperty::setAccessible; otherwise<br> a ReflectionException was thrown. |
|  | [ReflectionZendExtension::\_\_clone](https://www.php.net/manual/en/reflectionzendextension.clone.php) | This method is no longer final. |
|  | [SimpleXMLElement::current](https://www.php.net/manual/en/simplexmlelement.current.php) | An Error is now thrown if<br> SimpleXMLElement::current is called on an<br> invalid iterator. Previously, null was returned. |
|  | [SimpleXMLElement::key](https://www.php.net/manual/en/simplexmlelement.key.php) | An Error is now thrown if<br> SimpleXMLElement::key is called on an<br> invalid iterator. Previously, false was returned. |
|  | [SplFileObject::fputcsv](https://www.php.net/manual/en/splfileobject.fputcsv.php) | The optional eol parameter has been added. |
|  | [SplObjectStorage::current](https://www.php.net/manual/en/splobjectstorage.current.php) | SplObjectStorage::current now throws an Error exception<br> if the current position is invalid. Previously, false was returned instead. |
|  | [SQLite3Result::finalize](https://www.php.net/manual/en/sqlite3result.finalize.php) | This method now throws an Error exception if the<br> object is not correct initialized. Previously, it returned false. |
|  | [SQLite3Stmt::close](https://www.php.net/manual/en/sqlite3stmt.close.php) | This method now throws an Error exception if the<br> object is not correct initialized. Previously, it returned<br> false. |
| 8.0.21 | [DateTime::createFromFormat](https://www.php.net/manual/en/datetime.createfromformat.php) | Now throws ValueError when NULL-bytes<br> are passed into datetime, which previously was silently<br> ignored. |
|  | [DateTimeImmutable::createFromFormat](https://www.php.net/manual/en/datetimeimmutable.createfromformat.php) | Now throws ValueError when NULL-bytes<br> are passed into datetime, which previously was silently<br> ignored. |
|  | [date\_parse\_from\_format](https://www.php.net/manual/en/function.date-parse-from-format.php) | Now throws ValueError when NULL-bytes<br> are passed into datetime, which previously was silently<br> ignored. |
| 8.0.5 | [imageinterlace](https://www.php.net/manual/en/function.imageinterlace.php) | imageinterlace returns a bool now;<br> previously it returned an int<br> (non-zero for interlaced images, zero otherwise). |
| 8.0.3 | [DOMDocument::getElementsByTagNameNS](https://www.php.net/manual/en/domdocument.getelementsbytagnamens.php) | namespace is nullable now. |
|  | [DOMElement::getElementsByTagNameNS](https://www.php.net/manual/en/domelement.getelementsbytagnamens.php) | namespace is nullable now. |
|  | [DOMImplementation::createDocument](https://www.php.net/manual/en/domimplementation.createdocument.php) | namespace is now nullable. |
|  | [finfo::\_\_construct](https://www.php.net/manual/en/finfo.construct.php) | magic\_database is nullable now. |
|  | [bind\_textdomain\_codeset](https://www.php.net/manual/en/function.bind-textdomain-codeset.php) | codeset is nullable now.<br> Previously, it was not possible to retrieve the currently set encoding. |
|  | [bindtextdomain](https://www.php.net/manual/en/function.bindtextdomain.php) | directory is nullable now.<br> Previously, it was not possible to retrieve the currently set directory. |
|  | [finfo\_open](https://www.php.net/manual/en/function.finfo-open.php) | magic\_database is nullable now. |
|  | [imagegd](https://www.php.net/manual/en/function.imagegd.php) | file is now nullable. |
|  | [imagegd2](https://www.php.net/manual/en/function.imagegd2.php) | file is now nullable. |
|  | [SoapClient::\_\_setLocation](https://www.php.net/manual/en/soapclient.setlocation.php) | location is nullable now. |
|  | [SoapVar::\_\_construct](https://www.php.net/manual/en/soapvar.construct.php) | typeName, typeNamespace, nodeName,and<br> nodeNamespace are nullable now. |
| 8.0.0 | [CURLFile::\_\_construct](https://www.php.net/manual/en/curlfile.construct.php) | mime\_type and posted\_filename<br> are nullable now; previously their default was 0. |
|  | [DateInterval::\_\_construct](https://www.php.net/manual/en/dateinterval.construct.php) | W can be combined with D. |
|  | [DateTime::createFromImmutable](https://www.php.net/manual/en/datetime.createfromimmutable.php) | The method returns an instance of the currently invoked class now. Previously, it created a new instance<br> of DateTime. |
|  | [DateTimeInterface::format](https://www.php.net/manual/en/datetime.format.php) | The format character p has been added. |
|  | [DateTimeInterface::getTimestamp](https://www.php.net/manual/en/datetime.gettimestamp.php) | These functions no longer return false on failure. |
|  | [DateTimeImmutable::createFromMutable](https://www.php.net/manual/en/datetimeimmutable.createfrommutable.php) | The method returns an instance of the currently invoked class now. Previously, it created a new instance<br> of DateTimeImmutable. |
|  | [DateTimeZone::listIdentifiers](https://www.php.net/manual/en/datetimezone.listidentifiers.php) | Prior to this version, false was returned on failure. |
|  | [Directory::close](https://www.php.net/manual/en/directory.close.php) | No parameter is accepted. Previously, a directory handle could be passed as argument. |
|  | [Directory::read](https://www.php.net/manual/en/directory.read.php) | No parameter is accepted. Previously, a directory handle could be passed as argument. |
|  | [Directory::rewind](https://www.php.net/manual/en/directory.rewind.php) | No parameter is accepted. Previously, a directory handle could be passed as argument. |
|  | [DirectoryIterator::\_\_construct](https://www.php.net/manual/en/directoryiterator.construct.php) | Now throws a ValueError if<br> directory is an empty string;<br> previously it threw a RuntimeException. |
|  | [DOMDocument::load](https://www.php.net/manual/en/domdocument.load.php) | Calling this function statically will<br> now throw an Error.<br> Previously, an E\_DEPRECATED was raised. |
|  | [DOMDocument::loadHTML](https://www.php.net/manual/en/domdocument.loadhtml.php) | Calling this function statically will<br> now throw an Error.<br> Previously, an E\_DEPRECATED was raised. |
|  | [DOMDocument::loadHTMLFile](https://www.php.net/manual/en/domdocument.loadhtmlfile.php) | Calling this function statically will<br> now throw an Error.<br> Previously, an E\_DEPRECATED was raised. |
|  | [DOMDocument::loadXML](https://www.php.net/manual/en/domdocument.loadxml.php) | Calling this function statically will<br> now throw an Error.<br> Previously, an E\_DEPRECATED was raised. |
|  | [DOMImplementation::createDocument](https://www.php.net/manual/en/domimplementation.createdocument.php) | doctype is now nullable. |
|  | [DOMImplementation::createDocument](https://www.php.net/manual/en/domimplementation.createdocument.php) | Calling this function statically will<br> now throw an Error.<br> Previously, an E\_DEPRECATED was raised. |
|  | [DOMImplementation::createDocumentType](https://www.php.net/manual/en/domimplementation.createdocumenttype.php) | Calling this function statically will<br> now throw an Error.<br> Previously, an E\_DEPRECATED was raised. |
|  | [DOMImplementation::hasFeature](https://www.php.net/manual/en/domimplementation.hasfeature.php) | Calling this function statically will<br> now throw an Error.<br> Previously, an E\_DEPRECATED was raised. |
|  | [FFI::cdef](https://www.php.net/manual/en/ffi.cdef.php) | lib is nullable now. |
|  | [FFI::string](https://www.php.net/manual/en/ffi.string.php) | size is nullable now; previously, its default was<br> 0. |
|  | [FilesystemIterator::\_\_construct](https://www.php.net/manual/en/filesystemiterator.construct.php) | Now throws a ValueError if<br> directory is an empty string;<br> previously it threw a RuntimeException. |
|  | [abs](https://www.php.net/manual/en/function.abs.php) | num no longer accepts internal objects which support<br> numeric conversion. |
|  | [apache\_note](https://www.php.net/manual/en/function.apache-note.php) | note\_value is nullable now. |
|  | [array\_chunk](https://www.php.net/manual/en/function.array-chunk.php) | If length is less than 1,<br> a ValueError will be thrown now;<br> previously, an error of level E\_WARNING<br> has been raised instead, and the function returned null. |
|  | [array\_column](https://www.php.net/manual/en/function.array-column.php) | Objects in columns indicated by index\_key parameter<br> will no longer be cast to string and will now throw a TypeError instead. |
|  | [array\_combine](https://www.php.net/manual/en/function.array-combine.php) | array\_combine will now throw a<br> ValueError if the number of elements<br> for each array is not equal;<br> previously this function returned false instead. |
|  | [array\_diff](https://www.php.net/manual/en/function.array-diff.php) | This function can now be called with only one parameter.<br> Formerly, at least two parameters have been required. |
|  | [array\_diff\_assoc](https://www.php.net/manual/en/function.array-diff-assoc.php) | This function can now be called with only one parameter.<br> Formerly, at least two parameters have been required. |
|  | [array\_diff\_key](https://www.php.net/manual/en/function.array-diff-key.php) | This function can now be called with only one parameter.<br> Formerly, at least two parameters have been required. |
|  | [array\_fill](https://www.php.net/manual/en/function.array-fill.php) | array\_fill now throws a ValueError<br> if count is out of range; previously E\_WARNING<br> was raised, and the function returned false. |
|  | [array\_filter](https://www.php.net/manual/en/function.array-filter.php) | callback is nullable now. |
|  | [array\_filter](https://www.php.net/manual/en/function.array-filter.php) | If callback expects a parameter to be passed<br> by reference, this function will now emit an E\_WARNING. |
|  | [array\_intersect](https://www.php.net/manual/en/function.array-intersect.php) | This function can now be called with only one parameter.<br> Formerly, at least two parameters have been required. |
|  | [array\_intersect\_assoc](https://www.php.net/manual/en/function.array-intersect-assoc.php) | This function can now be called with only one parameter.<br> Formerly, at least two parameters have been required. |
|  | [array\_intersect\_key](https://www.php.net/manual/en/function.array-intersect-key.php) | This function can now be called with only one parameter.<br> Formerly, at least two parameters have been required. |
|  | [array\_key\_exists](https://www.php.net/manual/en/function.array-key-exists.php) | The key parameter now accepts<br> bool, float, int,<br> null, resource, and<br> string as arguments. |
|  | [array\_key\_exists](https://www.php.net/manual/en/function.array-key-exists.php) | Passing an object to the array parameter is no longer supported. |
|  | [array\_map](https://www.php.net/manual/en/function.array-map.php) | If callback expects a parameter to be passed<br> by reference, this function will now emit an E\_WARNING. |
|  | [array\_rand](https://www.php.net/manual/en/function.array-rand.php) | array\_rand now throws a ValueError<br> if num is out of range; previously an<br> E\_WARNING was raised, and the function returned null. |
|  | [array\_rand](https://www.php.net/manual/en/function.array-rand.php) | array\_rand now throws a ValueError<br> if array is empty; previously an<br> E\_WARNING was raised, and the function returned null. |
|  | [array\_reduce](https://www.php.net/manual/en/function.array-reduce.php) | If callback expects a parameter to be passed<br> by reference, this function will now emit an E\_WARNING. |
|  | [array\_splice](https://www.php.net/manual/en/function.array-splice.php) | length is nullable now. |
|  | [array\_walk](https://www.php.net/manual/en/function.array-walk.php) | If callback expects the second or third parameter to be passed<br> by reference, this function will now emit an E\_WARNING. |
|  | [assert](https://www.php.net/manual/en/function.assert.php) | assert will no longer evaluate string arguments, instead they will be<br> treated like any other argument. assert($a == $b) should be used instead of<br> assert('$a == $b'). The assert.quiet\_eval php.ini directive and<br> the ASSERT\_QUIET\_EVAL constant have also been removed, as they would no longer<br> have any effect. |
|  | [assert](https://www.php.net/manual/en/function.assert.php) | If description is an instance of<br> Throwable, the object is thrown if the assertion<br> fails, regardless of the value of<br> assert.exception. |
|  | [assert](https://www.php.net/manual/en/function.assert.php) | If description is an instance of<br> Throwable, no user callback is called even<br> if it set. |
|  | [assert](https://www.php.net/manual/en/function.assert.php) | Declaring a function called assert() inside a namespace is<br> no longer allowed, and issues E\_COMPILE\_ERROR. |
|  | [assert\_options](https://www.php.net/manual/en/function.assert-options.php) | If option is not a valid option,<br> a ValueError is now thrown.<br> Previously false was returned. |
|  | [bcadd](https://www.php.net/manual/en/function.bcadd.php) | scale is now nullable. |
|  | [bccomp](https://www.php.net/manual/en/function.bccomp.php) | scale is now nullable. |
|  | [bcdiv](https://www.php.net/manual/en/function.bcdiv.php) | scale is now nullable. |
|  | [bcdiv](https://www.php.net/manual/en/function.bcdiv.php) | Dividing by 0 now throws a<br> DivisionByZeroError exception<br> instead of returning null. |
|  | [bcmod](https://www.php.net/manual/en/function.bcmod.php) | scale is now nullable. |
|  | [bcmod](https://www.php.net/manual/en/function.bcmod.php) | Dividing by 0 now throws a DivisionByZeroError exception instead of returning null. |
|  | [bcmul](https://www.php.net/manual/en/function.bcmul.php) | scale is now nullable. |
|  | [bcpow](https://www.php.net/manual/en/function.bcpow.php) | When exponent has a fractional part, it now throws a ValueError<br> instead of truncating. |
|  | [bcpowmod](https://www.php.net/manual/en/function.bcpowmod.php) | scale is now nullable. |
|  | [bcpowmod](https://www.php.net/manual/en/function.bcpowmod.php) | Now throws a ValueError instead of returning false if exponent is a negative value. |
|  | [bcpowmod](https://www.php.net/manual/en/function.bcpowmod.php) | Dividing by 0 now throws a DivisionByZeroError exception instead of returning false. |
|  | [bcscale](https://www.php.net/manual/en/function.bcscale.php) | scale is now nullable. |
|  | [bcsqrt](https://www.php.net/manual/en/function.bcsqrt.php) | If num is not a well-formed BCMath numeric string,<br> or less than 0, a ValueError is thrown.<br> Previously, E\_WARNING was raised instead. |
|  | [bcsqrt](https://www.php.net/manual/en/function.bcsqrt.php) | scale now needs to be between 0<br> and 2147483647; previously, negative scales have been<br> silently treated as 0. |
|  | [bcsqrt](https://www.php.net/manual/en/function.bcsqrt.php) | scale is now nullable. |
|  | [bcsub](https://www.php.net/manual/en/function.bcsub.php) | scale is now nullable. |
|  | [bzdecompress](https://www.php.net/manual/en/function.bzdecompress.php) | The type of use\_less\_memory has been changed from<br> int to bool. Previously, the default value was<br> 0. |
|  | [bzwrite](https://www.php.net/manual/en/function.bzwrite.php) | length is nullable now. |
|  | [call\_user\_func\_array](https://www.php.net/manual/en/function.call-user-func-array.php) | args keys will now be interpreted as parameter names, instead of being silently ignored. |
|  | [ceil](https://www.php.net/manual/en/function.ceil.php) | num no longer accepts internal objects which support<br> numeric conversion. |
|  | [com\_event\_sink](https://www.php.net/manual/en/function.com-event-sink.php) | sink\_interface is nullable now. |
|  | [com\_get\_active\_object](https://www.php.net/manual/en/function.com-get-active-object.php) | codepage is nullable now. |
|  | [compact](https://www.php.net/manual/en/function.compact.php) | If a given string references an unset variable, an E\_WARNING level error is now issued. |
|  | [constant](https://www.php.net/manual/en/function.constant.php) | If the constant is not defined, constant now throws an<br> Error exception; previously an E\_WARNING<br> was generated, and null was returned. |
|  | [convert\_cyr\_string](https://www.php.net/manual/en/function.convert-cyr-string.php) | Removed this function. |
|  | [convert\_uuencode](https://www.php.net/manual/en/function.convert-uuencode.php) | Prior to this version, trying to convert an empty string returned false<br> for no particular reason. |
|  | [count](https://www.php.net/manual/en/function.count.php) | count will now throw TypeError on <br> invalid countable types passed to the value parameter. |
|  | [count\_chars](https://www.php.net/manual/en/function.count-chars.php) | Prior to this version, the function returned false on failure. |
|  | [crypt](https://www.php.net/manual/en/function.crypt.php) | The salt is no longer optional. |
|  | [curl\_close](https://www.php.net/manual/en/function.curl-close.php) | handle expects a CurlHandle<br> instance now; previously, a resource was expected. |
|  | [curl\_copy\_handle](https://www.php.net/manual/en/function.curl-copy-handle.php) | handle expects a CurlHandle<br> instance now; previously, a resource was expected. |
|  | [curl\_copy\_handle](https://www.php.net/manual/en/function.curl-copy-handle.php) | On success, this function returns a CurlHandle instance now;<br> previously, a resource was returned. |
|  | [curl\_errno](https://www.php.net/manual/en/function.curl-errno.php) | handle expects a CurlHandle<br> instance now; previously, a resource was expected. |
|  | [curl\_error](https://www.php.net/manual/en/function.curl-error.php) | handle expects a CurlHandle<br> instance now; previously, a resource was expected. |
|  | [curl\_escape](https://www.php.net/manual/en/function.curl-escape.php) | handle expects a CurlHandle<br> instance now; previously, a resource was expected. |
|  | [curl\_exec](https://www.php.net/manual/en/function.curl-exec.php) | handle expects a CurlHandle<br> instance now; previously, a resource was expected. |
|  | [curl\_getinfo](https://www.php.net/manual/en/function.curl-getinfo.php) | handle expects a CurlHandle<br> instance now; previously, a resource was expected. |
|  | [curl\_getinfo](https://www.php.net/manual/en/function.curl-getinfo.php) | option is nullable now;<br> previously, the default was 0. |
|  | [curl\_init](https://www.php.net/manual/en/function.curl-init.php) | On success, this function returns a CurlHandle instance now;<br> previously, a resource was returned. |
|  | [curl\_init](https://www.php.net/manual/en/function.curl-init.php) | url is nullable now. |
|  | [curl\_multi\_add\_handle](https://www.php.net/manual/en/function.curl-multi-add-handle.php) | multi\_handle expects a CurlMultiHandle<br> instance now; previously, a resource was expected. |
|  | [curl\_multi\_add\_handle](https://www.php.net/manual/en/function.curl-multi-add-handle.php) | handle expects a CurlHandle<br> instance now; previously, a resource was expected. |
|  | [curl\_multi\_close](https://www.php.net/manual/en/function.curl-multi-close.php) | multi\_handle expects a CurlMultiHandle<br> instance now; previously, a resource was expected. |
|  | [curl\_multi\_errno](https://www.php.net/manual/en/function.curl-multi-errno.php) | The function no longer returns false on failure. |
|  | [curl\_multi\_errno](https://www.php.net/manual/en/function.curl-multi-errno.php) | multi\_handle expects a CurlMultiHandle<br> instance now; previously, a resource was expected. |
|  | [curl\_multi\_exec](https://www.php.net/manual/en/function.curl-multi-exec.php) | multi\_handle expects a CurlMultiHandle<br> instance now; previously, a resource was expected. |
|  | [curl\_multi\_getcontent](https://www.php.net/manual/en/function.curl-multi-getcontent.php) | handle expects a CurlHandle<br> instance now; previously, a resource was expected. |
|  | [curl\_multi\_info\_read](https://www.php.net/manual/en/function.curl-multi-info-read.php) | multi\_handle expects a CurlMultiHandle<br> instance now; previously, a resource was expected. |
|  | [curl\_multi\_init](https://www.php.net/manual/en/function.curl-multi-init.php) | On success, this function returns a CurlMultiHandle instance now;<br> previously, a resource was returned. |
|  | [curl\_multi\_remove\_handle](https://www.php.net/manual/en/function.curl-multi-remove-handle.php) | multi\_handle expects a CurlMultiHandle<br> instance now; previously, a resource was expected. |
|  | [curl\_multi\_remove\_handle](https://www.php.net/manual/en/function.curl-multi-remove-handle.php) | handle expects a CurlHandle<br> instance now; previously, a resource was expected. |
|  | [curl\_multi\_select](https://www.php.net/manual/en/function.curl-multi-select.php) | multi\_handle expects a CurlMultiHandle<br> instance now; previously, a resource was expected. |
|  | [curl\_multi\_setopt](https://www.php.net/manual/en/function.curl-multi-setopt.php) | multi\_handle expects a CurlMultiHandle<br> instance now; previously, a resource was expected. |
|  | [curl\_pause](https://www.php.net/manual/en/function.curl-pause.php) | handle expects a CurlHandle<br> instance now; previously, a resource was expected. |
|  | [curl\_reset](https://www.php.net/manual/en/function.curl-reset.php) | handle expects a CurlHandle<br> instance now; previously, a resource was expected. |
|  | [curl\_setopt](https://www.php.net/manual/en/function.curl-setopt.php) | handle expects a CurlHandle<br> instance now; previously, a resource was expected. |
|  | [curl\_setopt\_array](https://www.php.net/manual/en/function.curl-setopt-array.php) | handle expects a CurlHandle<br> instance now; previously, a resource was expected. |
|  | [curl\_share\_close](https://www.php.net/manual/en/function.curl-share-close.php) | share\_handle expects a CurlShareHandle<br> instance now; previously, a resource was expected. |
|  | [curl\_share\_errno](https://www.php.net/manual/en/function.curl-share-errno.php) | The function no longer returns false on failure. |
|  | [curl\_share\_errno](https://www.php.net/manual/en/function.curl-share-errno.php) | share\_handle expects a CurlShareHandle<br> instance now; previously, a resource was expected. |
|  | [curl\_share\_init](https://www.php.net/manual/en/function.curl-share-init.php) | This function returns a CurlShareHandle instance now;<br> previously, a resource was returned. |
|  | [curl\_share\_setopt](https://www.php.net/manual/en/function.curl-share-setopt.php) | share\_handle expects a CurlShareHandle<br> instance now; previously, a resource was expected. |
|  | [curl\_unescape](https://www.php.net/manual/en/function.curl-unescape.php) | handle expects a CurlHandle<br> instance now; previously, a resource was expected. |
|  | [curl\_version](https://www.php.net/manual/en/function.curl-version.php) | The optional age parameter has been removed. |
|  | [date](https://www.php.net/manual/en/function.date.php) | timestamp is nullable now. |
|  | [date\_sunrise](https://www.php.net/manual/en/function.date-sunrise.php) | latitude, longitude,<br> zenith and utcOffset are nullable now. |
|  | [date\_sunset](https://www.php.net/manual/en/function.date-sunset.php) | latitude, longitude,<br> zenith and utcOffset are nullable now. |
|  | [define](https://www.php.net/manual/en/function.define.php) | Passing true to case\_insensitive now emits an E\_WARNING. Passing false is still allowed. |
|  | [deflate\_add](https://www.php.net/manual/en/function.deflate-add.php) | context expects a DeflateContext<br> instance now; previously, a resource was expected. |
|  | [deflate\_init](https://www.php.net/manual/en/function.deflate-init.php) | On success, this function returns a DeflateContext instance now;<br> previously, a resource was returned. |
|  | [dir](https://www.php.net/manual/en/function.dir.php) | context is now nullable. |
|  | [dom\_import\_simplexml](https://www.php.net/manual/en/function.dom-import-simplexml.php) | This function no longer returns null on failure. |
|  | [easter\_date](https://www.php.net/manual/en/function.easter-date.php) | year is nullable now. |
|  | [easter\_date](https://www.php.net/manual/en/function.easter-date.php) | A ValueError is now thrown when<br> year is outside the allowed range.<br> Previously, an E\_WARNING was raised<br> and the function returned false. |
|  | [easter\_days](https://www.php.net/manual/en/function.easter-days.php) | year is nullable now. |
|  | [enchant\_broker\_describe](https://www.php.net/manual/en/function.enchant-broker-describe.php) | broker expects an EnchantBroker instance now;<br> previoulsy, a resource was expected. |
|  | [enchant\_broker\_describe](https://www.php.net/manual/en/function.enchant-broker-describe.php) | Prior to this version, the function returned false on failure. |
|  | [enchant\_broker\_dict\_exists](https://www.php.net/manual/en/function.enchant-broker-dict-exists.php) | broker expects an EnchantBroker instance now;<br> previoulsy, a resource was expected. |
|  | [enchant\_broker\_free](https://www.php.net/manual/en/function.enchant-broker-free.php) | This function has been deprecated in favor of unsetting the object. |
|  | [enchant\_broker\_free](https://www.php.net/manual/en/function.enchant-broker-free.php) | broker expects an EnchantBroker instance now;<br> previoulsy, a resource was expected. |
|  | [enchant\_broker\_free\_dict](https://www.php.net/manual/en/function.enchant-broker-free-dict.php) | This function has been deprecated in favor of unsetting the object. |
|  | [enchant\_broker\_free\_dict](https://www.php.net/manual/en/function.enchant-broker-free-dict.php) | dictionary expects a EnchantDictionary now;<br> previoulsy, a resource was expected. |
|  | [enchant\_broker\_get\_dict\_path](https://www.php.net/manual/en/function.enchant-broker-get-dict-path.php) | This function has been deprecated. |
|  | [enchant\_broker\_get\_dict\_path](https://www.php.net/manual/en/function.enchant-broker-get-dict-path.php) | broker expects an EnchantBroker instance now;<br> previoulsy, a resource was expected. |
|  | [enchant\_broker\_get\_error](https://www.php.net/manual/en/function.enchant-broker-get-error.php) | broker expects an EnchantBroker instance now;<br> previoulsy, a resource was expected. |
|  | [enchant\_broker\_init](https://www.php.net/manual/en/function.enchant-broker-init.php) | On success, this function returns an EnchantBroker instance now;<br> previously, a resource was returned. |
|  | [enchant\_broker\_list\_dicts](https://www.php.net/manual/en/function.enchant-broker-list-dicts.php) | broker expects an EnchantBroker instance now;<br> previoulsy, a resource was expected. |
|  | [enchant\_broker\_list\_dicts](https://www.php.net/manual/en/function.enchant-broker-list-dicts.php) | Prior to this version, the function returned false on failure. |
|  | [enchant\_broker\_request\_dict](https://www.php.net/manual/en/function.enchant-broker-request-dict.php) | broker expects an EnchantBroker instance now;<br> previoulsy, a resource was expected. |
|  | [enchant\_broker\_request\_dict](https://www.php.net/manual/en/function.enchant-broker-request-dict.php) | On success, this function returns an EnchantDictionary instance now;<br> previously, a resource was returned. |
|  | [enchant\_broker\_request\_pwl\_dict](https://www.php.net/manual/en/function.enchant-broker-request-pwl-dict.php) | broker expects an EnchantBroker instance now;<br> previoulsy, a resource was expected. |
|  | [enchant\_broker\_request\_pwl\_dict](https://www.php.net/manual/en/function.enchant-broker-request-pwl-dict.php) | On success, this function returns an EnchantDictionary instance now;<br> previoulsy, a resource was retured. |
|  | [enchant\_broker\_set\_dict\_path](https://www.php.net/manual/en/function.enchant-broker-set-dict-path.php) | This function has been deprecated. |
|  | [enchant\_broker\_set\_dict\_path](https://www.php.net/manual/en/function.enchant-broker-set-dict-path.php) | broker expects an EnchantBroker instance now;<br> previoulsy, a resource was expected. |
|  | [enchant\_broker\_set\_ordering](https://www.php.net/manual/en/function.enchant-broker-set-ordering.php) | broker expects an EnchantBroker instance now;<br> previoulsy, a resource was expected. |
|  | [enchant\_dict\_add](https://www.php.net/manual/en/function.enchant-dict-add.php) | dictionary expects an EnchantDictionary instance now;<br> previoulsy, a resource was expected. |
|  | [enchant\_dict\_add\_to\_session](https://www.php.net/manual/en/function.enchant-dict-add-to-session.php) | dictionary expects an EnchantDictionary instance now;<br> previoulsy, a resource was expected. |
|  | [enchant\_dict\_check](https://www.php.net/manual/en/function.enchant-dict-check.php) | dictionary expects an EnchantDictionary instance now;<br> previoulsy, a resource was expected. |
|  | [enchant\_dict\_describe](https://www.php.net/manual/en/function.enchant-dict-describe.php) | dictionary expects an EnchantDictionary instance now;<br> previoulsy, a resource was expected. |
|  | [enchant\_dict\_describe](https://www.php.net/manual/en/function.enchant-dict-describe.php) | Prior to this version, the function returned false on failure. |
|  | [enchant\_dict\_get\_error](https://www.php.net/manual/en/function.enchant-dict-get-error.php) | dictionary expects an EnchantDictionary instance now;<br> previoulsy, a resource was expected. |
|  | [enchant\_dict\_is\_added](https://www.php.net/manual/en/function.enchant-dict-is-added.php) | dictionary expects an EnchantDictionary instance now;<br> previoulsy, a resource was expected. |
|  | [enchant\_dict\_quick\_check](https://www.php.net/manual/en/function.enchant-dict-quick-check.php) | dictionary expects an EnchantDictionary instance now;<br> previoulsy, a resource was expected. |
|  | [enchant\_dict\_store\_replacement](https://www.php.net/manual/en/function.enchant-dict-store-replacement.php) | dictionary expects an EnchantDictionary instance now;<br> previoulsy, a resource was expected. |
|  | [enchant\_dict\_suggest](https://www.php.net/manual/en/function.enchant-dict-suggest.php) | dictionary expects an EnchantDictionary instance now;<br> previoulsy, a resource was expected. |
|  | [error\_log](https://www.php.net/manual/en/function.error-log.php) | destination and<br> additional\_headers are now nullable. |
|  | [error\_reporting](https://www.php.net/manual/en/function.error-reporting.php) | error\_level is nullable now. |
|  | [exec](https://www.php.net/manual/en/function.exec.php) | If command is empty or contains null bytes,<br> exec now throws a ValueError.<br> Previously it emitted an E\_WARNING and returned false. |
|  | [exif\_read\_data](https://www.php.net/manual/en/function.exif-read-data.php) | required\_sections is nullable now. |
|  | [explode](https://www.php.net/manual/en/function.explode.php) | explode will now throw ValueError<br> when separator parameter is given an empty string<br> ("").<br> Previously, explode returned false instead. |
|  | [ezmlm\_hash](https://www.php.net/manual/en/function.ezmlm-hash.php) | Removed this function. |
|  | [fgetcsv](https://www.php.net/manual/en/function.fgetcsv.php) | length is now nullable. |
|  | [file\_get\_contents](https://www.php.net/manual/en/function.file-get-contents.php) | length is nullable now. |
|  | [finfo\_buffer](https://www.php.net/manual/en/function.finfo-buffer.php) | context is nullable now. |
|  | [finfo\_file](https://www.php.net/manual/en/function.finfo-file.php) | context is nullable now. |
|  | [floatval](https://www.php.net/manual/en/function.floatval.php) | The error level when converting from object was changed from E\_NOTICE to E\_WARNING. |
|  | [floor](https://www.php.net/manual/en/function.floor.php) | num no longer accepts internal objects which support<br> numeric conversion. |
|  | [fprintf](https://www.php.net/manual/en/function.fprintf.php) | This function no longer returns false on failure. |
|  | [fprintf](https://www.php.net/manual/en/function.fprintf.php) | Throw a ValueError if the number of arguments is zero;<br> previously this function emitted a E\_WARNING instead. |
|  | [fprintf](https://www.php.net/manual/en/function.fprintf.php) | Throw a ValueError if \[width\] is less than zero or bigger than PHP\_INT\_MAX;<br> previously this function emitted a E\_WARNING instead. |
|  | [fprintf](https://www.php.net/manual/en/function.fprintf.php) | Throw a ValueError if \[precision\] is less than zero or bigger than PHP\_INT\_MAX;<br> previously this function emitted a E\_WARNING instead. |
|  | [fprintf](https://www.php.net/manual/en/function.fprintf.php) | Throw a ArgumentCountError when less arguments are given than required;<br> previously this function emitted a E\_WARNING instead. |
|  | [fsockopen](https://www.php.net/manual/en/function.fsockopen.php) | timeout is nullable now. |
|  | [fwrite](https://www.php.net/manual/en/function.fwrite.php) | length is nullable now. |
|  | [get\_called\_class](https://www.php.net/manual/en/function.get-called-class.php) | Calling this function from outside a class,<br> will now throw an Error.<br> Previously, an E\_WARNING was raised<br> and the function returned false. |
|  | [get\_class](https://www.php.net/manual/en/function.get-class.php) | Calling this function from outside a class, without any arguments,<br> will now throw an Error.<br> Previously, an E\_WARNING was raised<br> and the function returned false. |
|  | [get\_class\_methods](https://www.php.net/manual/en/function.get-class-methods.php) | The object\_or\_class parameter now only accepts objects or valid class names. |
|  | [get\_defined\_functions](https://www.php.net/manual/en/function.get-defined-functions.php) | The default value of the exclude\_disabled parameter<br> has been changed from false to true. However, it will not have<br> any effect as disabled functions are removed from the function table at<br> compile time. |
|  | [get\_headers](https://www.php.net/manual/en/function.get-headers.php) | The associative has been changed from int to bool. |
|  | [get\_magic\_quotes\_gpc](https://www.php.net/manual/en/function.get-magic-quotes-gpc.php) | Removed this function. |
|  | [get\_magic\_quotes\_runtime](https://www.php.net/manual/en/function.get-magic-quotes-runtime.php) | Removed this function. |
|  | [get\_parent\_class](https://www.php.net/manual/en/function.get-parent-class.php) | The object\_or\_class parameter now only accepts objects or valid class names. |
|  | [get\_resources](https://www.php.net/manual/en/function.get-resources.php) | type is nullable now. |
|  | [getdate](https://www.php.net/manual/en/function.getdate.php) | timestamp is nullable now. |
|  | [getenv](https://www.php.net/manual/en/function.getenv.php) | The name is now nullable. |
|  | [gmdate](https://www.php.net/manual/en/function.gmdate.php) | timestamp is nullable now. |
|  | [gmmktime](https://www.php.net/manual/en/function.gmmktime.php) | hour is no longer optional. If you need a Unix<br> timestamp, use time. |
|  | [gmmktime](https://www.php.net/manual/en/function.gmmktime.php) | minute, second, month,<br> day and year are nullable now. |
|  | [gmp\_binomial](https://www.php.net/manual/en/function.gmp-binomial.php) | This function no longer returns false on failure. |
|  | [gmp\_export](https://www.php.net/manual/en/function.gmp-export.php) | This function no longer returns false on failure. |
|  | [gmp\_import](https://www.php.net/manual/en/function.gmp-import.php) | This function no longer returns false on failure. |
|  | [gmp\_random\_seed](https://www.php.net/manual/en/function.gmp-random-seed.php) | If seed is invalid, gmp\_random\_seed<br> now throws a ValueError.<br> Previously it emitted an E\_WARNING and returned false. |
|  | [gmstrftime](https://www.php.net/manual/en/function.gmstrftime.php) | timestamp is nullable now. |
|  | [grapheme\_substr](https://www.php.net/manual/en/function.grapheme-substr.php) | The function now consistently clamps out-of-bounds offsets to the string boundary.<br> Previously, false was returned instead of the empty string in some cases. |
|  | [gzgets](https://www.php.net/manual/en/function.gzgets.php) | length is nullable now;<br> previously, the default was 1024. |
|  | [gzwrite](https://www.php.net/manual/en/function.gzwrite.php) | length is nullable now; previously, the default was<br> 0. |
|  | [hash](https://www.php.net/manual/en/function.hash.php) | hash now throws a ValueError exception<br> if algo is unknown; previously, false was returned instead. |
|  | [hash\_hkdf](https://www.php.net/manual/en/function.hash-hkdf.php) | Now throws a ValueError exception on error.<br> Previously, false was returned and an E\_WARNING<br> message was emitted. |
|  | [hash\_hmac](https://www.php.net/manual/en/function.hash-hmac.php) | Now throws a ValueError exception if<br> algo is unknown or is a<br> non-cryptographic hash function; previously, false was returned instead. |
|  | [hash\_hmac\_file](https://www.php.net/manual/en/function.hash-hmac-file.php) | Now throws a ValueError exception if<br> algo is unknown or is a non-cryptographic hash<br> function; previously, false was returned instead. |
|  | [hash\_init](https://www.php.net/manual/en/function.hash-init.php) | Now throws an ValueError exception if the<br> algo is unknown or is a non-cryptographic hash<br> function, or if key is empty. Previously,<br> false was returned and an E\_WARNING message was<br> emitted. |
|  | [hash\_pbkdf2](https://www.php.net/manual/en/function.hash-pbkdf2.php) | Now throws a ValueError exception on error.<br> Previously, false was returned and an E\_WARNING<br> message was emitted. |
|  | [hash\_update\_file](https://www.php.net/manual/en/function.hash-update-file.php) | stream\_context is now nullable. |
|  | [header\_remove](https://www.php.net/manual/en/function.header-remove.php) | name is nullable now. |
|  | [hebrevc](https://www.php.net/manual/en/function.hebrevc.php) | Removed this function. |
|  | [html\_entity\_decode](https://www.php.net/manual/en/function.html-entity-decode.php) | encoding is nullable now. |
|  | [htmlentities](https://www.php.net/manual/en/function.htmlentities.php) | encoding is nullable now. |
|  | [http\_build\_query](https://www.php.net/manual/en/function.http-build-query.php) | arg\_separator is now nullable. |
|  | [iconv\_mime\_decode](https://www.php.net/manual/en/function.iconv-mime-decode.php) | encoding is nullable now. |
|  | [iconv\_mime\_decode\_headers](https://www.php.net/manual/en/function.iconv-mime-decode-headers.php) | encoding is nullable now. |
|  | [iconv\_strlen](https://www.php.net/manual/en/function.iconv-strlen.php) | encoding is nullable now. |
|  | [iconv\_strpos](https://www.php.net/manual/en/function.iconv-strpos.php) | encoding is nullable now. |
|  | [iconv\_strrpos](https://www.php.net/manual/en/function.iconv-strrpos.php) | encoding is nullable now. |
|  | [iconv\_substr](https://www.php.net/manual/en/function.iconv-substr.php) | length and encoding are nullable now. |
|  | [idate](https://www.php.net/manual/en/function.idate.php) | timestamp is nullable now. |
|  | [ignore\_user\_abort](https://www.php.net/manual/en/function.ignore-user-abort.php) | enable is nullable now. |
|  | [imageaffine](https://www.php.net/manual/en/function.imageaffine.php) | clip is now nullable. |
|  | [imageaffine](https://www.php.net/manual/en/function.imageaffine.php) | On success, this function returns a GDImage instance now;<br> previously, a resource was returned. |
|  | [imagealphablending](https://www.php.net/manual/en/function.imagealphablending.php) | image expects a GdImage<br> instance now; previously, a valid gd resource was expected. |
|  | [imageantialias](https://www.php.net/manual/en/function.imageantialias.php) | image expects a GdImage<br> instance now; previously, a valid gd resource was expected. |
|  | [imagearc](https://www.php.net/manual/en/function.imagearc.php) | image expects a GdImage<br> instance now; previously, a valid gd resource was expected. |
|  | [imagebmp](https://www.php.net/manual/en/function.imagebmp.php) | image expects a GdImage<br> instance now; previously, a valid gd resource was expected. |
|  | [imagebmp](https://www.php.net/manual/en/function.imagebmp.php) | The type of compressed is bool now; formerly it was int. |
|  | [imagechar](https://www.php.net/manual/en/function.imagechar.php) | image expects a GdImage<br> instance now; previously, a valid gd resource was expected. |
|  | [imagecharup](https://www.php.net/manual/en/function.imagecharup.php) | image expects a GdImage<br> instance now; previously, a valid gd resource was expected. |
|  | [imagecolorallocate](https://www.php.net/manual/en/function.imagecolorallocate.php) | image expects a GdImage<br> instance now; previously, a valid gd resource was expected. |
|  | [imagecolorallocatealpha](https://www.php.net/manual/en/function.imagecolorallocatealpha.php) | image expects a GdImage<br> instance now; previously, a valid gd resource was expected. |
|  | [imagecolorat](https://www.php.net/manual/en/function.imagecolorat.php) | image expects a GdImage<br> instance now; previously, a valid gd resource was expected. |
|  | [imagecolorclosest](https://www.php.net/manual/en/function.imagecolorclosest.php) | image expects a GdImage<br> instance now; previously, a valid gd resource was expected. |
|  | [imagecolorclosesthwb](https://www.php.net/manual/en/function.imagecolorclosesthwb.php) | image expects a GdImage<br> instance now; previously, a valid gd resource was expected. |
|  | [imagecolordeallocate](https://www.php.net/manual/en/function.imagecolordeallocate.php) | image expects a GdImage<br> instance now; previously, a valid gd resource was expected. |
|  | [imagecolorexact](https://www.php.net/manual/en/function.imagecolorexact.php) | image expects a GdImage<br> instance now; previously, a valid gd resource was expected. |
|  | [imagecolorexactalpha](https://www.php.net/manual/en/function.imagecolorexactalpha.php) | image expects a GdImage<br> instance now; previously, a valid gd resource was expected. |
|  | [imagecolormatch](https://www.php.net/manual/en/function.imagecolormatch.php) | image1 and image2 expect<br> GdImage instances now; previously, resources<br> were expected. |
|  | [imagecolorresolve](https://www.php.net/manual/en/function.imagecolorresolve.php) | image expects a GdImage<br> instance now; previously, a valid gd resource was expected. |
|  | [imagecolorresolvealpha](https://www.php.net/manual/en/function.imagecolorresolvealpha.php) | image expects a GdImage<br> instance now; previously, a valid gd resource was expected. |
|  | [imagecolorset](https://www.php.net/manual/en/function.imagecolorset.php) | image expects a GdImage<br> instance now; previously, a valid gd resource was expected. |
|  | [imagecolorsforindex](https://www.php.net/manual/en/function.imagecolorsforindex.php) | image expects a GdImage<br> instance now; previously, a valid gd resource was expected. |
|  | [imagecolorsforindex](https://www.php.net/manual/en/function.imagecolorsforindex.php) | imagecolorsforindex now throws a ValueError exception<br> if color is out of range; previously, false was returned instead. |
|  | [imagecolorstotal](https://www.php.net/manual/en/function.imagecolorstotal.php) | image expects a GdImage<br> instance now; previously, a valid gd resource was expected. |
|  | [imagecolortransparent](https://www.php.net/manual/en/function.imagecolortransparent.php) | image expects a GdImage<br> instance now; previously, a valid gd resource was expected. |
|  | [imagecolortransparent](https://www.php.net/manual/en/function.imagecolortransparent.php) | color is now nullable. |
|  | [imageconvolution](https://www.php.net/manual/en/function.imageconvolution.php) | image expects a GdImage<br> instance now; previously, a valid gd resource was expected. |
|  | [imagecopy](https://www.php.net/manual/en/function.imagecopy.php) | dst\_image and src\_image expect<br> GdImage instances now; previously, resources<br> were expected. |
|  | [imagecopymerge](https://www.php.net/manual/en/function.imagecopymerge.php) | dst\_image and src\_image expect<br> GdImage instances now; previously, resources<br> were expected. |
|  | [imagecopymergegray](https://www.php.net/manual/en/function.imagecopymergegray.php) | dst\_image and src\_image expect<br> GdImage instances now; previously, resources<br> were expected. |
|  | [imagecopyresampled](https://www.php.net/manual/en/function.imagecopyresampled.php) | dst\_image and src\_image expect<br> GdImage instances now; previously, resources<br> were expected. |
|  | [imagecopyresized](https://www.php.net/manual/en/function.imagecopyresized.php) | dst\_image and src\_image expect<br> GdImage instances now; previously, resources<br> were expected. |
|  | [imagecreate](https://www.php.net/manual/en/function.imagecreate.php) | On success, this function returns a GDImage instance now;<br> previously, a resource was returned. |
|  | [imagecreatefrombmp](https://www.php.net/manual/en/function.imagecreatefrombmp.php) | On success, this function returns a GDImage instance now;<br> previously, a resource was returned. |
|  | [imagecreatefromgd](https://www.php.net/manual/en/function.imagecreatefromgd.php) | On success, this function returns a GDImage instance now;<br> previously, a resource was returned. |
|  | [imagecreatefromgd2](https://www.php.net/manual/en/function.imagecreatefromgd2.php) | On success, this function returns a GDImage instance now;<br> previously, a resource was returned. |
|  | [imagecreatefromgd2part](https://www.php.net/manual/en/function.imagecreatefromgd2part.php) | On success, this function returns a GDImage instance now;<br> previously, a resource was returned. |
|  | [imagecreatefromgif](https://www.php.net/manual/en/function.imagecreatefromgif.php) | On success, this function returns a GDImage instance now;<br> previously, a resource was returned. |
|  | [imagecreatefromjpeg](https://www.php.net/manual/en/function.imagecreatefromjpeg.php) | On success, this function returns a GDImage instance now;<br> previously, a resource was returned. |
|  | [imagecreatefrompng](https://www.php.net/manual/en/function.imagecreatefrompng.php) | On success, this function returns a GDImage instance now;<br> previously, a resource was returned. |
|  | [imagecreatefromstring](https://www.php.net/manual/en/function.imagecreatefromstring.php) | On success, this function returns a GDImage instance now;<br> previously, a resource was returned. |
|  | [imagecreatefromtga](https://www.php.net/manual/en/function.imagecreatefromtga.php) | On success, this function returns a GDImage instance now;<br> previously, a resource was returned. |
|  | [imagecreatefromwbmp](https://www.php.net/manual/en/function.imagecreatefromwbmp.php) | On success, this function returns a GDImage instance now;<br> previously, a resource was returned. |
|  | [imagecreatefromwebp](https://www.php.net/manual/en/function.imagecreatefromwebp.php) | On success, this function returns a GDImage instance now;<br> previously, a resource was returned. |
|  | [imagecreatefromxbm](https://www.php.net/manual/en/function.imagecreatefromxbm.php) | On success, this function returns a GDImage instance now;<br> previously, a resource was returned. |
|  | [imagecreatefromxpm](https://www.php.net/manual/en/function.imagecreatefromxpm.php) | On success, this function returns a GDImage instance now;<br> previously, a resource was returned. |
|  | [imagecreatetruecolor](https://www.php.net/manual/en/function.imagecreatetruecolor.php) | On success, this function returns a GDImage instance now;<br> previously, a resource was returned. |
|  | [imagecrop](https://www.php.net/manual/en/function.imagecrop.php) | image expects a GdImage<br> instance now; previously, a valid gd resource was expected. |
|  | [imagecrop](https://www.php.net/manual/en/function.imagecrop.php) | On success, this function returns a GDImage instance now;<br> previously, a resource was returned. |
|  | [imagecropauto](https://www.php.net/manual/en/function.imagecropauto.php) | image expects a GdImage<br> instance now; previously, a valid gd resource was expected. |
|  | [imagecropauto](https://www.php.net/manual/en/function.imagecropauto.php) | On success, this function returns a GDImage instance now;<br> previously, a resource was returned. |
|  | [imagedashedline](https://www.php.net/manual/en/function.imagedashedline.php) | image expects a GdImage<br> instance now; previously, a valid gd resource was expected. |
|  | [imagedestroy](https://www.php.net/manual/en/function.imagedestroy.php) | This function is a NOP now. |
|  | [imagedestroy](https://www.php.net/manual/en/function.imagedestroy.php) | image expects a GdImage<br> instance now; previously, a valid gd resource was expected. |
|  | [imageellipse](https://www.php.net/manual/en/function.imageellipse.php) | image expects a GdImage<br> instance now; previously, a valid gd resource was expected. |
|  | [imagefill](https://www.php.net/manual/en/function.imagefill.php) | image expects a GdImage<br> instance now; previously, a valid gd resource was expected. |
|  | [imagefilledarc](https://www.php.net/manual/en/function.imagefilledarc.php) | image expects a GdImage<br> instance now; previously, a valid gd resource was expected. |
|  | [imagefilledellipse](https://www.php.net/manual/en/function.imagefilledellipse.php) | image expects a GdImage<br> instance now; previously, a valid gd resource was expected. |
|  | [imagefilledpolygon](https://www.php.net/manual/en/function.imagefilledpolygon.php) | image expects a GdImage<br> instance now; previously, a valid gd resource was expected. |
|  | [imagefilledrectangle](https://www.php.net/manual/en/function.imagefilledrectangle.php) | image expects a GdImage<br> instance now; previously, a valid gd resource was expected. |
|  | [imagefilltoborder](https://www.php.net/manual/en/function.imagefilltoborder.php) | image expects a GdImage<br> instance now; previously, a valid gd resource was expected. |
|  | [imagefilter](https://www.php.net/manual/en/function.imagefilter.php) | image expects a GdImage<br> instance now; previously, a valid gd resource was expected. |
|  | [imageflip](https://www.php.net/manual/en/function.imageflip.php) | image expects a GdImage<br> instance now; previously, a valid gd resource was expected. |
|  | [imagefttext](https://www.php.net/manual/en/function.imagefttext.php) | image expects a GdImage<br> instance now; previously, a valid gd resource was expected. |
|  | [imagegammacorrect](https://www.php.net/manual/en/function.imagegammacorrect.php) | image expects a GdImage<br> instance now; previously, a valid gd resource was expected. |
|  | [imagegd](https://www.php.net/manual/en/function.imagegd.php) | image expects a GdImage<br> instance now; previously, a valid gd resource was expected. |
|  | [imagegd2](https://www.php.net/manual/en/function.imagegd2.php) | image expects a GdImage<br> instance now; previously, a valid gd resource was expected. |
|  | [imagegetclip](https://www.php.net/manual/en/function.imagegetclip.php) | image expects a GdImage<br> instance now; previously, a valid gd resource was expected. |
|  | [imagegetinterpolation](https://www.php.net/manual/en/function.imagegetinterpolation.php) | image expects a GdImage<br> instance now; previously, a valid gd resource was expected. |
|  | [imagegif](https://www.php.net/manual/en/function.imagegif.php) | image expects a GdImage<br> instance now; previously, a valid gd resource was expected. |
|  | [imagegrabscreen](https://www.php.net/manual/en/function.imagegrabscreen.php) | On success, this function returns a GDImage instance now;<br> previously, a resource was returned. |
|  | [imagegrabwindow](https://www.php.net/manual/en/function.imagegrabwindow.php) | On success, this function returns a GDImage instance now;<br> previously, a resource was returned. |
|  | [imagegrabwindow](https://www.php.net/manual/en/function.imagegrabwindow.php) | client\_area expects a bool now;<br> previously it expected an int. |
|  | [imageinterlace](https://www.php.net/manual/en/function.imageinterlace.php) | image expects a GdImage<br> instance now; previously, a valid gd resource was expected. |
|  | [imageinterlace](https://www.php.net/manual/en/function.imageinterlace.php) | enable expects a bool now;<br> previously it expected an int. |
|  | [imageistruecolor](https://www.php.net/manual/en/function.imageistruecolor.php) | image expects a GdImage<br> instance now; previously, a valid gd resource was expected. |
|  | [imagejpeg](https://www.php.net/manual/en/function.imagejpeg.php) | image expects a GdImage<br> instance now; previously, a valid gd resource was expected. |
|  | [imagelayereffect](https://www.php.net/manual/en/function.imagelayereffect.php) | image expects a GdImage<br> instance now; previously, a valid gd resource was expected. |
|  | [imageline](https://www.php.net/manual/en/function.imageline.php) | image expects a GdImage<br> instance now; previously, a valid gd resource was expected. |
|  | [imageopenpolygon](https://www.php.net/manual/en/function.imageopenpolygon.php) | image expects a GdImage<br> instance now; previously, a valid gd resource was expected. |
|  | [imagepalettecopy](https://www.php.net/manual/en/function.imagepalettecopy.php) | dst and src expect<br> GdImage instances now; previously, resources<br> were expected. |
|  | [imagepalettetotruecolor](https://www.php.net/manual/en/function.imagepalettetotruecolor.php) | image expects a GdImage<br> instance now; previously, a valid gd resource was expected. |
|  | [imagepng](https://www.php.net/manual/en/function.imagepng.php) | image expects a GdImage<br> instance now; previously, a valid gd resource was expected. |
|  | [imagepolygon](https://www.php.net/manual/en/function.imagepolygon.php) | image expects a GdImage<br> instance now; previously, a valid gd resource was expected. |
|  | [imagerectangle](https://www.php.net/manual/en/function.imagerectangle.php) | image expects a GdImage<br> instance now; previously, a valid gd resource was expected. |
|  | [imageresolution](https://www.php.net/manual/en/function.imageresolution.php) | resolution\_x and resolution\_y are now nullable. |
|  | [imagerotate](https://www.php.net/manual/en/function.imagerotate.php) | On success, this function returns a GDImage instance now;<br> previously, a resource was returned. |
|  | [imagerotate](https://www.php.net/manual/en/function.imagerotate.php) | image expects a GdImage<br> instance now; previously, a valid gd resource was expected. |
|  | [imagerotate](https://www.php.net/manual/en/function.imagerotate.php) | The unused ignore\_transparent expects a bool now;<br> previously it expected an int. |
|  | [imagesavealpha](https://www.php.net/manual/en/function.imagesavealpha.php) | image expects a GdImage<br> instance now; previously, a valid gd resource was expected. |
|  | [imagescale](https://www.php.net/manual/en/function.imagescale.php) | On success, this function returns a GDImage instance now;<br> previously, a resource was returned. |
|  | [imagescale](https://www.php.net/manual/en/function.imagescale.php) | image expects a GdImage<br> instance now; previously, a valid gd resource was expected. |
|  | [imagesetbrush](https://www.php.net/manual/en/function.imagesetbrush.php) | image and brush expect<br> GdImage instances now; previously, resources<br> were expected. |
|  | [imagesetclip](https://www.php.net/manual/en/function.imagesetclip.php) | image expects a GdImage<br> instance now; previously, a valid gd resource was expected. |
|  | [imagesetinterpolation](https://www.php.net/manual/en/function.imagesetinterpolation.php) | image expects a GdImage<br> instance now; previously, a valid gd resource was expected. |
|  | [imagesetpixel](https://www.php.net/manual/en/function.imagesetpixel.php) | image expects a GdImage<br> instance now; previously, a valid gd resource was expected. |
|  | [imagesetthickness](https://www.php.net/manual/en/function.imagesetthickness.php) | image expects a GdImage<br> instance now; previously, a valid gd resource was expected. |
|  | [imagesettile](https://www.php.net/manual/en/function.imagesettile.php) | image and tile expect<br> GdImage instances now; previously, resources<br> were expected. |
|  | [imagestring](https://www.php.net/manual/en/function.imagestring.php) | image expects a GdImage<br> instance now; previously, a valid gd resource was expected. |
|  | [imagestringup](https://www.php.net/manual/en/function.imagestringup.php) | image expects a GdImage<br> instance now; previously, a valid gd resource was expected. |
|  | [imagesx](https://www.php.net/manual/en/function.imagesx.php) | image expects a GdImage<br> instance now; previously, a valid gd resource was expected. |
|  | [imagesy](https://www.php.net/manual/en/function.imagesy.php) | image expects a GdImage<br> instance now; previously, a valid gd resource was expected. |
|  | [imagetruecolortopalette](https://www.php.net/manual/en/function.imagetruecolortopalette.php) | image expects a GdImage<br> instance now; previously, a valid gd resource was expected. |
|  | [imagettfbbox](https://www.php.net/manual/en/function.imagettfbbox.php) | The options has been added. |
|  | [imagettftext](https://www.php.net/manual/en/function.imagettftext.php) | The options has been added. |
|  | [imagewbmp](https://www.php.net/manual/en/function.imagewbmp.php) | image expects a GdImage<br> instance now; previously, a valid gd resource was expected. |
|  | [imagewbmp](https://www.php.net/manual/en/function.imagewbmp.php) | foreground\_color is nullable now. |
|  | [imagewebp](https://www.php.net/manual/en/function.imagewebp.php) | image expects a GdImage<br> instance now; previously, a valid gd resource was expected. |
|  | [imagexbm](https://www.php.net/manual/en/function.imagexbm.php) | image expects a GdImage<br> instance now; previously, a valid gd resource was expected. |
|  | [imagexbm](https://www.php.net/manual/en/function.imagexbm.php) | foreground\_color is now nullable. |
|  | [imagexbm](https://www.php.net/manual/en/function.imagexbm.php) | The fourth parameter, which was unused, has been removed. |
|  | [implode](https://www.php.net/manual/en/function.implode.php) | Passing the separator after the array<br> is no longer supported. |
|  | [inflate\_add](https://www.php.net/manual/en/function.inflate-add.php) | context expects an InflateContext<br> instance now; previously, a resource was expected. |
|  | [inflate\_get\_read\_len](https://www.php.net/manual/en/function.inflate-get-read-len.php) | context expects an InflateContext<br> instance now; previously, a resource was expected. |
|  | [inflate\_get\_status](https://www.php.net/manual/en/function.inflate-get-status.php) | context expects an InflateContext<br> instance now; previously, a resource was expected. |
|  | [inflate\_init](https://www.php.net/manual/en/function.inflate-init.php) | On success, this function returns an InflateContext instance now;<br> previously, a resource was returned. |
|  | [intval](https://www.php.net/manual/en/function.intval.php) | The error level when converting from object was changed from E\_NOTICE to E\_WARNING. |
|  | [is\_numeric](https://www.php.net/manual/en/function.is-numeric.php) | Numeric strings ending with whitespace ("42 ") will now<br> return true. Previously, false was returned instead. |
|  | [jdtounix](https://www.php.net/manual/en/function.jdtounix.php) | This function no longer returns false on failure, but raises a<br> ValueError instead. |
|  | [ldap\_add](https://www.php.net/manual/en/function.ldap-add.php) | controls is nullable now; previously, it defaulted to \[\]. |
|  | [ldap\_add\_ext](https://www.php.net/manual/en/function.ldap-add-ext.php) | controls is nullable now; previously, it defaulted to \[\]. |
|  | [ldap\_bind\_ext](https://www.php.net/manual/en/function.ldap-bind-ext.php) | controls is nullable now; previously, it defaulted to \[\]. |
|  | [ldap\_compare](https://www.php.net/manual/en/function.ldap-compare.php) | controls is nullable now; previously, it defaulted to \[\]. |
|  | [ldap\_control\_paged\_result](https://www.php.net/manual/en/function.ldap-control-paged-result.php) | This function has been removed. |
|  | [ldap\_control\_paged\_result\_response](https://www.php.net/manual/en/function.ldap-control-paged-result-response.php) | This function has been removed. |
|  | [ldap\_delete](https://www.php.net/manual/en/function.ldap-delete.php) | controls is nullable now; previously, it defaulted to \[\]. |
|  | [ldap\_delete\_ext](https://www.php.net/manual/en/function.ldap-delete-ext.php) | controls is nullable now; previously, it defaulted to \[\]. |
|  | [ldap\_exop\_passwd](https://www.php.net/manual/en/function.ldap-exop-passwd.php) | controls is nullable now; previously, it defaulted to \[\]. |
|  | [ldap\_first\_attribute](https://www.php.net/manual/en/function.ldap-first-attribute.php) | The unused third parameter ber\_identifier is no longer accepted. |
|  | [ldap\_list](https://www.php.net/manual/en/function.ldap-list.php) | controls is nullable now; previously, it defaulted to \[\]. |
|  | [ldap\_mod\_add](https://www.php.net/manual/en/function.ldap-mod-add.php) | controls is nullable now; previously, it defaulted to \[\]. |
|  | [ldap\_mod\_del](https://www.php.net/manual/en/function.ldap-mod-del.php) | controls is nullable now; previously, it defaulted to \[\]. |
|  | [ldap\_mod\_replace](https://www.php.net/manual/en/function.ldap-mod-replace.php) | controls is nullable now; previously, it defaulted to \[\]. |
|  | [ldap\_modify\_batch](https://www.php.net/manual/en/function.ldap-modify-batch.php) | controls is nullable now; previously, it defaulted to \[\]. |
|  | [ldap\_mod\_add\_ext](https://www.php.net/manual/en/function.ldap-mod_add-ext.php) | controls is nullable now; previously, it defaulted to \[\]. |
|  | [ldap\_mod\_del\_ext](https://www.php.net/manual/en/function.ldap-mod_del-ext.php) | controls is nullable now; previously, it defaulted to \[\]. |
|  | [ldap\_mod\_replace\_ext](https://www.php.net/manual/en/function.ldap-mod_replace-ext.php) | controls is nullable now; previously, it defaulted to \[\]. |
|  | [ldap\_next\_attribute](https://www.php.net/manual/en/function.ldap-next-attribute.php) | The unused third parameter ber\_identifier is no longer accepted. |
|  | [ldap\_read](https://www.php.net/manual/en/function.ldap-read.php) | controls is nullable now; previously, it defaulted to \[\]. |
|  | [ldap\_rename](https://www.php.net/manual/en/function.ldap-rename.php) | controls is nullable now; previously, it defaulted to \[\]. |
|  | [ldap\_rename\_ext](https://www.php.net/manual/en/function.ldap-rename-ext.php) | controls is nullable now; previously, it defaulted to \[\]. |
|  | [ldap\_sasl\_bind](https://www.php.net/manual/en/function.ldap-sasl-bind.php) | dn, password, mech,<br> realm, authc\_id, authz\_id<br> and props are nullable now. |
|  | [ldap\_search](https://www.php.net/manual/en/function.ldap-search.php) | controls is nullable now; previously, it defaulted to \[\]. |
|  | [ldap\_set\_rebind\_proc](https://www.php.net/manual/en/function.ldap-set-rebind-proc.php) | callback is nullable now. |
|  | [ldap\_sort](https://www.php.net/manual/en/function.ldap-sort.php) | This function has been removed. |
|  | [levenshtein](https://www.php.net/manual/en/function.levenshtein.php) | Prior to this version, levenshtein had to be called<br> with either two or five arguments. |
|  | [levenshtein](https://www.php.net/manual/en/function.levenshtein.php) | Prior to this version, levenshtein would return -1<br> if one of the argument strings is longer than 255 characters. |
|  | [libxml\_disable\_entity\_loader](https://www.php.net/manual/en/function.libxml-disable-entity-loader.php) | This function has been deprecated. |
|  | [libxml\_use\_internal\_errors](https://www.php.net/manual/en/function.libxml-use-internal-errors.php) | use\_errors is nullable now. Previously, its default<br> was false. |
|  | [localtime](https://www.php.net/manual/en/function.localtime.php) | timestamp is nullable now. |
|  | [max](https://www.php.net/manual/en/function.max.php) | max throws a ValueError on failure now;<br> previously, false was returned and an E\_WARNING error was emitted. |
|  | [max](https://www.php.net/manual/en/function.max.php) | As <br> string to number comparisons were changed,<br> max no longer returns a<br> different value based on the argument order in those cases. |
|  | [mb\_check\_encoding](https://www.php.net/manual/en/function.mb-check-encoding.php) | value and encoding are nullable now. |
|  | [mb\_chr](https://www.php.net/manual/en/function.mb-chr.php) | encoding is nullable now. |
|  | [mb\_convert\_encoding](https://www.php.net/manual/en/function.mb-convert-encoding.php) | mb\_convert\_encoding will now throw a<br> ValueError when<br> to\_encoding is passed an invalid encoding. |
|  | [mb\_convert\_encoding](https://www.php.net/manual/en/function.mb-convert-encoding.php) | mb\_convert\_encoding will now throw a<br> ValueError when<br> from\_encoding is passed an invalid encoding. |
|  | [mb\_convert\_encoding](https://www.php.net/manual/en/function.mb-convert-encoding.php) | from\_encoding is nullable now. |
|  | [mb\_convert\_kana](https://www.php.net/manual/en/function.mb-convert-kana.php) | encoding is nullable now. |
|  | [mb\_decode\_numericentity](https://www.php.net/manual/en/function.mb-decode-numericentity.php) | encoding is nullable now. |
|  | [mb\_detect\_order](https://www.php.net/manual/en/function.mb-detect-order.php) | encoding is nullable now. |
|  | [mb\_encode\_mimeheader](https://www.php.net/manual/en/function.mb-encode-mimeheader.php) | charset and transfer\_encoding<br> are nullable now. |
|  | [mb\_encode\_numericentity](https://www.php.net/manual/en/function.mb-encode-numericentity.php) | encoding is nullable now. |
|  | [mb\_encoding\_aliases](https://www.php.net/manual/en/function.mb-encoding-aliases.php) | If the encoding is unknown, a ValueError<br> is now thrown; previously an E\_WARNING was emitted,<br> and the function returned false. |
|  | [mb\_ereg](https://www.php.net/manual/en/function.mb-ereg.php) | This function returns true on success now. Previously, it returned the byte length<br> of the matched string if a match for pattern was found in<br> string and matches was passed.<br> If the optional parameter matches was not passed or<br> the length of the matched string was 0, this function returned 1. |
|  | [mb\_ereg\_match](https://www.php.net/manual/en/function.mb-ereg-match.php) | options is nullable now. |
|  | [mb\_ereg\_replace](https://www.php.net/manual/en/function.mb-ereg-replace.php) | options is nullable now. |
|  | [mb\_ereg\_replace\_callback](https://www.php.net/manual/en/function.mb-ereg-replace-callback.php) | options is nullable now. |
|  | [mb\_ereg\_search](https://www.php.net/manual/en/function.mb-ereg-search.php) | pattern and options are nullable now. |
|  | [mb\_ereg\_search\_init](https://www.php.net/manual/en/function.mb-ereg-search-init.php) | pattern and options are nullable now. |
|  | [mb\_ereg\_search\_pos](https://www.php.net/manual/en/function.mb-ereg-search-pos.php) | pattern and options are nullable now. |
|  | [mb\_ereg\_search\_regs](https://www.php.net/manual/en/function.mb-ereg-search-regs.php) | pattern and options are nullable now. |
|  | [mb\_eregi](https://www.php.net/manual/en/function.mb-eregi.php) | This function returns true on success now. Previously, it returned the byte length<br> of the matched string if a match for pattern was found in<br> string and matches was passed.<br> If the optional parameter matches was not passed or<br> the length of the matched string was 0, this function returned 1. |
|  | [mb\_eregi\_replace](https://www.php.net/manual/en/function.mb-eregi-replace.php) | options is nullable now. |
|  | [mb\_get\_info](https://www.php.net/manual/en/function.mb-get-info.php) | The types "func\_overload"<br> and "func\_overload\_list" are no longer supported. |
|  | [mb\_http\_input](https://www.php.net/manual/en/function.mb-http-input.php) | type is nullable now. |
|  | [mb\_http\_output](https://www.php.net/manual/en/function.mb-http-output.php) | encoding is nullable now. |
|  | [mb\_internal\_encoding](https://www.php.net/manual/en/function.mb-internal-encoding.php) | encoding is nullable now. |
|  | [mb\_internal\_encoding](https://www.php.net/manual/en/function.mb-internal-encoding.php) | Now throws a ValueError if<br> encoding is an invalid encoding.<br> Previously a E\_WARNING was emitted instead. |
|  | [mb\_language](https://www.php.net/manual/en/function.mb-language.php) | language is nullable now. |
|  | [mb\_ord](https://www.php.net/manual/en/function.mb-ord.php) | encoding is nullable now. |
|  | [mb\_parse\_str](https://www.php.net/manual/en/function.mb-parse-str.php) | The second parameter was no longer optional. |
|  | [mb\_regex\_encoding](https://www.php.net/manual/en/function.mb-regex-encoding.php) | encoding is nullable now. |
|  | [mb\_regex\_set\_options](https://www.php.net/manual/en/function.mb-regex-set-options.php) | If the parameter options is given and not null, the previous<br> options are returned. Formerly, the current options have been returned. |
|  | [mb\_regex\_set\_options](https://www.php.net/manual/en/function.mb-regex-set-options.php) | options is nullable now. |
|  | [mb\_regex\_set\_options](https://www.php.net/manual/en/function.mb-regex-set-options.php) | The "e" option now throws a ValueError. |
|  | [mb\_scrub](https://www.php.net/manual/en/function.mb-scrub.php) | encoding is nullable now. |
|  | [mb\_send\_mail](https://www.php.net/manual/en/function.mb-send-mail.php) | additional\_params is nullable now. |
|  | [mb\_str\_split](https://www.php.net/manual/en/function.mb-str-split.php) | encoding is nullable now. |
|  | [mb\_str\_split](https://www.php.net/manual/en/function.mb-str-split.php) | This function no longer returns false on failure. |
|  | [mb\_strcut](https://www.php.net/manual/en/function.mb-strcut.php) | encoding is nullable now. |
|  | [mb\_strimwidth](https://www.php.net/manual/en/function.mb-strimwidth.php) | encoding is nullable now. |
|  | [mb\_stripos](https://www.php.net/manual/en/function.mb-stripos.php) | needle now accepts an empty string. |
|  | [mb\_stripos](https://www.php.net/manual/en/function.mb-stripos.php) | encoding is nullable now. |
|  | [mb\_stristr](https://www.php.net/manual/en/function.mb-stristr.php) | needle now accepts an empty string. |
|  | [mb\_stristr](https://www.php.net/manual/en/function.mb-stristr.php) | encoding is nullable now. |
|  | [mb\_strlen](https://www.php.net/manual/en/function.mb-strlen.php) | encoding is nullable now. |
|  | [mb\_strpos](https://www.php.net/manual/en/function.mb-strpos.php) | needle now accepts an empty string. |
|  | [mb\_strpos](https://www.php.net/manual/en/function.mb-strpos.php) | encoding is nullable now. |
|  | [mb\_strrchr](https://www.php.net/manual/en/function.mb-strrchr.php) | needle now accepts an empty string. |
|  | [mb\_strrchr](https://www.php.net/manual/en/function.mb-strrchr.php) | encoding is nullable now. |
|  | [mb\_strrichr](https://www.php.net/manual/en/function.mb-strrichr.php) | needle now accepts an empty string. |
|  | [mb\_strrichr](https://www.php.net/manual/en/function.mb-strrichr.php) | encoding is nullable now. |
|  | [mb\_strripos](https://www.php.net/manual/en/function.mb-strripos.php) | needle now accepts an empty string. |
|  | [mb\_strripos](https://www.php.net/manual/en/function.mb-strripos.php) | encoding is nullable now. |
|  | [mb\_strrpos](https://www.php.net/manual/en/function.mb-strrpos.php) | needle now accepts an empty string. |
|  | [mb\_strrpos](https://www.php.net/manual/en/function.mb-strrpos.php) | Passing the encoding as the third argument <br> instead of an offset has been removed. |
|  | [mb\_strrpos](https://www.php.net/manual/en/function.mb-strrpos.php) | encoding is nullable now. |
|  | [mb\_strstr](https://www.php.net/manual/en/function.mb-strstr.php) | needle now accepts an empty string. |
|  | [mb\_strstr](https://www.php.net/manual/en/function.mb-strstr.php) | encoding is nullable now. |
|  | [mb\_strwidth](https://www.php.net/manual/en/function.mb-strwidth.php) | encoding is nullable now. |
|  | [mb\_substitute\_character](https://www.php.net/manual/en/function.mb-substitute-character.php) | Passing an empty string to substitute\_character<br> is no longer supported; "none" should be passed instead. |
|  | [mb\_substitute\_character](https://www.php.net/manual/en/function.mb-substitute-character.php) | encoding is nullable now. |
|  | [mb\_substr](https://www.php.net/manual/en/function.mb-substr.php) | encoding is nullable now. |
|  | [mb\_substr\_count](https://www.php.net/manual/en/function.mb-substr-count.php) | encoding is nullable now. |
|  | [metaphone](https://www.php.net/manual/en/function.metaphone.php) | The function returned false on failure. |
|  | [mhash](https://www.php.net/manual/en/function.mhash.php) | key is now nullable. |
|  | [min](https://www.php.net/manual/en/function.min.php) | min throws a ValueError on failure now;<br> previously, false was returned and an E\_WARNING error was emitted. |
|  | [min](https://www.php.net/manual/en/function.min.php) | As <br> string to number comparisons were changed,<br> min no longer returns a<br> different value based on the argument order in those cases. |
|  | [mktime](https://www.php.net/manual/en/function.mktime.php) | hour is no longer optional. If you need a Unix<br> timestamp, use time. |
|  | [mktime](https://www.php.net/manual/en/function.mktime.php) | minute, second, month,<br> day and year are nullable now. |
|  | [money\_format](https://www.php.net/manual/en/function.money-format.php) | Removed this function. |
|  | [msg\_get\_queue](https://www.php.net/manual/en/function.msg-get-queue.php) | On success, this function returns a SysvMessageQueue instance now;<br> previously, a resource was returned. |
|  | [msg\_receive](https://www.php.net/manual/en/function.msg-receive.php) | queue expects a SysvMessageQueue<br> instance now; previously, a resource was expected. |
|  | [msg\_remove\_queue](https://www.php.net/manual/en/function.msg-remove-queue.php) | queue expects a SysvMessageQueue<br> instance now; previously, a resource was expected. |
|  | [msg\_send](https://www.php.net/manual/en/function.msg-send.php) | queue expects a SysvMessageQueue<br> instance now; previously, a resource was expected. |
|  | [msg\_set\_queue](https://www.php.net/manual/en/function.msg-set-queue.php) | queue expects a SysvMessageQueue<br> instance now; previously, a resource was expected. |
|  | [msg\_stat\_queue](https://www.php.net/manual/en/function.msg-stat-queue.php) | queue expects a SysvMessageQueue<br> instance now; previously, a resource was expected. |
|  | [mt\_rand](https://www.php.net/manual/en/function.mt-rand.php) | A ValueError will be thrown if max is less than min;<br> previously an E\_WARNING was raised, and the function returned false. |
|  | [number\_format](https://www.php.net/manual/en/function.number-format.php) | Prior to this version, number\_format accepted<br> one, two, or four parameters (but not three). |
|  | [ob\_implicit\_flush](https://www.php.net/manual/en/function.ob-implicit-flush.php) | The enable expects a bool value now;<br> previously, an int was expected. |
|  | [odbc\_columns](https://www.php.net/manual/en/function.odbc-columns.php) | schema, table and column<br> are now nullable. |
|  | [odbc\_error](https://www.php.net/manual/en/function.odbc-error.php) | odbc is now nullable. |
|  | [odbc\_errormsg](https://www.php.net/manual/en/function.odbc-errormsg.php) | odbc is now nullable. |
|  | [odbc\_exec](https://www.php.net/manual/en/function.odbc-exec.php) | flags was removed. |
|  | [odbc\_execute](https://www.php.net/manual/en/function.odbc-execute.php) | The unused flags parameter was removed. |
|  | [odbc\_fetch\_row](https://www.php.net/manual/en/function.odbc-fetch-row.php) | row is now nullable. |
|  | [odbc\_procedurecolumns](https://www.php.net/manual/en/function.odbc-procedurecolumns.php) | Prior to this version, the function could only be called with either one<br> or five arguments. |
|  | [odbc\_procedures](https://www.php.net/manual/en/function.odbc-procedures.php) | Prior to this version, the function could only be called with either one<br> or four arguments. |
|  | [odbc\_tables](https://www.php.net/manual/en/function.odbc-tables.php) | schema, table and types<br> are now nullable. |
|  | [opendir](https://www.php.net/manual/en/function.opendir.php) | context is now nullable. |
|  | [openssl\_csr\_export](https://www.php.net/manual/en/function.openssl-csr-export.php) | csr accepts an OpenSSLCertificateSigningRequest instance now;<br> previously, a resource of type OpenSSL X.509 CSR was accepted. |
|  | [openssl\_csr\_export\_to\_file](https://www.php.net/manual/en/function.openssl-csr-export-to-file.php) | csr accepts an OpenSSLCertificateSigningRequest instance now;<br> previously, a resource of type OpenSSL X.509 CSR was accepted. |
|  | [openssl\_csr\_get\_public\_key](https://www.php.net/manual/en/function.openssl-csr-get-public-key.php) | On success, this function returns an OpenSSLAsymmetricKey instance now;<br> previously, a resource of type OpenSSL key was returned. |
|  | [openssl\_csr\_get\_public\_key](https://www.php.net/manual/en/function.openssl-csr-get-public-key.php) | csr accepts an OpenSSLCertificateSigningRequest instance now;<br> previously, a resource of type OpenSSL X.509 CSR was accepted. |
|  | [openssl\_csr\_get\_subject](https://www.php.net/manual/en/function.openssl-csr-get-subject.php) | csr accepts an OpenSSLCertificateSigningRequest instance now;<br> previously, a resource of type OpenSSL X.509 CSR was accepted. |
|  | [openssl\_csr\_new](https://www.php.net/manual/en/function.openssl-csr-new.php) | On success, this function returns an OpenSSLCertificateSigningRequest instance now;<br> previously, a resource of type OpenSSL X.509 CSR was returned. |
|  | [openssl\_csr\_new](https://www.php.net/manual/en/function.openssl-csr-new.php) | private\_key accepts an OpenSSLAsymmetricKey instance now;<br> previously, a resource of type OpenSSL key was accepted. |
|  | [openssl\_csr\_sign](https://www.php.net/manual/en/function.openssl-csr-sign.php) | On success, this function returns an OpenSSLCertificate instance now;<br> previously, a resource of type OpenSSL X.509 was returned. |
|  | [openssl\_csr\_sign](https://www.php.net/manual/en/function.openssl-csr-sign.php) | csr accepts an OpenSSLCertificateSigningRequest instance now;<br> previously, a resource of type OpenSSL X.509 CSR was accepted. |
|  | [openssl\_csr\_sign](https://www.php.net/manual/en/function.openssl-csr-sign.php) | ca\_certificate accepts an OpenSSLCertificate instance now;<br> previously, a resource of type OpenSSL X.509 was accepted. |
|  | [openssl\_csr\_sign](https://www.php.net/manual/en/function.openssl-csr-sign.php) | private\_key accepts an OpenSSLAsymmetricKey<br> or OpenSSLCertificate instance now;<br> previously, a resource of type OpenSSL key or OpenSSL X.509<br> was accepted. |
|  | [openssl\_dh\_compute\_key](https://www.php.net/manual/en/function.openssl-dh-compute-key.php) | private\_key accepts an OpenSSLAsymmetricKey now;<br> previously, a resource of type OpenSSL key was accepted. |
|  | [openssl\_free\_key](https://www.php.net/manual/en/function.openssl-free-key.php) | This function is now deprecated as it doesn't have an effect anymore. |
|  | [openssl\_free\_key](https://www.php.net/manual/en/function.openssl-free-key.php) | key accepts an OpenSSLAsymmetricKey now;<br> previously, a resource of type OpenSSL key was accepted. |
|  | [openssl\_open](https://www.php.net/manual/en/function.openssl-open.php) | private\_key accepts an OpenSSLAsymmetricKey<br> or OpenSSLCertificate instance now;<br> previously, a resource of type OpenSSL key or OpenSSL X.509 CSR<br> was accepted. |
|  | [openssl\_open](https://www.php.net/manual/en/function.openssl-open.php) | cipher\_algo is no longer an optional parameter. |
|  | [openssl\_pkcs7\_decrypt](https://www.php.net/manual/en/function.openssl-pkcs7-decrypt.php) | private\_key accepts an OpenSSLAsymmetricKey<br> or OpenSSLCertificate instance now;<br> previously, a resource of type OpenSSL key or OpenSSL X.509 CSR<br> was accepted. |
|  | [openssl\_pkcs7\_encrypt](https://www.php.net/manual/en/function.openssl-pkcs7-encrypt.php) | certificate accepts an OpenSSLCertificate instance now;<br> previously, a resource of type OpenSSL X.509 CSR was accepted. |
|  | [openssl\_pkcs7\_sign](https://www.php.net/manual/en/function.openssl-pkcs7-sign.php) | certificate accepts an OpenSSLCertificate instance now;<br> previously, a resource of type OpenSSL X.509 CSR was accepted. |
|  | [openssl\_pkcs7\_sign](https://www.php.net/manual/en/function.openssl-pkcs7-sign.php) | private\_key accepts an OpenSSLAsymmetricKey<br> or OpenSSLCertificate instance now;<br> previously, a resource of type OpenSSL key or OpenSSL X.509 CSR<br> was accepted. |
|  | [openssl\_pkcs7\_verify](https://www.php.net/manual/en/function.openssl-pkcs7-verify.php) | signers\_certificates\_filename, untrusted\_certificates\_filename,<br> content and output\_filename are nullable now. |
|  | [openssl\_pkcs12\_export](https://www.php.net/manual/en/function.openssl-pkcs12-export.php) | certificate accepts an OpenSSLCertificate instance now;<br> previously, a resource of type OpenSSL X.509 CSR was accepted. |
|  | [openssl\_pkcs12\_export](https://www.php.net/manual/en/function.openssl-pkcs12-export.php) | private\_key accepts an OpenSSLAsymmetricKey<br> or OpenSSLCertificate instance now;<br> previously, a resource of type OpenSSL key or OpenSSL X.509<br> was accepted. |
|  | [openssl\_pkcs12\_export\_to\_file](https://www.php.net/manual/en/function.openssl-pkcs12-export-to-file.php) | certificate accepts an OpenSSLCertificate instance now;<br> previously, a resource of type OpenSSL X.509 CSR was accepted. |
|  | [openssl\_pkcs12\_export\_to\_file](https://www.php.net/manual/en/function.openssl-pkcs12-export-to-file.php) | private\_key accepts an OpenSSLAsymmetricKey<br> or OpenSSLCertificate instance now;<br> previously, a resource of type OpenSSL key or OpenSSL X.509<br> was accepted. |
|  | [openssl\_pkey\_export](https://www.php.net/manual/en/function.openssl-pkey-export.php) | key accepts an OpenSSLAsymmetricKey<br> or OpenSSLCertificate instance now;<br> previously, a resource of type OpenSSL key or OpenSSL X.509<br> was accepted. |
|  | [openssl\_pkey\_export\_to\_file](https://www.php.net/manual/en/function.openssl-pkey-export-to-file.php) | key accepts an OpenSSLAsymmetricKey<br> or OpenSSLCertificate instance now;<br> previously, a resource of type OpenSSL key or OpenSSL X.509<br> was accepted. |
|  | [openssl\_pkey\_free](https://www.php.net/manual/en/function.openssl-pkey-free.php) | This function is now deprecated as it doesn't have an effect anymore. |
|  | [openssl\_pkey\_free](https://www.php.net/manual/en/function.openssl-pkey-free.php) | key accepts an OpenSSLAsymmetricKey now;<br> previously, a resource of type OpenSSL key was accepted. |
|  | [openssl\_pkey\_get\_details](https://www.php.net/manual/en/function.openssl-pkey-get-details.php) | key accepts an OpenSSLAsymmetricKey now;<br> previously, a resource of type OpenSSL key was accepted. |
|  | [openssl\_pkey\_get\_private](https://www.php.net/manual/en/function.openssl-pkey-get-private.php) | On success, this function returns an OpenSSLAsymmetricKey instance now;<br> previously, a resource of type OpenSSL key was returned. |
|  | [openssl\_pkey\_get\_private](https://www.php.net/manual/en/function.openssl-pkey-get-private.php) | private\_key accepts an OpenSSLAsymmetricKey<br> or OpenSSLCertificate instance now;<br> previously, a resource of type OpenSSL key or OpenSSL X.509<br> was accepted. |
|  | [openssl\_pkey\_get\_private](https://www.php.net/manual/en/function.openssl-pkey-get-private.php) | passphrase is nullable now. |
|  | [openssl\_pkey\_get\_public](https://www.php.net/manual/en/function.openssl-pkey-get-public.php) | On success, this function returns an OpenSSLAsymmetricKey instance now;<br> previously, a resource of type OpenSSL key was returned. |
|  | [openssl\_pkey\_get\_public](https://www.php.net/manual/en/function.openssl-pkey-get-public.php) | public\_key accepts an OpenSSLAsymmetricKey<br> or OpenSSLCertificate instance now;<br> previously, a resource of type OpenSSL key or OpenSSL X.509<br> was accepted. |
|  | [openssl\_pkey\_new](https://www.php.net/manual/en/function.openssl-pkey-new.php) | On success, this function returns an OpenSSLAsymmetricKey instance now;<br> previously, a resource of type OpenSSL key was returned. |
|  | [openssl\_private\_decrypt](https://www.php.net/manual/en/function.openssl-private-decrypt.php) | private\_key accepts an OpenSSLAsymmetricKey<br> or OpenSSLCertificate instance now;<br> previously, a resource of type OpenSSL key or OpenSSL X.509<br> was accepted. |
|  | [openssl\_private\_encrypt](https://www.php.net/manual/en/function.openssl-private-encrypt.php) | private\_key accepts an OpenSSLAsymmetricKey<br> or OpenSSLCertificate instance now;<br> previously, a resource of type OpenSSL key or OpenSSL X.509<br> was accepted. |
|  | [openssl\_public\_decrypt](https://www.php.net/manual/en/function.openssl-public-decrypt.php) | public\_key accepts an OpenSSLAsymmetricKey<br> or OpenSSLCertificate instance now;<br> previously, a resource of type OpenSSL key or OpenSSL X.509<br> was accepted. |
|  | [openssl\_public\_encrypt](https://www.php.net/manual/en/function.openssl-public-encrypt.php) | public\_key accepts an OpenSSLAsymmetricKey<br> or OpenSSLCertificate instance now;<br> previously, a resource of type OpenSSL key or OpenSSL X.509<br> was accepted. |
|  | [openssl\_random\_pseudo\_bytes](https://www.php.net/manual/en/function.openssl-random-pseudo-bytes.php) | strong\_result is nullable now. |
|  | [openssl\_seal](https://www.php.net/manual/en/function.openssl-seal.php) | public\_key accepts an array of<br> OpenSSLAsymmetricKey instances now;<br> previously, an array of resources of type OpenSSL key<br> was accepted. |
|  | [openssl\_seal](https://www.php.net/manual/en/function.openssl-seal.php) | cipher\_algo is no longer an optional parameter. |
|  | [openssl\_seal](https://www.php.net/manual/en/function.openssl-seal.php) | iv is nullable now. |
|  | [openssl\_sign](https://www.php.net/manual/en/function.openssl-sign.php) | private\_key accepts an OpenSSLAsymmetricKey<br> or OpenSSLCertificate instance now;<br> previously, a resource of type OpenSSL key or OpenSSL X.509<br> was accepted. |
|  | [openssl\_spki\_new](https://www.php.net/manual/en/function.openssl-spki-new.php) | private\_key accepts an OpenSSLAsymmetricKey instance now;<br> previously, a resource of type OpenSSL key was accepted. |
|  | [openssl\_verify](https://www.php.net/manual/en/function.openssl-verify.php) | public\_key accepts an OpenSSLAsymmetricKey<br> or OpenSSLCertificate instance now;<br> previously, a resource of type OpenSSL key or OpenSSL X.509<br> was accepted. |
|  | [openssl\_x509\_check\_private\_key](https://www.php.net/manual/en/function.openssl-x509-check-private-key.php) | certificate accepts an OpenSSLCertificate instance now;<br> previously, a resource of type OpenSSL X.509 was accepted. |
|  | [openssl\_x509\_check\_private\_key](https://www.php.net/manual/en/function.openssl-x509-check-private-key.php) | private\_key accepts an OpenSSLAsymmetricKey<br> or OpenSSLCertificate instance now;<br> previously, a resource of type OpenSSL key or OpenSSL X.509<br> was accepted. |
|  | [openssl\_x509\_checkpurpose](https://www.php.net/manual/en/function.openssl-x509-checkpurpose.php) | certificate accepts an OpenSSLCertificate instance now;<br> previously, a resource of type OpenSSL X.509 was accepted. |
|  | [openssl\_x509\_checkpurpose](https://www.php.net/manual/en/function.openssl-x509-checkpurpose.php) | untrusted\_certificates\_file is nullable now. |
|  | [openssl\_x509\_export](https://www.php.net/manual/en/function.openssl-x509-export.php) | certificate accepts an OpenSSLCertificate instance now;<br> previously, a resource of type OpenSSL X.509 was accepted. |
|  | [openssl\_x509\_export\_to\_file](https://www.php.net/manual/en/function.openssl-x509-export-to-file.php) | certificate accepts an OpenSSLCertificate instance now;<br> previously, a resource of type OpenSSL X.509 was accepted. |
|  | [openssl\_x509\_fingerprint](https://www.php.net/manual/en/function.openssl-x509-fingerprint.php) | certificate accepts an OpenSSLCertificate instance now;<br> previously, a resource of type OpenSSL X.509 was accepted. |
|  | [openssl\_x509\_free](https://www.php.net/manual/en/function.openssl-x509-free.php) | This function is now deprecated as it doesn't have an effect anymore. |
|  | [openssl\_x509\_free](https://www.php.net/manual/en/function.openssl-x509-free.php) | certificate accepts an OpenSSLCertificate instance now;<br> previously, a resource of type OpenSSL X.509 was accepted. |
|  | [openssl\_x509\_parse](https://www.php.net/manual/en/function.openssl-x509-parse.php) | certificate accepts an OpenSSLCertificate instance now;<br> previously, a resource of type OpenSSL X.509 was accepted. |
|  | [openssl\_x509\_read](https://www.php.net/manual/en/function.openssl-x509-read.php) | On success, this function returns an OpenSSLCertificate instance now;<br> previously, a resource of type OpenSSL X.509 was returned. |
|  | [openssl\_x509\_read](https://www.php.net/manual/en/function.openssl-x509-read.php) | certificate accepts an OpenSSLCertificate instance now;<br> previously, a resource of type OpenSSL X.509 was accepted. |
|  | [openssl\_x509\_verify](https://www.php.net/manual/en/function.openssl-x509-verify.php) | certificate accepts an OpenSSLCertificate instance now;<br> previously, a resource of type OpenSSL X.509 was accepted. |
|  | [openssl\_x509\_verify](https://www.php.net/manual/en/function.openssl-x509-verify.php) | public\_key accepts an OpenSSLAsymmetricKey<br> or OpenSSLCertificate instance now;<br> previously, a resource of type OpenSSL key or OpenSSL X.509<br> was accepted. |
|  | [pack](https://www.php.net/manual/en/function.pack.php) | This function no longer returns false on failure. |
|  | [parse\_str](https://www.php.net/manual/en/function.parse-str.php) | result is no longer optional. |
|  | [parse\_url](https://www.php.net/manual/en/function.parse-url.php) | parse\_url will now distinguish absent and empty queries<br> and fragments. |
|  | [passthru](https://www.php.net/manual/en/function.passthru.php) | If command is empty or contains null bytes,<br> passthru now throws a ValueError.<br> Previously it emitted an E\_WARNING and returned false. |
|  | [password\_hash](https://www.php.net/manual/en/function.password-hash.php) | password\_hash no longer returns false on failure, instead a<br> ValueError will be thrown if the password hashing algorithm<br> is not valid, or an Error if the password hashing failed<br> for an unknown error. |
|  | [password\_hash](https://www.php.net/manual/en/function.password-hash.php) | The algo parameter is nullable now. |
|  | [pcntl\_async\_signals](https://www.php.net/manual/en/function.pcntl-async-signals.php) | enable is nullable now. |
|  | [pcntl\_getpriority](https://www.php.net/manual/en/function.pcntl-getpriority.php) | process\_id is nullable now. |
|  | [pcntl\_setpriority](https://www.php.net/manual/en/function.pcntl-setpriority.php) | process\_id is nullable now. |
|  | [pfsockopen](https://www.php.net/manual/en/function.pfsockopen.php) | timeout is nullable now. |
|  | [pg\_client\_encoding](https://www.php.net/manual/en/function.pg-client-encoding.php) | connection is now nullable. |
|  | [pg\_close](https://www.php.net/manual/en/function.pg-close.php) | connection is now nullable. |
|  | [pg\_dbname](https://www.php.net/manual/en/function.pg-dbname.php) | connection is now nullable. |
|  | [pg\_end\_copy](https://www.php.net/manual/en/function.pg-end-copy.php) | connection is now nullable. |
|  | [pg\_fetch\_all](https://www.php.net/manual/en/function.pg-fetch-all.php) | pg\_fetch\_all will now return an empty array<br> instead of false for result sets with zero rows. |
|  | [pg\_host](https://www.php.net/manual/en/function.pg-host.php) | connection is now nullable. |
|  | [pg\_last\_error](https://www.php.net/manual/en/function.pg-last-error.php) | connection is now nullable. |
|  | [pg\_lo\_write](https://www.php.net/manual/en/function.pg-lo-write.php) | length is now nullable. |
|  | [pg\_options](https://www.php.net/manual/en/function.pg-options.php) | connection is now nullable. |
|  | [pg\_ping](https://www.php.net/manual/en/function.pg-ping.php) | connection is now nullable. |
|  | [pg\_port](https://www.php.net/manual/en/function.pg-port.php) | connection is now nullable. |
|  | [pg\_trace](https://www.php.net/manual/en/function.pg-trace.php) | connection is now nullable. |
|  | [pg\_tty](https://www.php.net/manual/en/function.pg-tty.php) | connection is now nullable. |
|  | [pg\_untrace](https://www.php.net/manual/en/function.pg-untrace.php) | connection is now nullable. |
|  | [pg\_version](https://www.php.net/manual/en/function.pg-version.php) | connection is now nullable. |
|  | [phpversion](https://www.php.net/manual/en/function.phpversion.php) | extension is nullable now. |
|  | [printf](https://www.php.net/manual/en/function.printf.php) | This function no longer returns false on failure. |
|  | [printf](https://www.php.net/manual/en/function.printf.php) | Throw a ValueError if the number of arguments is zero;<br> previously this function emitted a E\_WARNING instead. |
|  | [printf](https://www.php.net/manual/en/function.printf.php) | Throw a ValueError if \[width\] is less than zero or bigger than PHP\_INT\_MAX;<br> previously this function emitted a E\_WARNING instead. |
|  | [printf](https://www.php.net/manual/en/function.printf.php) | Throw a ValueError if \[precision\] is less than zero or bigger than PHP\_INT\_MAX;<br> previously this function emitted a E\_WARNING instead. |
|  | [printf](https://www.php.net/manual/en/function.printf.php) | Throw a ArgumentCountError when less arguments are given than required;<br> previously this function emitted a E\_WARNING instead. |
|  | [readdir](https://www.php.net/manual/en/function.readdir.php) | dir\_handle is now nullable. |
|  | [readline\_info](https://www.php.net/manual/en/function.readline-info.php) | var\_name and value are nullable now. |
|  | [readline\_read\_history](https://www.php.net/manual/en/function.readline-read-history.php) | filename is nullable now. |
|  | [readline\_write\_history](https://www.php.net/manual/en/function.readline-write-history.php) | filename is nullable now. |
|  | [restore\_include\_path](https://www.php.net/manual/en/function.restore-include-path.php) | Removed this function. |
|  | [rewinddir](https://www.php.net/manual/en/function.rewinddir.php) | dir\_handle is now nullable. |
|  | [round](https://www.php.net/manual/en/function.round.php) | num no longer accepts internal objects which support<br> numeric conversion. |
|  | [sapi\_windows\_vt100\_support](https://www.php.net/manual/en/function.sapi-windows-vt100-support.php) | enable is now nullable. |
|  | [scandir](https://www.php.net/manual/en/function.scandir.php) | context is now nullable. |
|  | [sem\_acquire](https://www.php.net/manual/en/function.sem-acquire.php) | semaphore expects a SysvSemaphore<br> instance now; previously, a resource was expected. |
|  | [sem\_get](https://www.php.net/manual/en/function.sem-get.php) | On success, this function returns a SysvSemaphore instance now;<br> previously, a resource was returned. |
|  | [sem\_get](https://www.php.net/manual/en/function.sem-get.php) | The type of auto\_release has been changed from<br> int to bool. |
|  | [sem\_release](https://www.php.net/manual/en/function.sem-release.php) | semaphore expects a SysvSemaphore<br> instance now; previously, a resource was expected. |
|  | [sem\_remove](https://www.php.net/manual/en/function.sem-remove.php) | semaphore expects a SysvSemaphore<br> instance now; previously, a resource was expected. |
|  | [session\_cache\_expire](https://www.php.net/manual/en/function.session-cache-expire.php) | value is nullable now. |
|  | [session\_cache\_limiter](https://www.php.net/manual/en/function.session-cache-limiter.php) | value is nullable now. |
|  | [session\_id](https://www.php.net/manual/en/function.session-id.php) | id is nullable now. |
|  | [session\_module\_name](https://www.php.net/manual/en/function.session-module-name.php) | module is nullable now. |
|  | [session\_name](https://www.php.net/manual/en/function.session-name.php) | name is nullable now. |
|  | [session\_save\_path](https://www.php.net/manual/en/function.session-save-path.php) | path is nullable now. |
|  | [session\_set\_cookie\_params](https://www.php.net/manual/en/function.session-set-cookie-params.php) | path, domain,<br> secure and httponly are nullable now. |
|  | [set\_error\_handler](https://www.php.net/manual/en/function.set-error-handler.php) | errcontext was removed, and will no longer be passed to user callbacks. |
|  | [shm\_attach](https://www.php.net/manual/en/function.shm-attach.php) | On success, this function returns an SysvSharedMemory instance now;<br> previously, a resource was returned. |
|  | [shm\_attach](https://www.php.net/manual/en/function.shm-attach.php) | size is nullable now. |
|  | [shm\_detach](https://www.php.net/manual/en/function.shm-detach.php) | shm expects a SysvSharedMemory<br> instance now; previously, a resource was expected. |
|  | [shm\_get\_var](https://www.php.net/manual/en/function.shm-get-var.php) | shm expects a SysvSharedMemory<br> instance now; previously, a resource was expected. |
|  | [shm\_has\_var](https://www.php.net/manual/en/function.shm-has-var.php) | shm expects a SysvSharedMemory<br> instance now; previously, a resource was expected. |
|  | [shm\_put\_var](https://www.php.net/manual/en/function.shm-put-var.php) | shm expects a SysvSharedMemory<br> instance now; previously, a resource was expected. |
|  | [shm\_remove](https://www.php.net/manual/en/function.shm-remove.php) | shm expects a SysvSharedMemory<br> instance now; previously, a resource was expected. |
|  | [shm\_remove\_var](https://www.php.net/manual/en/function.shm-remove-var.php) | shm expects a SysvSharedMemory<br> instance now; previously, a resource was expected. |
|  | [shmop\_close](https://www.php.net/manual/en/function.shmop-close.php) | This function has been deprecated, as this function has no effect anymore. |
|  | [shmop\_close](https://www.php.net/manual/en/function.shmop-close.php) | shmop expects a Shmop<br> instance now; previously, a resource was expected. |
|  | [shmop\_delete](https://www.php.net/manual/en/function.shmop-delete.php) | shmop expects a Shmop<br> instance now; previously, a resource was expected. |
|  | [shmop\_open](https://www.php.net/manual/en/function.shmop-open.php) | On success, this function returns an Shmop instance now;<br> previously, a resource was returned. |
|  | [shmop\_open](https://www.php.net/manual/en/function.shmop-open.php) | If mode is invalid, or size is less than or equal to zero,<br> a ValueError is thrown; previously E\_WARNING was emitted instead,<br> and the function returned false. |
|  | [shmop\_read](https://www.php.net/manual/en/function.shmop-read.php) | shmop expects a Shmop<br> instance now; previously, a resource was expected. |
|  | [shmop\_read](https://www.php.net/manual/en/function.shmop-read.php) | If offset or size are out of range,<br> a ValueError is thrown; previously E\_WARNING<br> was emitted, and false was returned, |
|  | [shmop\_size](https://www.php.net/manual/en/function.shmop-size.php) | shmop expects a Shmop<br> instance now; previously, a resource was expected. |
|  | [shmop\_write](https://www.php.net/manual/en/function.shmop-write.php) | Prior to PHP 8.0.0, false was returned on failure. |
|  | [shmop\_write](https://www.php.net/manual/en/function.shmop-write.php) | shmop expects a Shmop<br> instance now; previously, a resource was expected. |
|  | [sleep](https://www.php.net/manual/en/function.sleep.php) | The function throws a ValueError on negative seconds;<br> previously, an E\_WARNING was raised instead, and the function returned false. |
|  | [socket\_accept](https://www.php.net/manual/en/function.socket-accept.php) | On success, this function returns a Socket instance now;<br> previously, a resource was returned. |
|  | [socket\_addrinfo\_bind](https://www.php.net/manual/en/function.socket-addrinfo-bind.php) | On success, this function returns a Socket instance now;<br> previously, a resource was returned. |
|  | [socket\_addrinfo\_bind](https://www.php.net/manual/en/function.socket-addrinfo-bind.php) | address is an AddressInfo instance now;<br> previously, it was a resource. |
|  | [socket\_addrinfo\_connect](https://www.php.net/manual/en/function.socket-addrinfo-connect.php) | On success, this function returns a Socket instance now;<br> previously, a resource was returned. |
|  | [socket\_addrinfo\_connect](https://www.php.net/manual/en/function.socket-addrinfo-connect.php) | address is an AddressInfo instance now;<br> previously, it was a resource. |
|  | [socket\_addrinfo\_explain](https://www.php.net/manual/en/function.socket-addrinfo-explain.php) | address is an AddressInfo instance now;<br> previously, it was a resource. |
|  | [socket\_addrinfo\_lookup](https://www.php.net/manual/en/function.socket-addrinfo-lookup.php) | On success, this function returns a array of AddressInfo instances now;<br> previously, an array of resources was returned. |
|  | [socket\_addrinfo\_lookup](https://www.php.net/manual/en/function.socket-addrinfo-lookup.php) | service is nullable now. |
|  | [socket\_bind](https://www.php.net/manual/en/function.socket-bind.php) | socket is a Socket instance now;<br> previously, it was a resource. |
|  | [socket\_clear\_error](https://www.php.net/manual/en/function.socket-clear-error.php) | socket is a Socket instance now;<br> previously, it was a resource. |
|  | [socket\_clear\_error](https://www.php.net/manual/en/function.socket-clear-error.php) | socket is nullable now. |
|  | [socket\_close](https://www.php.net/manual/en/function.socket-close.php) | socket is a Socket instance now;<br> previously, it was a resource. |
|  | [socket\_connect](https://www.php.net/manual/en/function.socket-connect.php) | socket is a Socket instance now;<br> previously, it was a resource. |
|  | [socket\_connect](https://www.php.net/manual/en/function.socket-connect.php) | port is nullable now. |
|  | [socket\_create](https://www.php.net/manual/en/function.socket-create.php) | On success, this function returns a Socket instance now;<br> previously, a resource was returned. |
|  | [socket\_create\_listen](https://www.php.net/manual/en/function.socket-create-listen.php) | On success, this function returns a Socket instance now;<br> previously, a resource was returned. |
|  | [socket\_create\_pair](https://www.php.net/manual/en/function.socket-create-pair.php) | pair is a reference to an array of Socket instances now;<br> previously, it was a reference to an array of resources. |
|  | [socket\_export\_stream](https://www.php.net/manual/en/function.socket-export-stream.php) | socket is a Socket instance now;<br> previously, it was a resource. |
|  | [socket\_get\_option](https://www.php.net/manual/en/function.socket-get-option.php) | socket is a Socket instance now;<br> previously, it was a resource. |
|  | [socket\_getpeername](https://www.php.net/manual/en/function.socket-getpeername.php) | socket is a Socket instance now;<br> previously, it was a resource. |
|  | [socket\_getsockname](https://www.php.net/manual/en/function.socket-getsockname.php) | socket is a Socket instance now;<br> previously, it was a resource. |
|  | [socket\_import\_stream](https://www.php.net/manual/en/function.socket-import-stream.php) | On success, this function returns a Socket instance now;<br> previously, a resource was returned. |
|  | [socket\_last\_error](https://www.php.net/manual/en/function.socket-last-error.php) | socket is a Socket instance now;<br> previously, it was a resource. |
|  | [socket\_last\_error](https://www.php.net/manual/en/function.socket-last-error.php) | socket is nullable now. |
|  | [socket\_listen](https://www.php.net/manual/en/function.socket-listen.php) | socket is a Socket instance now;<br> previously, it was a resource. |
|  | [socket\_read](https://www.php.net/manual/en/function.socket-read.php) | socket is a Socket instance now;<br> previously, it was a resource. |
|  | [socket\_recv](https://www.php.net/manual/en/function.socket-recv.php) | socket is a Socket instance now;<br> previously, it was a resource. |
|  | [socket\_recvfrom](https://www.php.net/manual/en/function.socket-recvfrom.php) | socket is a Socket instance now;<br> previously, it was a resource. |
|  | [socket\_recvmsg](https://www.php.net/manual/en/function.socket-recvmsg.php) | socket is a Socket instance now;<br> previously, it was a resource. |
|  | [socket\_send](https://www.php.net/manual/en/function.socket-send.php) | socket is a Socket instance now;<br> previously, it was a resource. |
|  | [socket\_sendmsg](https://www.php.net/manual/en/function.socket-sendmsg.php) | socket is a Socket instance now;<br> previously, it was a resource. |
|  | [socket\_sendto](https://www.php.net/manual/en/function.socket-sendto.php) | socket is a Socket instance now;<br> previously, it was a resource. |
|  | [socket\_sendto](https://www.php.net/manual/en/function.socket-sendto.php) | port is nullable now. |
|  | [socket\_set\_block](https://www.php.net/manual/en/function.socket-set-block.php) | socket is a Socket instance now;<br> previously, it was a resource. |
|  | [socket\_set\_nonblock](https://www.php.net/manual/en/function.socket-set-nonblock.php) | socket is a Socket instance now;<br> previously, it was a resource. |
|  | [socket\_set\_option](https://www.php.net/manual/en/function.socket-set-option.php) | socket is a Socket instance now;<br> previously, it was a resource. |
|  | [socket\_shutdown](https://www.php.net/manual/en/function.socket-shutdown.php) | socket is a Socket instance now;<br> previously, it was a resource. |
|  | [socket\_write](https://www.php.net/manual/en/function.socket-write.php) | socket is a Socket instance now;<br> previously, it was a resource. |
|  | [socket\_write](https://www.php.net/manual/en/function.socket-write.php) | length is nullable now. |
|  | [socket\_wsaprotocol\_info\_export](https://www.php.net/manual/en/function.socket-wsaprotocol-info-export.php) | socket is a Socket instance now;<br> previously, it was a resource. |
|  | [socket\_wsaprotocol\_info\_import](https://www.php.net/manual/en/function.socket-wsaprotocol-info-import.php) | On success, this function returns a Socket instance now;<br> previously, a resource was returned. |
|  | [soundex](https://www.php.net/manual/en/function.soundex.php) | Prior to this version, calling the function with an empty string returned false<br> for no particular reason. |
|  | [spl\_autoload](https://www.php.net/manual/en/function.spl-autoload.php) | file\_extensions is now nullable. |
|  | [spl\_autoload\_extensions](https://www.php.net/manual/en/function.spl-autoload-extensions.php) | file\_extensions is now nullable. |
|  | [spl\_autoload\_functions](https://www.php.net/manual/en/function.spl-autoload-functions.php) | Return value was updated to always be an array; previously this function returned<br> false if the autoload queue wasn't activated. |
|  | [spl\_autoload\_register](https://www.php.net/manual/en/function.spl-autoload-register.php) | callback is now nullable. |
|  | [sprintf](https://www.php.net/manual/en/function.sprintf.php) | This function no longer returns false on failure. |
|  | [sprintf](https://www.php.net/manual/en/function.sprintf.php) | Throw a ValueError if the number of arguments is zero;<br> previously this function emitted a E\_WARNING instead. |
|  | [sprintf](https://www.php.net/manual/en/function.sprintf.php) | Throw a ValueError if \[width\] is less than zero or bigger than PHP\_INT\_MAX;<br> previously this function emitted a E\_WARNING instead. |
|  | [sprintf](https://www.php.net/manual/en/function.sprintf.php) | Throw a ValueError if \[precision\] is less than zero or bigger than PHP\_INT\_MAX;<br> previously this function emitted a E\_WARNING instead. |
|  | [sprintf](https://www.php.net/manual/en/function.sprintf.php) | Throw a ArgumentCountError when less arguments are given than required;<br> previously this function emitted a E\_WARNING instead. |
|  | [str\_split](https://www.php.net/manual/en/function.str-split.php) | If length is less than 1,<br> a ValueError will be thrown now;<br> previously, an error of level E\_WARNING<br> has been raised instead, and the function returned false. |
|  | [str\_word\_count](https://www.php.net/manual/en/function.str-word-count.php) | characters is nullable now. |
|  | [strcspn](https://www.php.net/manual/en/function.strcspn.php) | length is nullable now. |
|  | [stream\_context\_create](https://www.php.net/manual/en/function.stream-context-create.php) | options and params are now nullable. |
|  | [stream\_context\_get\_default](https://www.php.net/manual/en/function.stream-context-get-default.php) | options is now nullable. |
|  | [stream\_copy\_to\_stream](https://www.php.net/manual/en/function.stream-copy-to-stream.php) | length is now nullable. |
|  | [stream\_get\_contents](https://www.php.net/manual/en/function.stream-get-contents.php) | length is now nullable. |
|  | [stream\_set\_chunk\_size](https://www.php.net/manual/en/function.stream-set-chunk-size.php) | A ValueError is now thrown if<br> size is less than 1 or greater than<br> PHP\_INT\_MAX. Previously, an<br> E\_WARNING level error was emitted and false was<br> returned. |
|  | [stream\_socket\_accept](https://www.php.net/manual/en/function.stream-socket-accept.php) | timeout is now nullable. |
|  | [stream\_socket\_client](https://www.php.net/manual/en/function.stream-socket-client.php) | timeout and context are now nullable. |
|  | [stream\_socket\_enable\_crypto](https://www.php.net/manual/en/function.stream-socket-enable-crypto.php) | session\_stream is now nullable. |
|  | [stream\_socket\_server](https://www.php.net/manual/en/function.stream-socket-server.php) | context is nullable now. |
|  | [strftime](https://www.php.net/manual/en/function.strftime.php) | timestamp is nullable now. |
|  | [strip\_tags](https://www.php.net/manual/en/function.strip-tags.php) | allowed\_tags is nullable now. |
|  | [stripos](https://www.php.net/manual/en/function.stripos.php) | needle now accepts an empty string. |
|  | [stripos](https://www.php.net/manual/en/function.stripos.php) | Passing an int as needle is no longer supported. |
|  | [stristr](https://www.php.net/manual/en/function.stristr.php) | needle now accepts an empty string. |
|  | [stristr](https://www.php.net/manual/en/function.stristr.php) | Passing an int as needle is no longer supported. |
|  | [strpos](https://www.php.net/manual/en/function.strpos.php) | needle now accepts an empty string. |
|  | [strpos](https://www.php.net/manual/en/function.strpos.php) | Passing an int as needle is no longer supported. |
|  | [strrchr](https://www.php.net/manual/en/function.strrchr.php) | needle now accepts an empty string. |
|  | [strrchr](https://www.php.net/manual/en/function.strrchr.php) | Passing an int as needle is no longer supported. |
|  | [strripos](https://www.php.net/manual/en/function.strripos.php) | needle now accepts an empty string. |
|  | [strripos](https://www.php.net/manual/en/function.strripos.php) | Passing an int as needle is no longer supported. |
|  | [strrpos](https://www.php.net/manual/en/function.strrpos.php) | needle now accepts an empty string. |
|  | [strrpos](https://www.php.net/manual/en/function.strrpos.php) | Passing an int as needle is no longer supported. |
|  | [strspn](https://www.php.net/manual/en/function.strspn.php) | length is nullable now. |
|  | [strstr](https://www.php.net/manual/en/function.strstr.php) | needle now accepts an empty string. |
|  | [strstr](https://www.php.net/manual/en/function.strstr.php) | Passing an int as needle is no longer supported. |
|  | [strtotime](https://www.php.net/manual/en/function.strtotime.php) | baseTimestamp is nullable now. |
|  | [substr](https://www.php.net/manual/en/function.substr.php) | length is nullable now.<br> When length is explicitly set to null,<br> the function returns a substring finishing at the end of the string, when it previously returned an empty string. |
|  | [substr](https://www.php.net/manual/en/function.substr.php) | The function returns an empty string where it previously returned false. |
|  | [substr\_compare](https://www.php.net/manual/en/function.substr-compare.php) | length is nullable now. |
|  | [substr\_count](https://www.php.net/manual/en/function.substr-count.php) | length is nullable now. |
|  | [substr\_replace](https://www.php.net/manual/en/function.substr-replace.php) | length is nullable now. |
|  | [touch](https://www.php.net/manual/en/function.touch.php) | mtime and atime<br> are now nullable. |
|  | [trigger\_error](https://www.php.net/manual/en/function.trigger-error.php) | The function now throws a ValueError if an invalid<br> error\_level is specified. Previously, it returned false. |
|  | [uasort](https://www.php.net/manual/en/function.uasort.php) | If callback expects a parameter to be passed<br> by reference, this function will now emit an E\_WARNING. |
|  | [uksort](https://www.php.net/manual/en/function.uksort.php) | If callback expects a parameter to be passed<br> by reference, this function will now emit an E\_WARNING. |
|  | [umask](https://www.php.net/manual/en/function.umask.php) | mask is nullable now. |
|  | [unixtojd](https://www.php.net/manual/en/function.unixtojd.php) | timestamp is nullable now. |
|  | [usort](https://www.php.net/manual/en/function.usort.php) | If callback expects a parameter to be passed<br> by reference, this function will now emit an E\_WARNING. |
|  | [vfprintf](https://www.php.net/manual/en/function.vfprintf.php) | This function no longer returns false on failure. |
|  | [vfprintf](https://www.php.net/manual/en/function.vfprintf.php) | Throw a ValueError if the number of arguments is zero;<br> previously this function emitted a E\_WARNING instead. |
|  | [vfprintf](https://www.php.net/manual/en/function.vfprintf.php) | Throw a ValueError if \[width\] is less than zero or bigger than PHP\_INT\_MAX;<br> previously this function emitted a E\_WARNING instead. |
|  | [vfprintf](https://www.php.net/manual/en/function.vfprintf.php) | Throw a ValueError if \[precision\] is less than zero or bigger than PHP\_INT\_MAX;<br> previously this function emitted a E\_WARNING instead. |
|  | [vfprintf](https://www.php.net/manual/en/function.vfprintf.php) | Throw a ValueError when less arguments are given than required;<br> previously this function emitted a E\_WARNING instead. |
|  | [vprintf](https://www.php.net/manual/en/function.vprintf.php) | This function no longer returns false on failure. |
|  | [vprintf](https://www.php.net/manual/en/function.vprintf.php) | Throw a ValueError if the number of arguments is zero;<br> previously this function emitted a E\_WARNING instead. |
|  | [vprintf](https://www.php.net/manual/en/function.vprintf.php) | Throw a ValueError if \[width\] is less than zero or bigger than PHP\_INT\_MAX;<br> previously this function emitted a E\_WARNING instead. |
|  | [vprintf](https://www.php.net/manual/en/function.vprintf.php) | Throw a ValueError if \[precision\] is less than zero or bigger than PHP\_INT\_MAX;<br> previously this function emitted a E\_WARNING instead. |
|  | [vprintf](https://www.php.net/manual/en/function.vprintf.php) | Throw a ValueError when less arguments are given than required;<br> previously this function emitted a E\_WARNING instead. |
|  | [vsprintf](https://www.php.net/manual/en/function.vsprintf.php) | This function no longer returns false on failure. |
|  | [vsprintf](https://www.php.net/manual/en/function.vsprintf.php) | Throw a ValueError if the number of arguments is zero;<br> previously this function emitted a E\_WARNING instead. |
|  | [vsprintf](https://www.php.net/manual/en/function.vsprintf.php) | Throw a ValueError if \[width\] is less than zero or bigger than PHP\_INT\_MAX;<br> previously this function emitted a E\_WARNING instead. |
|  | [vsprintf](https://www.php.net/manual/en/function.vsprintf.php) | Throw a ValueError if \[precision\] is less than zero or bigger than PHP\_INT\_MAX;<br> previously this function emitted a E\_WARNING instead. |
|  | [vsprintf](https://www.php.net/manual/en/function.vsprintf.php) | Throw a ValueError when less arguments are given than required;<br> previously this function emitted a E\_WARNING instead. |
|  | [wordwrap](https://www.php.net/manual/en/function.wordwrap.php) | If break is empty string,<br> a ValueError is thrown;<br> previously in this case it emitted an E\_WARNING and returned false. |
|  | [xml\_get\_current\_byte\_index](https://www.php.net/manual/en/function.xml-get-current-byte-index.php) | parser expects an XMLParser<br> instance now; previously, a valid xml resource was expected. |
|  | [xml\_get\_current\_column\_number](https://www.php.net/manual/en/function.xml-get-current-column-number.php) | parser expects an XMLParser<br> instance now; previously, a valid xml resource was expected. |
|  | [xml\_get\_current\_line\_number](https://www.php.net/manual/en/function.xml-get-current-line-number.php) | parser expects an XMLParser<br> instance now; previously, a valid xml resource was expected. |
|  | [xml\_get\_error\_code](https://www.php.net/manual/en/function.xml-get-error-code.php) | parser expects an XMLParser<br> instance now; previously, a valid xml resource was expected. |
|  | [xml\_parse](https://www.php.net/manual/en/function.xml-parse.php) | parser expects an XMLParser<br> instance now; previously, a valid xml resource was expected. |
|  | [xml\_parse\_into\_struct](https://www.php.net/manual/en/function.xml-parse-into-struct.php) | parser expects an XMLParser<br> instance now; previously, a valid xml resource was expected. |
|  | [xml\_parser\_create](https://www.php.net/manual/en/function.xml-parser-create.php) | This function returns an XMLParser instance now;<br> previously, a resource was returned, or false on failure. |
|  | [xml\_parser\_create](https://www.php.net/manual/en/function.xml-parser-create.php) | encoding is nullable now. |
|  | [xml\_parser\_create\_ns](https://www.php.net/manual/en/function.xml-parser-create-ns.php) | This function returns an XMLParser instance now;<br> previously, a resource was returned, or false on failure. |
|  | [xml\_parser\_create\_ns](https://www.php.net/manual/en/function.xml-parser-create-ns.php) | encoding is nullable now. |
|  | [xml\_parser\_free](https://www.php.net/manual/en/function.xml-parser-free.php) | parser expects an XMLParser<br> instance now; previously, a valid xml resource was expected. |
|  | [xml\_parser\_get\_option](https://www.php.net/manual/en/function.xml-parser-get-option.php) | parser expects an XMLParser<br> instance now; previously, a valid xml resource was expected. |
|  | [xml\_parser\_get\_option](https://www.php.net/manual/en/function.xml-parser-get-option.php) | A ValueError is now thrown if<br> option is invalid. |
|  | [xml\_parser\_set\_option](https://www.php.net/manual/en/function.xml-parser-set-option.php) | parser expects an XMLParser<br> instance now; previously, a valid xml resource was expected. |
|  | [xml\_parser\_set\_option](https://www.php.net/manual/en/function.xml-parser-set-option.php) | A ValueError is now thrown if<br> option is invalid. |
|  | [xml\_set\_character\_data\_handler](https://www.php.net/manual/en/function.xml-set-character-data-handler.php) | parser expects an XMLParser<br> instance now; previously, a valid xml resource was expected. |
|  | [xml\_set\_default\_handler](https://www.php.net/manual/en/function.xml-set-default-handler.php) | parser expects an XMLParser<br> instance now; previously, a valid xml resource was expected. |
|  | [xml\_set\_element\_handler](https://www.php.net/manual/en/function.xml-set-element-handler.php) | parser expects an XMLParser<br> instance now; previously, a valid xml resource was expected. |
|  | [xml\_set\_end\_namespace\_decl\_handler](https://www.php.net/manual/en/function.xml-set-end-namespace-decl-handler.php) | parser expects an XMLParser<br> instance now; previously, a valid xml resource was expected. |
|  | [xml\_set\_external\_entity\_ref\_handler](https://www.php.net/manual/en/function.xml-set-external-entity-ref-handler.php) | parser expects an XMLParser<br> instance now; previously, a valid xml resource was expected. |
|  | [xml\_set\_notation\_decl\_handler](https://www.php.net/manual/en/function.xml-set-notation-decl-handler.php) | parser expects an XMLParser<br> instance now; previously, a valid xml resource was expected. |
|  | [xml\_set\_object](https://www.php.net/manual/en/function.xml-set-object.php) | parser expects an XMLParser<br> instance now; previously, a valid xml resource was expected. |
|  | [xml\_set\_processing\_instruction\_handler](https://www.php.net/manual/en/function.xml-set-processing-instruction-handler.php) | parser expects an XMLParser<br> instance now; previously, a valid xml resource was expected. |
|  | [xml\_set\_start\_namespace\_decl\_handler](https://www.php.net/manual/en/function.xml-set-start-namespace-decl-handler.php) | parser expects an XMLParser<br> instance now; previously, a valid xml resource was expected. |
|  | [xml\_set\_unparsed\_entity\_decl\_handler](https://www.php.net/manual/en/function.xml-set-unparsed-entity-decl-handler.php) | parser expects an XMLParser<br> instance now; previously, a valid xml resource was expected. |
|  | [zip\_close](https://www.php.net/manual/en/function.zip-close.php) | This function is deprecated in favor of the Object API,<br> see ZipArchive::close. |
|  | [zip\_entry\_close](https://www.php.net/manual/en/function.zip-entry-close.php) | This function is deprecated in favor of the Object API. |
|  | [zip\_entry\_compressedsize](https://www.php.net/manual/en/function.zip-entry-compressedsize.php) | This function is deprecated in favor of the Object API,<br> see ZipArchive::statIndex. |
|  | [zip\_entry\_compressionmethod](https://www.php.net/manual/en/function.zip-entry-compressionmethod.php) | This function is deprecated in favor of the Object API,<br> see ZipArchive::statIndex. |
|  | [zip\_entry\_filesize](https://www.php.net/manual/en/function.zip-entry-filesize.php) | This function is deprecated in favor of the Object API,<br> see ZipArchive::statIndex. |
|  | [zip\_entry\_name](https://www.php.net/manual/en/function.zip-entry-name.php) | This function is deprecated in favor of the Object API,<br> see ZipArchive::statIndex. |
|  | [zip\_entry\_open](https://www.php.net/manual/en/function.zip-entry-open.php) | This function is deprecated in favor of the Object API. |
|  | [zip\_entry\_read](https://www.php.net/manual/en/function.zip-entry-read.php) | This function is deprecated in favor of the Object API,<br> see ZipArchive::getFromIndex. |
|  | [zip\_open](https://www.php.net/manual/en/function.zip-open.php) | This function is deprecated in favor of the Object API,<br> see ZipArchive::open. |
|  | [zip\_read](https://www.php.net/manual/en/function.zip-read.php) | This function is deprecated in favor of the Object API,<br> see ZipArchive::statIndex. |
|  | [GlobIterator::\_\_construct](https://www.php.net/manual/en/globiterator.construct.php) | Now throws a ValueError if<br> directory is an empty string;<br> previously it threw a RuntimeException. |
|  | [IntlCalendar::setMinimalDaysInFirstWeek](https://www.php.net/manual/en/intlcalendar.setminimaldaysinfirstweek.php) | A ValueError is now thrown on invalid input. Previously, false was returned. |
|  | [IntlTimeZone::getIDForWindowsID](https://www.php.net/manual/en/intltimezone.getidforwindowsid.php) | region is now nullable. |
|  | [LimitIterator::\_\_construct](https://www.php.net/manual/en/limititerator.construct.php) | Now throws a ValueError if<br> offset is less than 0;<br> previously it threw a RuntimeException. |
|  | [LimitIterator::\_\_construct](https://www.php.net/manual/en/limititerator.construct.php) | Now throws a ValueError if<br> limit is less than -1;<br> previously it threw a RuntimeException. |
|  | [Locale::getDisplayLanguage](https://www.php.net/manual/en/locale.getdisplaylanguage.php) | displayLocale is nullable now. |
|  | [Locale::getDisplayName](https://www.php.net/manual/en/locale.getdisplayname.php) | displayLocale is nullable now. |
|  | [Locale::getDisplayRegion](https://www.php.net/manual/en/locale.getdisplayregion.php) | displayLocale is nullable now. |
|  | [Locale::getDisplayScript](https://www.php.net/manual/en/locale.getdisplayscript.php) | displayLocale is nullable now. |
|  | [Locale::getDisplayVariant](https://www.php.net/manual/en/locale.getdisplayvariant.php) | displayLocale is nullable now. |
|  | [mysqli\_result::fetch\_object](https://www.php.net/manual/en/mysqli-result.fetch-object.php) | constructor\_args now accepts \[\] for constructors with 0 parameters;<br> previously an exception was thrown. |
|  | [mysqli\_result::field\_seek](https://www.php.net/manual/en/mysqli-result.field-seek.php) | This function now always returns true. Previously it returned false on failure. |
|  | [mysqli\_stmt::close](https://www.php.net/manual/en/mysqli-stmt.close.php) | This function now always returns true. Previously it returned false on failure. |
|  | [mysqli\_stmt::\_\_construct](https://www.php.net/manual/en/mysqli-stmt.construct.php) | query is now nullable. |
|  | [mysqli::begin\_transaction](https://www.php.net/manual/en/mysqli.begin-transaction.php) | name is now nullable. |
|  | [mysqli::close](https://www.php.net/manual/en/mysqli.close.php) | This function now always returns true. Previously it returned false on failure. |
|  | [mysqli::commit](https://www.php.net/manual/en/mysqli.commit.php) | name is now nullable. |
|  | [mysqli::debug](https://www.php.net/manual/en/mysqli.debug.php) | This function now always returns true. Previously it returned false on failure. |
|  | [mysqli::rollback](https://www.php.net/manual/en/mysqli.rollback.php) | name is now nullable. |
|  | [NumberFormatter::create](https://www.php.net/manual/en/numberformatter.create.php) | pattern is nullable now. |
|  | [PDOStatement::fetchAll](https://www.php.net/manual/en/pdostatement.fetchall.php) | This method always returns an array now, while previously false may have<br> been returned on failure. |
|  | [Phar::addFile](https://www.php.net/manual/en/phar.addfile.php) | localName is now nullable. |
|  | [Phar::buildFromIterator](https://www.php.net/manual/en/phar.buildfromiterator.php) | baseDirectory is now nullable. |
|  | [Phar::compress](https://www.php.net/manual/en/phar.compress.php) | extension is now nullable. |
|  | [Phar::convertToData](https://www.php.net/manual/en/phar.converttodata.php) | format, compression, and extension are now nullable. |
|  | [Phar::convertToExecutable](https://www.php.net/manual/en/phar.converttoexecutable.php) | format, compression, and extension are now nullable. |
|  | [Phar::createDefaultStub](https://www.php.net/manual/en/phar.createdefaultstub.php) | index and webIndex are now nullable. |
|  | [Phar::decompress](https://www.php.net/manual/en/phar.decompress.php) | extension is now nullable. |
|  | [Phar::getMetadata](https://www.php.net/manual/en/phar.getmetadata.php) | The parameter unserializeOptions has been added. |
|  | [Phar::setDefaultStub](https://www.php.net/manual/en/phar.setdefaultstub.php) | webIndex is nullable now. |
|  | [Phar::setSignatureAlgorithm](https://www.php.net/manual/en/phar.setsignaturealgorithm.php) | privateKey is now nullable. |
|  | [Phar::webPhar](https://www.php.net/manual/en/phar.webphar.php) | fileNotFoundScript and rewrite are nullable now. |
|  | [PharData::addFile](https://www.php.net/manual/en/phardata.addfile.php) | localName is now nullable. |
|  | [PharData::buildFromIterator](https://www.php.net/manual/en/phardata.buildfromiterator.php) | baseDirectory is now nullable. |
|  | [PharData::compress](https://www.php.net/manual/en/phardata.compress.php) | extension is now nullable. |
|  | [PharData::convertToData](https://www.php.net/manual/en/phardata.converttodata.php) | format, compression, and extension are now nullable. |
|  | [PharData::convertToExecutable](https://www.php.net/manual/en/phardata.converttoexecutable.php) | format, compression, and localName are now nullable. |
|  | [PharData::decompress](https://www.php.net/manual/en/phardata.decompress.php) | extension is now nullable. |
|  | [PharData::setDefaultStub](https://www.php.net/manual/en/phardata.setdefaultstub.php) | webIndex is nullable now. |
|  | [PharData::setSignatureAlgorithm](https://www.php.net/manual/en/phardata.setsignaturealgorithm.php) | privateKey is now nullable. |
|  | [PharFileInfo::getMetadata](https://www.php.net/manual/en/pharfileinfo.getmetadata.php) | The parameter unserializeOptions has been added. |
|  | [PharFileInfo::isCompressed](https://www.php.net/manual/en/pharfileinfo.iscompressed.php) | compression is now nullable. |
|  | [RecursiveDirectoryIterator::\_\_construct](https://www.php.net/manual/en/recursivedirectoryiterator.construct.php) | Now throws a ValueError if<br> directory is an empty string;<br> previously it threw a RuntimeException. |
|  | [RecursiveIteratorIterator::getSubIterator](https://www.php.net/manual/en/recursiveiteratoriterator.getsubiterator.php) | level is now nullable. |
|  | [ReflectionClass::getConstants](https://www.php.net/manual/en/reflectionclass.getconstants.php) | filter has been added. |
|  | [ReflectionClass::getReflectionConstants](https://www.php.net/manual/en/reflectionclass.getreflectionconstants.php) | filter has been added. |
|  | [ReflectionFunction::invokeArgs](https://www.php.net/manual/en/reflectionfunction.invokeargs.php) | args keys will now be interpreted as parameter names, instead of being silently ignored. |
|  | [ReflectionFunction::isDisabled](https://www.php.net/manual/en/reflectionfunction.isdisabled.php) | This function has been deprecated, as ReflectionFunction<br> can no longer be constructed for disabled functions. |
|  | [ReflectionMethod::export](https://www.php.net/manual/en/reflectionmethod.export.php) | Removed this function. |
|  | [ReflectionMethod::getClosure](https://www.php.net/manual/en/reflectionmethod.getclosure.php) | object is now nullable. |
|  | [ReflectionMethod::invokeArgs](https://www.php.net/manual/en/reflectionmethod.invokeargs.php) | args keys will now be interpreted as parameter names, instead of being silently ignored. |
|  | [ReflectionParameter::getClass](https://www.php.net/manual/en/reflectionparameter.getclass.php) | This function has been deprecated in favor of<br> ReflectionParameter::getType instead. |
|  | [ReflectionParameter::getDefaultValue](https://www.php.net/manual/en/reflectionparameter.getdefaultvalue.php) | This method now allows getting the default value of parameters of built-in functions and<br> built-in class methods. Previously, a ReflectionException was thrown. |
|  | [ReflectionParameter::getDefaultValueConstantName](https://www.php.net/manual/en/reflectionparameter.getdefaultvalueconstantname.php) | This method now allows getting the default values' constant names of built-in functions and<br> built-in class methods. Previously, a ReflectionException was thrown. |
|  | [ReflectionParameter::isArray](https://www.php.net/manual/en/reflectionparameter.isarray.php) | This function has been deprecated in favor of<br> ReflectionParameter::getType instead. |
|  | [ReflectionParameter::isCallable](https://www.php.net/manual/en/reflectionparameter.iscallable.php) | This function has been deprecated in favor of<br> ReflectionParameter::getType instead. |
|  | [ReflectionProperty::getValue](https://www.php.net/manual/en/reflectionproperty.getvalue.php) | object is nullable now. |
|  | [ReflectionProperty::isInitialized](https://www.php.net/manual/en/reflectionproperty.isinitialized.php) | object is nullable now. |
|  | [ReflectionType::\_\_toString](https://www.php.net/manual/en/reflectiontype.tostring.php) | ReflectionType::\_\_toString has been undeprecated. |
|  | [Reflector::export](https://www.php.net/manual/en/reflector.export.php) | Removed this function. |
|  | [SimpleXMLElement::asXML](https://www.php.net/manual/en/simplexmlelement.asxml.php) | filename is nullable now. |
|  | [SoapClient::\_\_doRequest](https://www.php.net/manual/en/soapclient.dorequest.php) | The type of oneWay is bool now; formerly it was int. |
|  | [SoapClient::\_\_setCookie](https://www.php.net/manual/en/soapclient.setcookie.php) | value is now nullable. |
|  | [SoapServer::handle](https://www.php.net/manual/en/soapserver.handle.php) | request is now nullable. |
|  | [SplFileInfo::getFileInfo](https://www.php.net/manual/en/splfileinfo.getfileinfo.php) | class is now nullable. |
|  | [SplFileInfo::getPathInfo](https://www.php.net/manual/en/splfileinfo.getpathinfo.php) | class is now nullable. |
|  | [SplFileInfo::openFile](https://www.php.net/manual/en/splfileinfo.openfile.php) | context is now nullable. |
|  | [SplFixedArray::\_\_construct](https://www.php.net/manual/en/splfixedarray.construct.php) | Now throws a ValueError if<br> size is a negative;<br> previously it threw a InvalidArgumentException. |
|  | [tidy::\_\_construct](https://www.php.net/manual/en/tidy.construct.php) | filename, config,<br> encoding and useIncludePath are nullable now. |
|  | [tidy::parseFile](https://www.php.net/manual/en/tidy.parsefile.php) | config and encoding are nullable now. |
|  | [tidy::parseString](https://www.php.net/manual/en/tidy.parsestring.php) | config and encoding are nullable now. |
|  | [tidy::repairFile](https://www.php.net/manual/en/tidy.repairfile.php) | tidy::repairFile is a static method now. |
|  | [tidy::repairFile](https://www.php.net/manual/en/tidy.repairfile.php) | config and encoding are nullable now. |
|  | [tidy::repairString](https://www.php.net/manual/en/tidy.repairstring.php) | tidy::repairString is a static method now. |
|  | [tidy::repairString](https://www.php.net/manual/en/tidy.repairstring.php) | config and encoding are nullable now. |
|  | [tidy::repairString](https://www.php.net/manual/en/tidy.repairstring.php) | This function no longer accepts the useIncludePath parameter. |
|  | [XMLReader::getAttribute](https://www.php.net/manual/en/xmlreader.getattribute.php) | This function can no longer return false. |
|  | [XMLReader::getAttributeNs](https://www.php.net/manual/en/xmlreader.getattributens.php) | This function can no longer return false. |
|  | [XMLReader::lookupNamespace](https://www.php.net/manual/en/xmlreader.lookupnamespace.php) | This function can no longer return false. |
|  | [XMLReader::next](https://www.php.net/manual/en/xmlreader.next.php) | name is nullable now. |
|  | [XMLReader::open](https://www.php.net/manual/en/xmlreader.open.php) | XMLReader::open is now declared as static method,<br> but can still be called on an XMLReader instance. |
|  | [XMLReader::XML](https://www.php.net/manual/en/xmlreader.xml.php) | XMLReader::XML is now declared as static method,<br> but can still be called on an XMLReader instance. |
|  | [XMLWriter::endAttribute](https://www.php.net/manual/en/xmlwriter.endattribute.php) | writer expects an XMLWriter<br> instance now; previously, a resource was expected. |
|  | [XMLWriter::endCdata](https://www.php.net/manual/en/xmlwriter.endcdata.php) | writer expects an XMLWriter<br> instance now; previously, a resource was expected. |
|  | [XMLWriter::endComment](https://www.php.net/manual/en/xmlwriter.endcomment.php) | writer expects an XMLWriter<br> instance now; previously, a resource was expected. |
|  | [XMLWriter::endDocument](https://www.php.net/manual/en/xmlwriter.enddocument.php) | writer expects an XMLWriter<br> instance now; previously, a resource was expected. |
|  | [XMLWriter::endDtd](https://www.php.net/manual/en/xmlwriter.enddtd.php) | writer expects an XMLWriter<br> instance now; previously, a resource was expected. |
|  | [XMLWriter::endDtdAttlist](https://www.php.net/manual/en/xmlwriter.enddtdattlist.php) | writer expects an XMLWriter<br> instance now; previously, a resource was expected. |
|  | [XMLWriter::endDtdElement](https://www.php.net/manual/en/xmlwriter.enddtdelement.php) | writer expects an XMLWriter<br> instance now; previously, a resource was expected. |
|  | [XMLWriter::endDtdEntity](https://www.php.net/manual/en/xmlwriter.enddtdentity.php) | writer expects an XMLWriter<br> instance now; previously, a resource was expected. |
|  | [XMLWriter::endElement](https://www.php.net/manual/en/xmlwriter.endelement.php) | writer expects an XMLWriter<br> instance now; previously, a resource was expected. |
|  | [XMLWriter::endPi](https://www.php.net/manual/en/xmlwriter.endpi.php) | writer expects an XMLWriter<br> instance now; previously, a resource was expected. |
|  | [XMLWriter::flush](https://www.php.net/manual/en/xmlwriter.flush.php) | writer expects an XMLWriter<br> instance now; previously, a resource was expected. |
|  | [XMLWriter::flush](https://www.php.net/manual/en/xmlwriter.flush.php) | This function can no longer return false. |
|  | [XMLWriter::fullEndElement](https://www.php.net/manual/en/xmlwriter.fullendelement.php) | writer expects an XMLWriter<br> instance now; previously, a resource was expected. |
|  | [XMLWriter::openMemory](https://www.php.net/manual/en/xmlwriter.openmemory.php) | This function returns now an XMLWriter instance on success.<br> Previouly, a resource has been returned in this case. |
|  | [XMLWriter::openUri](https://www.php.net/manual/en/xmlwriter.openuri.php) | This function returns now an XMLWriter instance on success.<br> Previouly, a resource has been returned in this case. |
|  | [XMLWriter::outputMemory](https://www.php.net/manual/en/xmlwriter.outputmemory.php) | writer expects an XMLWriter<br> instance now; previously, a resource was expected. |
|  | [XMLWriter::setIndent](https://www.php.net/manual/en/xmlwriter.setindent.php) | writer expects an XMLWriter<br> instance now; previously, a resource was expected. |
|  | [XMLWriter::setIndentString](https://www.php.net/manual/en/xmlwriter.setindentstring.php) | writer expects an XMLWriter<br> instance now; previously, a resource was expected. |
|  | [XMLWriter::startAttribute](https://www.php.net/manual/en/xmlwriter.startattribute.php) | writer expects an XMLWriter<br> instance now; previously, a resource was expected. |
|  | [XMLWriter::startAttributeNs](https://www.php.net/manual/en/xmlwriter.startattributens.php) | writer expects an XMLWriter<br> instance now; previously, a resource was expected. |
|  | [XMLWriter::startAttributeNs](https://www.php.net/manual/en/xmlwriter.startattributens.php) | prefix is nullable now. |
|  | [XMLWriter::startCdata](https://www.php.net/manual/en/xmlwriter.startcdata.php) | writer expects an XMLWriter<br> instance now; previously, a resource was expected. |
|  | [XMLWriter::startComment](https://www.php.net/manual/en/xmlwriter.startcomment.php) | writer expects an XMLWriter<br> instance now; previously, a resource was expected. |
|  | [XMLWriter::startDocument](https://www.php.net/manual/en/xmlwriter.startdocument.php) | writer expects an XMLWriter<br> instance now; previously, a resource was expected. |
|  | [XMLWriter::startDtd](https://www.php.net/manual/en/xmlwriter.startdtd.php) | writer expects an XMLWriter<br> instance now; previously, a resource was expected. |
|  | [XMLWriter::startDtdAttlist](https://www.php.net/manual/en/xmlwriter.startdtdattlist.php) | writer expects an XMLWriter<br> instance now; previously, a resource was expected. |
|  | [XMLWriter::startDtdElement](https://www.php.net/manual/en/xmlwriter.startdtdelement.php) | writer expects an XMLWriter<br> instance now; previously, a resource was expected. |
|  | [XMLWriter::startDtdEntity](https://www.php.net/manual/en/xmlwriter.startdtdentity.php) | writer expects an XMLWriter<br> instance now; previously, a resource was expected. |
|  | [XMLWriter::startElement](https://www.php.net/manual/en/xmlwriter.startelement.php) | writer expects an XMLWriter<br> instance now; previously, a resource was expected. |
|  | [XMLWriter::startElementNs](https://www.php.net/manual/en/xmlwriter.startelementns.php) | writer expects an XMLWriter<br> instance now; previously, a resource was expected. |
|  | [XMLWriter::startPi](https://www.php.net/manual/en/xmlwriter.startpi.php) | writer expects an XMLWriter<br> instance now; previously, a resource was expected. |
|  | [XMLWriter::text](https://www.php.net/manual/en/xmlwriter.text.php) | writer expects an XMLWriter<br> instance now; previously, a resource was expected. |
|  | [XMLWriter::writeAttribute](https://www.php.net/manual/en/xmlwriter.writeattribute.php) | writer expects an XMLWriter<br> instance now; previously, a resource was expected. |
|  | [XMLWriter::writeAttributeNs](https://www.php.net/manual/en/xmlwriter.writeattributens.php) | writer expects an XMLWriter<br> instance now; previously, a resource was expected. |
|  | [XMLWriter::writeCdata](https://www.php.net/manual/en/xmlwriter.writecdata.php) | writer expects an XMLWriter<br> instance now; previously, a resource was expected. |
|  | [XMLWriter::writeComment](https://www.php.net/manual/en/xmlwriter.writecomment.php) | writer expects an XMLWriter<br> instance now; previously, a resource was expected. |
|  | [XMLWriter::writeDtd](https://www.php.net/manual/en/xmlwriter.writedtd.php) | writer expects an XMLWriter<br> instance now; previously, a resource was expected. |
|  | [XMLWriter::writeDtdAttlist](https://www.php.net/manual/en/xmlwriter.writedtdattlist.php) | writer expects an XMLWriter<br> instance now; previously, a resource was expected. |
|  | [XMLWriter::writeDtdElement](https://www.php.net/manual/en/xmlwriter.writedtdelement.php) | writer expects an XMLWriter<br> instance now; previously, a resource was expected. |
|  | [XMLWriter::writeDtdEntity](https://www.php.net/manual/en/xmlwriter.writedtdentity.php) | writer expects an XMLWriter<br> instance now; previously, a resource was expected. |
|  | [XMLWriter::writeDtdEntity](https://www.php.net/manual/en/xmlwriter.writedtdentity.php) | publicId, systemId and<br> notationData are nullable now. |
|  | [XMLWriter::writeElement](https://www.php.net/manual/en/xmlwriter.writeelement.php) | writer expects an XMLWriter<br> instance now; previously, a resource was expected. |
|  | [XMLWriter::writeElementNs](https://www.php.net/manual/en/xmlwriter.writeelementns.php) | writer expects an XMLWriter<br> instance now; previously, a resource was expected. |
|  | [XMLWriter::writePi](https://www.php.net/manual/en/xmlwriter.writepi.php) | writer expects an XMLWriter<br> instance now; previously, a resource was expected. |
|  | [XMLWriter::writeRaw](https://www.php.net/manual/en/xmlwriter.writeraw.php) | writer expects an XMLWriter<br> instance now; previously, a resource was expected. |
|  | [ZipArchive::addEmptyDir](https://www.php.net/manual/en/ziparchive.addemptydir.php) | flags was added. |
|  | [ZipArchive::addFile](https://www.php.net/manual/en/ziparchive.addfile.php) | flags was added. |
|  | [ZipArchive::addFromString](https://www.php.net/manual/en/ziparchive.addfromstring.php) | flags was added. |
|  | [ZipArchive::addGlob](https://www.php.net/manual/en/ziparchive.addglob.php) | "flags" in options was added. |
|  | [ZipArchive::addGlob](https://www.php.net/manual/en/ziparchive.addglob.php) | "comp\_method", "comp\_flags",<br> "enc\_method" and "enc\_password" in<br> options were added. |
|  | [ZipArchive::getStatusString](https://www.php.net/manual/en/ziparchive.getstatusstring.php) | This method can be called on closed archive. |
|  | [ZipArchive::getStatusString](https://www.php.net/manual/en/ziparchive.getstatusstring.php) | This method no longer returns false on failure. |
|  | [ZipArchive::setEncryptionIndex](https://www.php.net/manual/en/ziparchive.setencryptionindex.php) | password is now nullable. |
|  | [ZipArchive::setEncryptionName](https://www.php.net/manual/en/ziparchive.setencryptionname.php) | password is now nullable. |
| 7.4.12 | [jdtounix](https://www.php.net/manual/en/function.jdtounix.php) | The upper limit of julian\_day has been extended. Previously,<br> it was 2465342 regardless of the architecture. |
|  | [tidyNode::isHtml](https://www.php.net/manual/en/tidynode.ishtml.php) | This function has been fixed to have reasonable behavior. Previously,<br> almost any node was reported as being an HTML node. |
| 7.4.4 | [proc\_open](https://www.php.net/manual/en/function.proc-open.php) | Added the create\_new\_console option to the<br> options parameter. |
| 7.4.3 | [curl\_setopt](https://www.php.net/manual/en/function.curl-setopt.php) | Introduced CURLOPT\_HTTP09\_ALLOWED. |
| 7.4.2 | [dba\_open](https://www.php.net/manual/en/function.dba-open.php) | The lmdb driver now supports an additional map\_size<br> parameter. |
|  | [dba\_popen](https://www.php.net/manual/en/function.dba-popen.php) | The lmdb driver now supports an additional map\_size<br> parameter. |
| 7.4.0 | [DatePeriod::\_\_construct](https://www.php.net/manual/en/dateperiod.construct.php) | recurrences must be greater than 0 now. |
|  | [array\_key\_exists](https://www.php.net/manual/en/function.array-key-exists.php) | Passing an object to the array parameter has been deprecated. Use property\_exists instead. |
|  | [array\_merge](https://www.php.net/manual/en/function.array-merge.php) | This function can now be called without any parameter.<br> Formerly, at least one parameter has been required. |
|  | [array\_merge\_recursive](https://www.php.net/manual/en/function.array-merge-recursive.php) | This function can now be called without any parameter.<br> Formerly, at least one parameter has been required. |
|  | [base\_convert](https://www.php.net/manual/en/function.base-convert.php) | Passing invalid characters will now generate a deprecation notice.<br> The result will still be computed as if the invalid characters did not exist. |
|  | [bindec](https://www.php.net/manual/en/function.bindec.php) | Passing invalid characters will now generate a deprecation notice.<br> The result will still be computed as if the invalid characters did not exist. |
|  | [chr](https://www.php.net/manual/en/function.chr.php) | The function no longer silently accepts unsupported codepoints,<br> and casts these to 0. |
|  | [convert\_cyr\_string](https://www.php.net/manual/en/function.convert-cyr-string.php) | Deprecated this function. |
|  | [curl\_version](https://www.php.net/manual/en/function.curl-version.php) | The optional age parameter has been deprecated;<br> if a value is passed, it is ignored. |
|  | [current](https://www.php.net/manual/en/function.current.php) | Instances of SPL classes are now treated like empty objects that have no properties instead of calling the Iterator method with the same name as this function. |
|  | [end](https://www.php.net/manual/en/function.end.php) | Instances of SPL classes are now treated like empty objects that have no properties instead of calling the Iterator method with the same name as this function. |
|  | [fgetcsv](https://www.php.net/manual/en/function.fgetcsv.php) | The escape parameter now also accepts an empty<br> string to disable the proprietary escape mechanism. |
|  | [fputcsv](https://www.php.net/manual/en/function.fputcsv.php) | The escape parameter now also accepts an empty<br> string to disable the proprietary escape mechanism. |
|  | [get\_declared\_classes](https://www.php.net/manual/en/function.get-declared-classes.php) | Previously get\_declared\_classes always returned parent classes before<br> child classes. This is no longer the case. No particular order is guaranteed<br> for the get\_declared\_classes return value. |
|  | [get\_magic\_quotes\_gpc](https://www.php.net/manual/en/function.get-magic-quotes-gpc.php) | Deprecated this function. |
|  | [get\_magic\_quotes\_runtime](https://www.php.net/manual/en/function.get-magic-quotes-runtime.php) | Deprecated this function. |
|  | [gzread](https://www.php.net/manual/en/function.gzread.php) | This functions returns false on failure now; previously 0 was returned. |
|  | [gzwrite](https://www.php.net/manual/en/function.gzwrite.php) | This functions returns false on failure now; previously 0 was returned. |
|  | [hash\_algos](https://www.php.net/manual/en/function.hash-algos.php) | Support for crc32c has been added. |
|  | [hebrevc](https://www.php.net/manual/en/function.hebrevc.php) | Deprecated this function. |
|  | [hexdec](https://www.php.net/manual/en/function.hexdec.php) | Passing invalid characters will now generate a deprecation notice.<br> The result will still be computed as if the invalid characters did not exist. |
|  | [idn\_to\_ascii](https://www.php.net/manual/en/function.idn-to-ascii.php) | The default value of variant is now<br> INTL\_IDNA\_VARIANT\_UTS46 instead of the deprecated<br> INTL\_IDNA\_VARIANT\_2003. |
|  | [idn\_to\_utf8](https://www.php.net/manual/en/function.idn-to-utf8.php) | The default value of variant is now<br> INTL\_IDNA\_VARIANT\_UTS46 instead of the deprecated<br> INTL\_IDNA\_VARIANT\_2003. |
|  | [imagecropauto](https://www.php.net/manual/en/function.imagecropauto.php) | The behavior of imagecropauto() in the bundled libgd has been synced with<br> that of system libgd: IMG\_CROP\_DEFAULT no longer falls<br> back to IMG\_CROP\_SIDES and threshold-cropping now uses<br> the same algorithm as system libgd. |
|  | [imagecropauto](https://www.php.net/manual/en/function.imagecropauto.php) | The default value of mode has been changed to<br> IMG\_CROP\_AUTO. Formerly, the default value has been<br> -1 which corresponds to IMG\_CROP\_DEFAULT,<br> but passing -1 is now deprecated. |
|  | [imagefilter](https://www.php.net/manual/en/function.imagefilter.php) | Scatter support (IMG\_FILTER\_SCATTER) was added. |
|  | [implode](https://www.php.net/manual/en/function.implode.php) | Passing the separator after the array<br> (i.e. using the legacy signature) has been deprecated. |
|  | [key](https://www.php.net/manual/en/function.key.php) | Instances of SPL classes are now treated like empty objects that have no properties instead of calling the Iterator method with the same name as this function. |
|  | [ldap\_control\_paged\_result](https://www.php.net/manual/en/function.ldap-control-paged-result.php) | This function has been deprecated. |
|  | [ldap\_control\_paged\_result\_response](https://www.php.net/manual/en/function.ldap-control-paged-result-response.php) | This function has been deprecated. |
|  | [method\_exists](https://www.php.net/manual/en/function.method-exists.php) | Class checks against inherited private methods now return false. |
|  | [money\_format](https://www.php.net/manual/en/function.money-format.php) | Deprecated this function. Instead, <br> use NumberFormatter::formatCurrency. |
|  | [next](https://www.php.net/manual/en/function.next.php) | Instances of SPL classes are now treated like empty objects that have no properties instead of calling the Iterator method with the same name as this function. |
|  | [octdec](https://www.php.net/manual/en/function.octdec.php) | Passing invalid characters will now generate a deprecation notice.<br> The result will still be computed as if the invalid characters did not exist. |
|  | [openssl\_random\_pseudo\_bytes](https://www.php.net/manual/en/function.openssl-random-pseudo-bytes.php) | The function no longer returns false on failure, but throws an Exception instead. |
|  | [password\_hash](https://www.php.net/manual/en/function.password-hash.php) | The algo parameter expects a string now, but still accepts<br> ints for backward compatibility. |
|  | [password\_hash](https://www.php.net/manual/en/function.password-hash.php) | The sodium extension provides an alternative implementation for Argon2 passwords. |
|  | [password\_needs\_rehash](https://www.php.net/manual/en/function.password-needs-rehash.php) | The algo parameter expects a string now, but still accepts<br> ints for backward compatibility. |
|  | [preg\_replace\_callback](https://www.php.net/manual/en/function.preg-replace-callback.php) | The flags parameter was added. |
|  | [preg\_replace\_callback\_array](https://www.php.net/manual/en/function.preg-replace-callback-array.php) | The flags parameter was added. |
|  | [prev](https://www.php.net/manual/en/function.prev.php) | Instances of SPL classes are now treated like empty objects that have no properties instead of calling the Iterator method with the same name as this function. |
|  | [proc\_open](https://www.php.net/manual/en/function.proc-open.php) | proc\_open now also accepts an array<br> for the command. |
|  | [proc\_open](https://www.php.net/manual/en/function.proc-open.php) | Added the create\_process\_group option to the<br> options parameter. |
|  | [reset](https://www.php.net/manual/en/function.reset.php) | Instances of SPL classes are now treated like empty objects that have no properties instead of calling the Iterator method with the same name as this function. |
|  | [restore\_include\_path](https://www.php.net/manual/en/function.restore-include-path.php) | Deprecated this function. |
|  | [stat](https://www.php.net/manual/en/function.stat.php) | On Windows, the device number is now the serial number of the volume that<br> contains the file, and the inode number is the identifier associated with the file. |
|  | [stat](https://www.php.net/manual/en/function.stat.php) | The size, atime, mtime and<br> ctime statistics of symlinks are always those of the target.<br> This was previously not the case for NTS builds on Windows. |
|  | [str\_getcsv](https://www.php.net/manual/en/function.str-getcsv.php) | The escape parameter now interprets an empty<br> string as signal to disable the proprietary escape mechanism. Formerly,<br> an empty string was treated like the default parameter value. |
|  | [strip\_tags](https://www.php.net/manual/en/function.strip-tags.php) | The allowed\_tags now alternatively accepts an array. |
|  | [unserialize](https://www.php.net/manual/en/function.unserialize.php) | Added the max\_depth element of<br> options to set the maximum depth of structures permitted during unserialization. |
|  | [Locale::lookup](https://www.php.net/manual/en/locale.lookup.php) | defaultLocale is nullable now. |
|  | [mysqli::\_\_construct](https://www.php.net/manual/en/mysqli.construct.php) | All parameters are now nullable. |
|  | [mysqli::real\_connect](https://www.php.net/manual/en/mysqli.real-connect.php) | All parameters are now nullable. |
|  | [ReflectionClass::setStaticPropertyValue](https://www.php.net/manual/en/reflectionclass.setstaticpropertyvalue.php) | Using ReflectionClass::setStaticPropertyValue to set<br> a private or protected property now results in a fatal error. Previously, it<br> threw a ReflectionException. |
|  | [ReflectionMethod::export](https://www.php.net/manual/en/reflectionmethod.export.php) | Deprecated this function. |
|  | [Reflector::export](https://www.php.net/manual/en/reflector.export.php) | Deprecated this function. |
|  | [SplFileObject::fgetcsv](https://www.php.net/manual/en/splfileobject.fgetcsv.php) | The escape parameter now also accepts an empty<br> string to disable the proprietary escape mechanism. |
|  | [SplFileObject::fputcsv](https://www.php.net/manual/en/splfileobject.fputcsv.php) | The escape parameter now also accepts an empty<br> string to disable the proprietary escape mechanism. |
|  | [SplFileObject::fwrite](https://www.php.net/manual/en/splfileobject.fwrite.php) | The function now returns false instead of zero on failure. |
|  | [SplFileObject::getCsvControl](https://www.php.net/manual/en/splfileobject.getcsvcontrol.php) | The escape character can now be an empty string. |
|  | [SplFileObject::setCsvControl](https://www.php.net/manual/en/splfileobject.setcsvcontrol.php) | The escape parameter now also accepts an empty<br> string to disable the proprietary escape mechanism. |
|  | [SQLite3Stmt::bindParam](https://www.php.net/manual/en/sqlite3stmt.bindparam.php) | param now also supports the @param<br> notation. |
|  | [SQLite3Stmt::bindValue](https://www.php.net/manual/en/sqlite3stmt.bindvalue.php) | param now also supports the @param<br> notation. |
| 7.3.24 | [jdtounix](https://www.php.net/manual/en/function.jdtounix.php) | The upper limit of julian\_day has been extended. Previously,<br> it was 2465342 regardless of the architecture. |
|  | [tidyNode::isHtml](https://www.php.net/manual/en/tidynode.ishtml.php) | This function has been fixed to have reasonable behavior. Previously,<br> almost any node was reported as being an HTML node. |
| 7.3.15 | [curl\_setopt](https://www.php.net/manual/en/function.curl-setopt.php) | Introduced CURLOPT\_HTTP09\_ALLOWED. |
| 7.3.14 | [dba\_open](https://www.php.net/manual/en/function.dba-open.php) | The lmdb driver now supports an additional map\_size<br> parameter. |
|  | [dba\_popen](https://www.php.net/manual/en/function.dba-popen.php) | The lmdb driver now supports an additional map\_size<br> parameter. |
| 7.3.6 | [DatePeriod::\_\_construct](https://www.php.net/manual/en/dateperiod.construct.php) | recurrences must be greater than 0 now. |
|  | [SplFileObject::\_\_toString](https://www.php.net/manual/en/splfileobject.tostring.php) | Changed from an alias of SplFileObject::current to an alias of SplFileObject::fgets. |
| 7.3.5 | [substr\_compare](https://www.php.net/manual/en/function.substr-compare.php) | offset may now be equal to the length of haystack. |
| 7.3.0 | [DateTimeImmutable::createFromFormat](https://www.php.net/manual/en/datetimeimmutable.createfromformat.php) | The v format specifier has<br> been added. |
|  | [apache\_request\_headers](https://www.php.net/manual/en/function.apache-request-headers.php) | This function became available in the FPM SAPI. |
|  | [array\_push](https://www.php.net/manual/en/function.array-push.php) | This function can now be called with only one parameter. Formerly, at<br> least two parameters have been required. |
|  | [array\_unshift](https://www.php.net/manual/en/function.array-unshift.php) | This function can now be called with only one parameter. Formerly, at<br> least two parameters have been required. |
|  | [assert](https://www.php.net/manual/en/function.assert.php) | Declaring a function called assert() inside a namespace<br> became deprecated. Such declaration now emits an E\_DEPRECATED. |
|  | [bcmul](https://www.php.net/manual/en/function.bcmul.php) | bcmul now returns numbers with the requested scale.<br> Formerly, the returned numbers may have omitted trailing decimal zeroes. |
|  | [bcpow](https://www.php.net/manual/en/function.bcpow.php) | bcpow now returns numbers with the requested scale.<br> Formerly, the returned numbers may have omitted trailing decimal zeroes. |
|  | [bcscale](https://www.php.net/manual/en/function.bcscale.php) | bcscale can now be used to get the current scale<br> factor; when used as setter, it now returns the old scale value.<br> Formerly, scale was mandatory, and<br> bcscale always returned true. |
|  | [compact](https://www.php.net/manual/en/function.compact.php) | compact now issues an E\_NOTICE level error if a given string<br> refers to an unset variable. Formerly, such strings have been silently skipped. |
|  | [curl\_getinfo](https://www.php.net/manual/en/function.curl-getinfo.php) | Introduced CURLINFO\_CONTENT\_LENGTH\_DOWNLOAD\_T,<br> CURLINFO\_CONTENT\_LENGTH\_UPLOAD\_T,<br> CURLINFO\_HTTP\_VERSION,<br> CURLINFO\_PROTOCOL,<br> CURLINFO\_PROXY\_SSL\_VERIFYRESULT,<br> CURLINFO\_SCHEME,<br> CURLINFO\_SIZE\_DOWNLOAD\_T,<br> CURLINFO\_SIZE\_UPLOAD\_T,<br> CURLINFO\_SPEED\_DOWNLOAD\_T,<br> CURLINFO\_SPEED\_UPLOAD\_T,<br> CURLINFO\_APPCONNECT\_TIME\_T,<br> CURLINFO\_CONNECT\_TIME\_T,<br> CURLINFO\_FILETIME\_T,<br> CURLINFO\_NAMELOOKUP\_TIME\_T,<br> CURLINFO\_PRETRANSFER\_TIME\_T,<br> CURLINFO\_REDIRECT\_TIME\_T,<br> CURLINFO\_STARTTRANSFER\_TIME\_T,<br> CURLINFO\_TOTAL\_TIME\_T. |
|  | [curl\_setopt](https://www.php.net/manual/en/function.curl-setopt.php) | Introduced CURLOPT\_ABSTRACT\_UNIX\_SOCKET, CURLOPT\_KEEP\_SENDING\_ON\_ERROR,<br> CURLOPT\_PRE\_PROXY, CURLOPT\_PROXY\_CAINFO,<br> CURLOPT\_PROXY\_CAPATH, CURLOPT\_PROXY\_CRLFILE,<br> CURLOPT\_PROXY\_KEYPASSWD, CURLOPT\_PROXY\_PINNEDPUBLICKEY,<br> CURLOPT\_PROXY\_SSLCERT, CURLOPT\_PROXY\_SSLCERTTYPE,<br> CURLOPT\_PROXY\_SSL\_CIPHER\_LIST, CURLOPT\_PROXY\_SSLKEY,<br> CURLOPT\_PROXY\_SSLKEYTYPE, CURLOPT\_PROXY\_SSL\_OPTIONS,<br> CURLOPT\_PROXY\_SSL\_VERIFYHOST, CURLOPT\_PROXY\_SSL\_VERIFYPEER,<br> CURLOPT\_PROXY\_SSLVERSION, CURLOPT\_PROXY\_TLSAUTH\_PASSWORD,<br> CURLOPT\_PROXY\_TLSAUTH\_TYPE, CURLOPT\_PROXY\_TLSAUTH\_USERNAME,<br> CURLOPT\_SOCKS5\_AUTH, CURLOPT\_SUPPRESS\_CONNECT\_HEADERS,<br> CURLOPT\_DISALLOW\_USERNAME\_IN\_URL, CURLOPT\_DNS\_SHUFFLE\_ADDRESSES,<br> CURLOPT\_HAPPY\_EYEBALLS\_TIMEOUT\_MS, CURLOPT\_HAPROXYPROTOCOL,<br> CURLOPT\_PROXY\_TLS13\_CIPHERS, CURLOPT\_SSH\_COMPRESSION,<br> CURLOPT\_TIMEVALUE\_LARGE and CURLOPT\_TLS13\_CIPHERS. |
|  | [define](https://www.php.net/manual/en/function.define.php) | case\_insensitive has been deprecated and will be removed in version 8.0.0. |
|  | [ftp\_fget](https://www.php.net/manual/en/function.ftp-fget.php) | The mode parameter is now optional. Formerly it<br> has been mandatory. |
|  | [ftp\_fput](https://www.php.net/manual/en/function.ftp-fput.php) | The mode parameter is now optional. Formerly it<br> has been mandatory. |
|  | [ftp\_get](https://www.php.net/manual/en/function.ftp-get.php) | The mode parameter is now optional. Formerly it<br> has been mandatory. |
|  | [ftp\_nb\_fget](https://www.php.net/manual/en/function.ftp-nb-fget.php) | The mode parameter is now optional. Formerly it<br> has been mandatory. |
|  | [ftp\_nb\_fput](https://www.php.net/manual/en/function.ftp-nb-fput.php) | The mode parameter is now optional. Formerly it<br> has been mandatory. |
|  | [ftp\_nb\_get](https://www.php.net/manual/en/function.ftp-nb-get.php) | The mode parameter is now optional. Formerly it<br> has been mandatory. |
|  | [ftp\_nb\_put](https://www.php.net/manual/en/function.ftp-nb-put.php) | The mode parameter is now optional. Formerly it<br> has been mandatory. |
|  | [ftp\_put](https://www.php.net/manual/en/function.ftp-put.php) | The mode parameter is now optional. Formerly it<br> has been mandatory. |
|  | [getallheaders](https://www.php.net/manual/en/function.getallheaders.php) | This function became available in the FPM SAPI. |
|  | [imagecreatefromstring](https://www.php.net/manual/en/function.imagecreatefromstring.php) | WEBP is supported now (if supported by the libgd in use). |
|  | [is\_countable](https://www.php.net/manual/en/function.is-countable.php) | is\_countable has been added. |
|  | [json\_decode](https://www.php.net/manual/en/function.json-decode.php) | JSON\_THROW\_ON\_ERROR<br> flags was added. |
|  | [json\_encode](https://www.php.net/manual/en/function.json-encode.php) | JSON\_THROW\_ON\_ERROR<br> flags was added. |
|  | [ldap\_add](https://www.php.net/manual/en/function.ldap-add.php) | Support for controls added |
|  | [ldap\_compare](https://www.php.net/manual/en/function.ldap-compare.php) | Support for controls added |
|  | [ldap\_delete](https://www.php.net/manual/en/function.ldap-delete.php) | Support for controls added |
|  | [ldap\_exop](https://www.php.net/manual/en/function.ldap-exop.php) | Support for controls added |
|  | [ldap\_exop\_passwd](https://www.php.net/manual/en/function.ldap-exop-passwd.php) | Support for controls added |
|  | [ldap\_list](https://www.php.net/manual/en/function.ldap-list.php) | Support for controls added |
|  | [ldap\_mod\_add](https://www.php.net/manual/en/function.ldap-mod-add.php) | Support for controls added |
|  | [ldap\_mod\_del](https://www.php.net/manual/en/function.ldap-mod-del.php) | Support for controls added |
|  | [ldap\_mod\_replace](https://www.php.net/manual/en/function.ldap-mod-replace.php) | Support for controls added |
|  | [ldap\_modify\_batch](https://www.php.net/manual/en/function.ldap-modify-batch.php) | Support for controls added |
|  | [ldap\_mod\_add\_ext](https://www.php.net/manual/en/function.ldap-mod_add-ext.php) | Support for controls added |
|  | [ldap\_mod\_del\_ext](https://www.php.net/manual/en/function.ldap-mod_del-ext.php) | Support for controls added |
|  | [ldap\_mod\_replace\_ext](https://www.php.net/manual/en/function.ldap-mod_replace-ext.php) | Support for controls added |
|  | [ldap\_parse\_result](https://www.php.net/manual/en/function.ldap-parse-result.php) | Support for controls added |
|  | [ldap\_read](https://www.php.net/manual/en/function.ldap-read.php) | Support for controls added |
|  | [ldap\_rename](https://www.php.net/manual/en/function.ldap-rename.php) | Support for controls added |
|  | [ldap\_rename\_ext](https://www.php.net/manual/en/function.ldap-rename-ext.php) | Support for controls added |
|  | [ldap\_search](https://www.php.net/manual/en/function.ldap-search.php) | Support for controls added |
|  | [list](https://www.php.net/manual/en/function.list.php) | Support for reference assignments in array destructuring was added. |
|  | [mb\_convert\_case](https://www.php.net/manual/en/function.mb-convert-case.php) | Added support for<br> MB\_CASE\_FOLD,<br> MB\_CASE\_UPPER\_SIMPLE,<br> MB\_CASE\_LOWER\_SIMPLE,<br> MB\_CASE\_TITLE\_SIMPLE, and<br> MB\_CASE\_FOLD\_SIMPLE<br> as mode. |
|  | [password\_hash](https://www.php.net/manual/en/function.password-hash.php) | Support for Argon2id passwords using PASSWORD\_ARGON2ID was added. |
|  | [preg\_quote](https://www.php.net/manual/en/function.preg-quote.php) | The # character is now quoted |
|  | [session\_get\_cookie\_params](https://www.php.net/manual/en/function.session-get-cookie-params.php) | The "samesite" entry was added in the returned array. |
|  | [session\_set\_cookie\_params](https://www.php.net/manual/en/function.session-set-cookie-params.php) | An alternative signature supporting an lifetime\_or\_options<br> array has been added. This signature supports also setting of the<br> SameSite cookie attribute. |
|  | [setcookie](https://www.php.net/manual/en/function.setcookie.php) | An alternative signature supporting an options<br> array has been added. This signature supports also setting of the<br> SameSite cookie attribute. |
|  | [setrawcookie](https://www.php.net/manual/en/function.setrawcookie.php) | An alternative signature supporting an options<br> array has been added. This signature supports also setting of the<br> SameSite cookie attribute. |
|  | [stripos](https://www.php.net/manual/en/function.stripos.php) | Passing an int as needle has been deprecated. |
|  | [stristr](https://www.php.net/manual/en/function.stristr.php) | Passing an int as needle has been deprecated. |
|  | [strpos](https://www.php.net/manual/en/function.strpos.php) | Passing an int as needle has been deprecated. |
|  | [strrchr](https://www.php.net/manual/en/function.strrchr.php) | Passing an int as needle has been deprecated. |
|  | [strripos](https://www.php.net/manual/en/function.strripos.php) | Passing an int as needle has been deprecated. |
|  | [strrpos](https://www.php.net/manual/en/function.strrpos.php) | Passing an int as needle has been deprecated. |
|  | [strstr](https://www.php.net/manual/en/function.strstr.php) | Passing an int as needle has been deprecated. |
|  | [unlink](https://www.php.net/manual/en/function.unlink.php) | On Windows, it is now possible to unlink files with<br> handles in use, while formerly that would fail. However, it is still not<br> possible to re-create the unlinked file, until all handles to it have been<br> closed. |
|  | [var\_export](https://www.php.net/manual/en/function.var-export.php) | Now exports stdClass objects as an array cast to<br> an object ((object) array( ... )), rather than using the<br> nonexistent method stdClass::\_\_setState.<br> The practical effect is that now stdClass is<br> exportable, and the resulting code will even work on earlier versions of<br> PHP. |
|  | [xml\_parser\_get\_option](https://www.php.net/manual/en/function.xml-parser-get-option.php) | options now supports XML\_OPTION\_SKIP\_TAGSTART<br> and XML\_OPTION\_SKIP\_WHITE. |
|  | [xml\_set\_external\_entity\_ref\_handler](https://www.php.net/manual/en/function.xml-set-external-entity-ref-handler.php) | The return value of the handler is no longer<br> ignored if the extension has been built against libxml. Formerly, the return<br> value has been ignored, and parsing did never stop. |
| 7.2.19 | [DatePeriod::\_\_construct](https://www.php.net/manual/en/dateperiod.construct.php) | recurrences must be greater than 0 now. |
|  | [SplFileObject::\_\_toString](https://www.php.net/manual/en/splfileobject.tostring.php) | Changed from an alias of SplFileObject::current to an alias of SplFileObject::fgets. |
| 7.2.18 | [substr\_compare](https://www.php.net/manual/en/function.substr-compare.php) | offset may now be equal to the length of haystack. |
| 7.2.12 | [DateInterval::format](https://www.php.net/manual/en/dateinterval.format.php) | The F and f format<br> will now always be positive. |
|  | [xml\_parser\_get\_option](https://www.php.net/manual/en/function.xml-parser-get-option.php) | options now supports XML\_OPTION\_SKIP\_TAGSTART<br> and XML\_OPTION\_SKIP\_WHITE. |
| 7.2.0 | [array\_unique](https://www.php.net/manual/en/function.array-unique.php) | If flags is SORT\_STRING,<br> formerly array has been copied and non-unique<br> elements have been removed (without packing the array afterwards), but<br> now a new array is built by adding the unique elements. This can result<br> in different numeric indexes. |
|  | [assert](https://www.php.net/manual/en/function.assert.php) | Usage of a string as the assertion<br> became deprecated. It now emits an E\_DEPRECATED<br> notice when both assert.active<br> and zend.assertions are set<br> to 1. |
|  | [bcmod](https://www.php.net/manual/en/function.bcmod.php) | num1 and num2 are no<br> longer truncated to integer, so now the behavior of<br> bcmod follows fmod rather than<br> the % operator. |
|  | [bcmod](https://www.php.net/manual/en/function.bcmod.php) | The scale parameter was added. |
|  | [count](https://www.php.net/manual/en/function.count.php) | count will now yield a warning on invalid countable types <br> passed to the value parameter. |
|  | [date\_parse](https://www.php.net/manual/en/function.date-parse.php) | The zone element of the returned array represents<br> seconds instead of minutes now, and its sign is inverted. For instance<br> -120 is now 7200. |
|  | [date\_parse\_from\_format](https://www.php.net/manual/en/function.date-parse-from-format.php) | The zone element of the returned array represents<br> seconds instead of minutes now, and its sign is inverted. For instance<br> -120 is now 7200. |
|  | [date\_sun\_info](https://www.php.net/manual/en/function.date-sun-info.php) | The calculation was fixed with regards to local midnight instead of<br> local noon, which changes the results slightly. |
|  | [exif\_read\_data](https://www.php.net/manual/en/function.exif-read-data.php) | The file parameter now supports both local files <br> and stream resources. |
|  | [exif\_read\_data](https://www.php.net/manual/en/function.exif-read-data.php) | Support for the following EXIF formats were added:<br> <br> Samsung<br> DJI<br> Panasonic<br> Sony<br> Pentax<br> Minolta<br> Sigma/Foveon<br> AGFA<br> Kyocera<br> Ricoh<br> Epson |
|  | [exif\_thumbnail](https://www.php.net/manual/en/function.exif-thumbnail.php) | The file parameter now supports both local files<br> and stream resources. |
|  | [ezmlm\_hash](https://www.php.net/manual/en/function.ezmlm-hash.php) | Deprecated this function. |
|  | [get\_class](https://www.php.net/manual/en/function.get-class.php) | Prior to this version the default value for object<br> was null and it had the same effect as not passing any value. Now<br> null has been removed as the default value for object,<br> and is no longer a valid input. |
|  | [gettype](https://www.php.net/manual/en/function.gettype.php) | Closed resources are now reported as 'resource (closed)'.<br> Previously the returned value for closed resources were 'unknown type'. |
|  | [hash\_copy](https://www.php.net/manual/en/function.hash-copy.php) | Accept and return HashContext instead of resource. |
|  | [hash\_final](https://www.php.net/manual/en/function.hash-final.php) | Accept HashContext instead of resource. |
|  | [hash\_hmac](https://www.php.net/manual/en/function.hash-hmac.php) | Usage of non-cryptographic hash functions (adler32, crc32, crc32b, fnv132, fnv1a32, fnv164, fnv1a64, joaat) was disabled. |
|  | [hash\_hmac\_file](https://www.php.net/manual/en/function.hash-hmac-file.php) | Usage of non-cryptographic hash functions (adler32, crc32, crc32b, fnv132, fnv1a32, fnv164, fnv1a64, joaat) was disabled. |
|  | [hash\_init](https://www.php.net/manual/en/function.hash-init.php) | Usage of non-cryptographic hash functions (adler32, crc32, crc32b, fnv132, fnv1a32, fnv164, fnv1a64, joaat) with HASH\_HMAC was disabled. |
|  | [hash\_init](https://www.php.net/manual/en/function.hash-init.php) | Return HashContext instead of resource. |
|  | [hash\_pbkdf2](https://www.php.net/manual/en/function.hash-pbkdf2.php) | Usage of non-cryptographic hash functions (adler32, crc32, crc32b, fnv132, fnv1a32, fnv164, fnv1a64, joaat) was disabled. |
|  | [hash\_update](https://www.php.net/manual/en/function.hash-update.php) | Accept HashContext instead of resource. |
|  | [hash\_update\_file](https://www.php.net/manual/en/function.hash-update-file.php) | Accept HashContext instead of resource. |
|  | [hash\_update\_stream](https://www.php.net/manual/en/function.hash-update-stream.php) | Accept HashContext instead of resource. |
|  | [idn\_to\_ascii](https://www.php.net/manual/en/function.idn-to-ascii.php) | INTL\_IDNA\_VARIANT\_2003 has been deprecated; use<br> INTL\_IDNA\_VARIANT\_UTS46 instead. |
|  | [idn\_to\_utf8](https://www.php.net/manual/en/function.idn-to-utf8.php) | INTL\_IDNA\_VARIANT\_2003 has been deprecated; use<br> INTL\_IDNA\_VARIANT\_UTS46 instead. |
|  | [imageantialias](https://www.php.net/manual/en/function.imageantialias.php) | imageantialias is now generally available. Formerly<br> it was only available if PHP was compiled with the bundled version of the<br> GD library. |
|  | [imagegd](https://www.php.net/manual/en/function.imagegd.php) | imagegd now allows to output truecolor images.<br> Formerly, these have been implicitly converted to palette. |
|  | [imagelayereffect](https://www.php.net/manual/en/function.imagelayereffect.php) | Added IMG\_EFFECT\_MULTIPLY (requires system libgd >=<br> 2.1.1 or the bundled libgd). |
|  | [imagetypes](https://www.php.net/manual/en/function.imagetypes.php) | IMG\_BMP added. |
|  | [is\_object](https://www.php.net/manual/en/function.is-object.php) | is\_object now returns true for unserialized objects without <br> a class definition (class of \_\_PHP\_Incomplete\_Class). Previously <br> false was returned. |
|  | [json\_decode](https://www.php.net/manual/en/function.json-decode.php) | associative is nullable now. |
|  | [json\_decode](https://www.php.net/manual/en/function.json-decode.php) | JSON\_INVALID\_UTF8\_IGNORE, and<br> JSON\_INVALID\_UTF8\_SUBSTITUTE<br> flags were added. |
|  | [json\_encode](https://www.php.net/manual/en/function.json-encode.php) | JSON\_INVALID\_UTF8\_IGNORE, and<br> JSON\_INVALID\_UTF8\_SUBSTITUTE<br> flags were added. |
|  | [mail](https://www.php.net/manual/en/function.mail.php) | The additional\_headers parameter now also accepts<br> an array. |
|  | [mb\_check\_encoding](https://www.php.net/manual/en/function.mb-check-encoding.php) | This function now also accepts an array as value.<br> Formerly, only strings have been supported. |
|  | [mb\_convert\_encoding](https://www.php.net/manual/en/function.mb-convert-encoding.php) | This function now also accepts an array as string.<br> Formerly, only strings have been supported. |
|  | [mb\_parse\_str](https://www.php.net/manual/en/function.mb-parse-str.php) | Calling mb\_parse\_str without the second parameter was deprecated. |
|  | [mb\_send\_mail](https://www.php.net/manual/en/function.mb-send-mail.php) | The additional\_headers parameter now also accepts<br> an array. |
|  | [mt\_rand](https://www.php.net/manual/en/function.mt-rand.php) | mt\_rand has received a bug fix for a modulo bias bug. This means that sequences generated with a specific seed may differ from PHP 7.1 on 64-bit machines. |
|  | [number\_format](https://www.php.net/manual/en/function.number-format.php) | number\_format was changed to not being able to return <br> -0, previously -0 could be returned <br> for cases like where num would be -0.01. |
|  | [openssl\_pkcs7\_verify](https://www.php.net/manual/en/function.openssl-pkcs7-verify.php) | The output\_filename parameter was added. |
|  | [pack](https://www.php.net/manual/en/function.pack.php) | float and double types supports both Big Endian and Little Endian. |
|  | [parse\_str](https://www.php.net/manual/en/function.parse-str.php) | Usage of parse\_str without a second parameter<br> now emits an E\_DEPRECATED notice. |
|  | [password\_hash](https://www.php.net/manual/en/function.password-hash.php) | Support for Argon2i passwords using PASSWORD\_ARGON2I was added. |
|  | [preg\_match](https://www.php.net/manual/en/function.preg-match.php) | The PREG\_UNMATCHED\_AS\_NULL is now supported for the<br> $flags parameter. |
|  | [preg\_match\_all](https://www.php.net/manual/en/function.preg-match-all.php) | The PREG\_UNMATCHED\_AS\_NULL is now supported for the<br> $flags parameter. |
|  | [preg\_quote](https://www.php.net/manual/en/function.preg-quote.php) | delimiter is nullable now. |
|  | [proc\_nice](https://www.php.net/manual/en/function.proc-nice.php) | This function is now available on Windows. |
|  | [rand](https://www.php.net/manual/en/function.rand.php) | rand has received a bug fix for a modulo bias bug. This means that sequences generated with a specific seed may differ from PHP 7.1 on 64-bit machines. |
|  | [read\_exif\_data](https://www.php.net/manual/en/function.read-exif-data.php) | This function alias was deprecated. |
|  | [session\_abort](https://www.php.net/manual/en/function.session-abort.php) | The return type of this function is bool now.<br> Formerly, it has been void. |
|  | [session\_module\_name](https://www.php.net/manual/en/function.session-module-name.php) | It is now explicitly forbidden to set the module name to<br> "user". Formerly, this has been silently ignored. |
|  | [session\_name](https://www.php.net/manual/en/function.session-name.php) | session\_name checks session status,<br> previously it only checked cookie status. Therefore,<br> older session\_name allows to<br> call session\_name<br> after session\_start which may crash PHP<br> and may result in misbehaviors. |
|  | [session\_reset](https://www.php.net/manual/en/function.session-reset.php) | The return type of this function is bool now.<br> Formerly, it has been void. |
|  | [session\_set\_cookie\_params](https://www.php.net/manual/en/function.session-set-cookie-params.php) | Returns true on success or false on failure. Formerly the function returned void. |
|  | [session\_unset](https://www.php.net/manual/en/function.session-unset.php) | The return type of this function is bool now.<br> Formerly, it has been void. |
|  | [session\_write\_close](https://www.php.net/manual/en/function.session-write-close.php) | The return type of this function is bool now.<br> Formerly, it has been void. |
|  | [set\_error\_handler](https://www.php.net/manual/en/function.set-error-handler.php) | errcontext became deprecated. Usage of this parameter now emits an E\_DEPRECATED notice. |
|  | [unpack](https://www.php.net/manual/en/function.unpack.php) | float and double types supports both Big Endian and Little Endian. |
|  | [utf8\_decode](https://www.php.net/manual/en/function.utf8-decode.php) | This function has been moved from the XML extension to the core of PHP.<br> In previous versions, it was only available if the XML extension was installed. |
|  | [utf8\_encode](https://www.php.net/manual/en/function.utf8-encode.php) | This function has been moved from the XML extension to the core of PHP.<br> In previous versions, it was only available if the XML extension was installed. |
|  | [PDOStatement::debugDumpParams](https://www.php.net/manual/en/pdostatement.debugdumpparams.php) | PDOStatement::debugDumpParams now returns the SQL sent to<br> the database, including the full, raw query (including the replaced placeholders with<br> their bounded values). Note, that this will only be available if emulated prepared<br> statements are turned on. |
|  | [ReflectionClass::getMethods](https://www.php.net/manual/en/reflectionclass.getmethods.php) | filter is nullable now. |
|  | [ReflectionClass::getProperties](https://www.php.net/manual/en/reflectionclass.getproperties.php) | filter is nullable now. |
|  | [SQLite3::openBlob](https://www.php.net/manual/en/sqlite3.openblob.php) | The flags parameter has been added, allowing to<br> write BLOBs; formerly only reading was supported. |
| 7.1.24 | [xml\_parser\_get\_option](https://www.php.net/manual/en/function.xml-parser-get-option.php) | options now supports XML\_OPTION\_SKIP\_TAGSTART<br> and XML\_OPTION\_SKIP\_WHITE. |
| 7.1.5 | [IntlDateFormatter::format](https://www.php.net/manual/en/intldateformatter.format.php) | Support for providing general DateTimeInterface objects to the<br> datetime parameter was added. Formerly, only proper<br> DateTime objects were supported. |
| 7.1.4 | [PDO::sqliteCreateFunction](https://www.php.net/manual/en/pdo.sqlitecreatefunction.php) | The flags parameter has been added. |
|  | [SQLite3::createFunction](https://www.php.net/manual/en/sqlite3.createfunction.php) | The flags parameter has been added. |
| 7.1.2 | [dns\_get\_record](https://www.php.net/manual/en/function.dns-get-record.php) | Added support for CAA record type. |
|  | [fopen](https://www.php.net/manual/en/function.fopen.php) | The 'e' option was added. |
| 7.1.1 | [get\_defined\_functions](https://www.php.net/manual/en/function.get-defined-functions.php) | The exclude\_disabled parameter has been added. |
|  | [pack](https://www.php.net/manual/en/function.pack.php) | The "e", "E", "g" and "G" codes were added to enable byte order support for float and double. |
| 7.1.0 | [DateInterval::format](https://www.php.net/manual/en/dateinterval.format.php) | The F and f format<br> characters were added. |
|  | [DateTime::setTime](https://www.php.net/manual/en/datetime.settime.php) | The microsecond parameter was added. |
|  | [DateTimeImmutable::\_\_construct](https://www.php.net/manual/en/datetimeimmutable.construct.php) | From now on microseconds are filled with actual value. Not with '00000'. |
|  | [DateTimeImmutable::setTime](https://www.php.net/manual/en/datetimeimmutable.settime.php) | The microsecond parameter was added. |
|  | [DateTimeZone::listIdentifiers](https://www.php.net/manual/en/datetimezone.listidentifiers.php) | countryCode is nullable now. |
|  | [array\_rand](https://www.php.net/manual/en/function.array-rand.php) | The internal randomization algorithm has been changed to use the Mersenne Twister Random Number Generator instead of the libc rand function. |
|  | [curl\_multi\_setopt](https://www.php.net/manual/en/function.curl-multi-setopt.php) | Introduced CURLMOPT\_PUSHFUNCTION. |
|  | [exif\_imagetype](https://www.php.net/manual/en/function.exif-imagetype.php) | Added WebP support. |
|  | [file\_get\_contents](https://www.php.net/manual/en/function.file-get-contents.php) | Support for negative offsets has been added. |
|  | [get\_headers](https://www.php.net/manual/en/function.get-headers.php) | The context parameter was added. |
|  | [getenv](https://www.php.net/manual/en/function.getenv.php) | The name can now be omitted to retrieve an<br> associative array of all environment variables. |
|  | [getimagesize](https://www.php.net/manual/en/function.getimagesize.php) | Added WebP support. |
|  | [getopt](https://www.php.net/manual/en/function.getopt.php) | Added the rest\_index parameter. |
|  | [grapheme\_extract](https://www.php.net/manual/en/function.grapheme-extract.php) | Support for negative offsets has been added. |
|  | [grapheme\_stripos](https://www.php.net/manual/en/function.grapheme-stripos.php) | Support for negative offsets has been added. |
|  | [grapheme\_strpos](https://www.php.net/manual/en/function.grapheme-strpos.php) | Support for negative offsets has been added. |
|  | [hash\_algos](https://www.php.net/manual/en/function.hash-algos.php) | Support for sha512/224, sha512/256, sha3-224, sha3-256, sha3-384 and<br> sha3-512 has been added. |
|  | [iconv\_strpos](https://www.php.net/manual/en/function.iconv-strpos.php) | Support for negative offsets has been added. |
|  | [json\_decode](https://www.php.net/manual/en/function.json-decode.php) | An empty JSON key ("") can be encoded to the empty object property<br> instead of using a key with value \_empty\_. |
|  | [json\_encode](https://www.php.net/manual/en/function.json-encode.php) | JSON\_UNESCAPED\_LINE\_TERMINATORS<br> flags was added. |
|  | [json\_encode](https://www.php.net/manual/en/function.json-encode.php) | serialize\_precision is<br> used instead of precision when<br> encoding float values. |
|  | [list](https://www.php.net/manual/en/function.list.php) | It is now possible to specify keys in list. This<br> enables destructuring of arrays with non-integer or non-sequential keys. |
|  | [long2ip](https://www.php.net/manual/en/function.long2ip.php) | The parameter type of ip has been<br> changed from string to int. |
|  | [mb\_ereg](https://www.php.net/manual/en/function.mb-ereg.php) | mb\_ereg will now set matches to<br> an empty array, if nothing matched. Formerly,<br> matches was not modified in that case. |
|  | [mb\_ereg\_replace](https://www.php.net/manual/en/function.mb-ereg-replace.php) | The function checks whether string is valid for the<br> current encoding. |
|  | [mb\_ereg\_replace](https://www.php.net/manual/en/function.mb-ereg-replace.php) | The e modifier has been deprecated. |
|  | [mb\_ereg\_replace\_callback](https://www.php.net/manual/en/function.mb-ereg-replace-callback.php) | The function checks whether string is valid for the<br> current encoding. |
|  | [mb\_ereg\_search\_setpos](https://www.php.net/manual/en/function.mb-ereg-search-setpos.php) | Support for negative offsets has been added. |
|  | [mb\_eregi](https://www.php.net/manual/en/function.mb-eregi.php) | mb\_eregi will now set matches to<br> an empty array, if nothing matched. Formerly,<br> matches was not modified in that case. |
|  | [mb\_eregi\_replace](https://www.php.net/manual/en/function.mb-eregi-replace.php) | The function checks whether string is valid for the<br> current encoding. |
|  | [mb\_eregi\_replace](https://www.php.net/manual/en/function.mb-eregi-replace.php) | The e modifier has been deprecated. |
|  | [mb\_regex\_set\_options](https://www.php.net/manual/en/function.mb-regex-set-options.php) | The "e" option now emits an E\_DEPRECATED. |
|  | [mb\_strimwidth](https://www.php.net/manual/en/function.mb-strimwidth.php) | Support for negative starts and widths has been added. |
|  | [mb\_stripos](https://www.php.net/manual/en/function.mb-stripos.php) | Support for negative offsets has been added. |
|  | [mb\_strpos](https://www.php.net/manual/en/function.mb-strpos.php) | Support for negative offsets has been added. |
|  | [mt\_rand](https://www.php.net/manual/en/function.mt-rand.php) | rand has been made an alias of mt\_rand. |
|  | [mt\_rand](https://www.php.net/manual/en/function.mt-rand.php) | mt\_rand has been updated to use the fixed, correct, version of<br> the Mersenne Twister algorithm. To fall back to the old behaviour, use mt\_srand with MT\_RAND\_PHP as the second parameter. |
|  | [mt\_srand](https://www.php.net/manual/en/function.mt-srand.php) | srand has been made an alias of mt\_srand. |
|  | [mt\_srand](https://www.php.net/manual/en/function.mt-srand.php) | mt\_rand has been updated to use the fixed, correct, version of<br> the Mersenne Twister algorithm. To fall back to the old behaviour, use mt\_srand with MT\_RAND\_PHP as the second parameter. |
|  | [openssl\_csr\_new](https://www.php.net/manual/en/function.openssl-csr-new.php) | options now also supports curve\_name. |
|  | [openssl\_decrypt](https://www.php.net/manual/en/function.openssl-decrypt.php) | The tag and aad parameters were added. |
|  | [openssl\_encrypt](https://www.php.net/manual/en/function.openssl-encrypt.php) | The tag, aad and tag\_length parameters were added. |
|  | [openssl\_pkey\_new](https://www.php.net/manual/en/function.openssl-pkey-new.php) | The curve\_name key of the options parameter was<br> added to make it possible to create EC keys based on Elliptic Curve algorithms. |
|  | [output\_add\_rewrite\_var](https://www.php.net/manual/en/function.output-add-rewrite-var.php) | As of PHP 7.1.0, a dedicated output buffer is used,<br> url\_rewriter.tags<br> is used solely for output functions and<br> url\_rewriter.hosts is available.<br> Prior to PHP 7.1.0, rewrite variables set by output\_add\_rewrite\_var<br> shared an output buffer with transparent session id support<br> (see session.trans\_sid\_tags). |
|  | [output\_reset\_rewrite\_vars](https://www.php.net/manual/en/function.output-reset-rewrite-vars.php) | Before PHP 7.1.0, rewrite vars set by output\_add\_rewrite\_var<br> use the same Session module trans sid output buffer. Since PHP 7.1.0,<br> dedicated output buffer is used and output\_reset\_rewrite\_vars<br> only removes rewrite vars defined by output\_add\_rewrite\_var. |
|  | [pcntl\_signal](https://www.php.net/manual/en/function.pcntl-signal.php) | As of PHP 7.1.0 the handler callback is given a second argument<br> containing the siginfo of the specific signal. This data is only<br> supplied if the operating system has the siginfo\_t structure.<br> If the OS does not implement siginfo\_t NULL is supplied. |
|  | [pcntl\_signal\_get\_handler](https://www.php.net/manual/en/function.pcntl-signal-get-handler.php) | pcntl\_signal\_get\_handler has been added. |
|  | [pg\_fetch\_all](https://www.php.net/manual/en/function.pg-fetch-all.php) | The mode parameter was added. |
|  | [pg\_last\_notice](https://www.php.net/manual/en/function.pg-last-notice.php) | The mode parameter was added. |
|  | [pg\_select](https://www.php.net/manual/en/function.pg-select.php) | The mode parameter was added. |
|  | [rand](https://www.php.net/manual/en/function.rand.php) | rand has been made an alias of mt\_rand. |
|  | [session\_start](https://www.php.net/manual/en/function.session-start.php) | session\_start now returns false and no longer<br> initializes $\_SESSION when it failed to start the<br> session. |
|  | [shuffle](https://www.php.net/manual/en/function.shuffle.php) | The internal randomization algorithm has been changed to use the Mersenne Twister Random Number Generator instead of the libc rand function. |
|  | [srand](https://www.php.net/manual/en/function.srand.php) | srand has been made an alias of mt\_srand. |
|  | [str\_shuffle](https://www.php.net/manual/en/function.str-shuffle.php) | The internal randomization algorithm has been changed to use the Mersenne Twister Random Number Generator instead of the libc rand function. |
|  | [stripos](https://www.php.net/manual/en/function.stripos.php) | Support for negative offsets has been added. |
|  | [strpos](https://www.php.net/manual/en/function.strpos.php) | Support for negative offsets has been added. |
|  | [substr\_count](https://www.php.net/manual/en/function.substr-count.php) | Support for negative offsets and lengths has been added.<br> length may also be 0 now. |
|  | [tempnam](https://www.php.net/manual/en/function.tempnam.php) | tempnam now emits a notice when falling back to the<br> temp directory of the system. |
|  | [unpack](https://www.php.net/manual/en/function.unpack.php) | The optional offset has been added. |
|  | [unserialize](https://www.php.net/manual/en/function.unserialize.php) | The allowed\_classes element of<br> options is now strictly typed, i.e. if anything<br> other than an array or a bool is given,<br> unserialize returns false and issues an<br> E\_WARNING. |
|  | [ReflectionType::\_\_toString](https://www.php.net/manual/en/reflectiontype.tostring.php) | ReflectionType::\_\_toString has been deprecated. |
|  | [SessionHandler::gc](https://www.php.net/manual/en/sessionhandler.gc.php) | Prior to this version, the function returned true on success. |
|  | [SessionHandlerInterface::gc](https://www.php.net/manual/en/sessionhandlerinterface.gc.php) | Prior to this version, the function returned true on success. |
| 7.0.16 | [dns\_get\_record](https://www.php.net/manual/en/function.dns-get-record.php) | Added support for CAA record type. |
|  | [fopen](https://www.php.net/manual/en/function.fopen.php) | The 'e' option was added. |
| 7.0.15 | [get\_defined\_functions](https://www.php.net/manual/en/function.get-defined-functions.php) | The exclude\_disabled parameter has been added. |
|  | [pack](https://www.php.net/manual/en/function.pack.php) | The "e", "E", "g" and "G" codes were added to enable byte order support for float and double. |
| 7.0.11 | [iconv\_substr](https://www.php.net/manual/en/function.iconv-substr.php) | If string is equal to<br> offset characters long, an empty string will be<br> returned. Prior to this version, false was returned in this case. |
| 7.0.10 | [imagetypes](https://www.php.net/manual/en/function.imagetypes.php) | IMG\_WEBP added. |
|  | [SplFileObject::getCsvControl](https://www.php.net/manual/en/splfileobject.getcsvcontrol.php) | Added the escape character to the returned array. |
|  | [SQLite3::\_\_construct](https://www.php.net/manual/en/sqlite3.construct.php) | The filename can now be empty to use a private,<br> temporary on-disk database. |
| 7.0.9 | [getenv](https://www.php.net/manual/en/function.getenv.php) | The local\_only parameter has been added. |
| 7.0.7 | [curl\_multi\_setopt](https://www.php.net/manual/en/function.curl-multi-setopt.php) | Introduced CURLMOPT\_CHUNK\_LENGTH\_PENALTY\_SIZE,<br> CURLMOPT\_CONTENT\_LENGTH\_PENALTY\_SIZE,<br> CURLMOPT\_MAX\_HOST\_CONNECTIONS,<br> CURLMOPT\_MAX\_PIPELINE\_LENGTH and<br> CURLMOPT\_MAX\_TOTAL\_CONNECTIONS. |
|  | [curl\_setopt](https://www.php.net/manual/en/function.curl-setopt.php) | Introduced CURL\_HTTP\_VERSION\_2, CURL\_HTTP\_VERSION\_2\_PRIOR\_KNOWLEDGE,<br> CURL\_HTTP\_VERSION\_2TLS, CURL\_REDIR\_POST\_301,<br> CURL\_REDIR\_POST\_302, CURL\_REDIR\_POST\_303,<br> CURL\_REDIR\_POST\_ALL, CURL\_VERSION\_KERBEROS5,<br> CURL\_VERSION\_PSL, CURL\_VERSION\_UNIX\_SOCKETS,<br> CURLAUTH\_NEGOTIATE, CURLAUTH\_NTLM\_WB,<br> CURLFTP\_CREATE\_DIR, CURLFTP\_CREATE\_DIR\_NONE,<br> CURLFTP\_CREATE\_DIR\_RETRY, CURLHEADER\_SEPARATE,<br> CURLHEADER\_UNIFIED, CURLMOPT\_CHUNK\_LENGTH\_PENALTY\_SIZE,<br> CURLMOPT\_CONTENT\_LENGTH\_PENALTY\_SIZE, CURLMOPT\_MAX\_HOST\_CONNECTIONS,<br> CURLMOPT\_MAX\_PIPELINE\_LENGTH, CURLMOPT\_MAX\_TOTAL\_CONNECTIONS,<br> CURLOPT\_CONNECT\_TO, CURLOPT\_DEFAULT\_PROTOCOL,<br> CURLOPT\_DNS\_INTERFACE, CURLOPT\_DNS\_LOCAL\_IP4,<br> CURLOPT\_DNS\_LOCAL\_IP6, CURLOPT\_EXPECT\_100\_TIMEOUT\_MS,<br> CURLOPT\_HEADEROPT, CURLOPT\_LOGIN\_OPTIONS,<br> CURLOPT\_PATH\_AS\_IS, CURLOPT\_PINNEDPUBLICKEY,<br> CURLOPT\_PIPEWAIT, CURLOPT\_PROXY\_SERVICE\_NAME,<br> CURLOPT\_PROXYHEADER, CURLOPT\_SASL\_IR,<br> CURLOPT\_SERVICE\_NAME, CURLOPT\_SSL\_ENABLE\_ALPN,<br> CURLOPT\_SSL\_ENABLE\_NPN, CURLOPT\_SSL\_FALSESTART,<br> CURLOPT\_SSL\_VERIFYSTATUS, CURLOPT\_STREAM\_WEIGHT,<br> CURLOPT\_TCP\_FASTOPEN, CURLOPT\_TFTP\_NO\_OPTIONS,<br> CURLOPT\_UNIX\_SOCKET\_PATH, CURLOPT\_XOAUTH2\_BEARER,<br> CURLPROTO\_SMB, CURLPROTO\_SMBS,<br> CURLPROXY\_HTTP\_1\_0, CURLSSH\_AUTH\_AGENT and<br> CURLSSLOPT\_NO\_REVOKE. |

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-base/blob/master/manual.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Fdoc.changelog%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=doc.changelog&repo=en&redirect=https://www.php.net/manual/en/doc.changelog.php)

### User Contributed Notes

There are no user contributed notes for this page.

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google