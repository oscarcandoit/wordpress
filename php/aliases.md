---
url: https://www.php.net/manual/en/aliases.php
scraped_at: 2025-10-20T02:43:03.732Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# List of Function Aliases [¶](https://www.php.net/manual/en/aliases.php\#aliases)

There are quite a few functions in PHP which you can call with more
than one name. In some cases there is no preferred name among the
multiple ones, [is\_int()](https://www.php.net/manual/en/function.is-int.php) and
[is\_integer()](https://www.php.net/manual/en/function.is-integer.php) are equally good for example.
However there are functions which changed names because of an API
cleanup or some other reason and the old names are only kept as
aliases for backward compatibility. It is usually a bad idea to use
these kind of aliases, as they may be bound to obsolescence or
renaming, which will lead to unportable script. This list is provided
to help those who want to upgrade their old scripts to newer syntax.


| Alias | Canonical function name | Extension used |
| --- | --- | --- |
| \_ | [gettext()](https://www.php.net/manual/en/function.gettext.php) | [Gettext](https://www.php.net/manual/en/ref.gettext.php) |
| chop | [rtrim()](https://www.php.net/manual/en/function.rtrim.php) | Base syntax |
| close | [closedir()](https://www.php.net/manual/en/function.closedir.php) | Base syntax |
| com\_get | **com\_propget()** | [COM](https://www.php.net/manual/en/ref.com.php) |
| com\_propset | **com\_propput()** | [COM](https://www.php.net/manual/en/ref.com.php) |
| com\_set | **com\_propput()** | [COM](https://www.php.net/manual/en/ref.com.php) |
| die | [exit()](https://www.php.net/manual/en/function.exit.php) | [Miscellaneous functions](https://www.php.net/manual/en/ref.misc.php) |
| diskfreespace | [disk\_free\_space()](https://www.php.net/manual/en/function.disk-free-space.php) | [Filesystem](https://www.php.net/manual/en/ref.filesystem.php) |
| doubleval | [floatval()](https://www.php.net/manual/en/function.floatval.php) | Base syntax |
| fputs | [fwrite()](https://www.php.net/manual/en/function.fwrite.php) | Base syntax |
| gzputs | [gzwrite()](https://www.php.net/manual/en/function.gzwrite.php) | [Zlib](https://www.php.net/manual/en/ref.zlib.php) |
| i18n\_convert | [mb\_convert\_encoding()](https://www.php.net/manual/en/function.mb-convert-encoding.php) | [Multi-bytes Strings](https://www.php.net/manual/en/ref.mbstring.php) |
| i18n\_discover\_encoding | [mb\_detect\_encoding()](https://www.php.net/manual/en/function.mb-detect-encoding.php) | [Multi-bytes Strings](https://www.php.net/manual/en/ref.mbstring.php) |
| i18n\_http\_input | [mb\_http\_input()](https://www.php.net/manual/en/function.mb-http-input.php) | [Multi-bytes Strings](https://www.php.net/manual/en/ref.mbstring.php) |
| i18n\_http\_output | [mb\_http\_output()](https://www.php.net/manual/en/function.mb-http-output.php) | [Multi-bytes Strings](https://www.php.net/manual/en/ref.mbstring.php) |
| i18n\_internal\_encoding | [mb\_internal\_encoding()](https://www.php.net/manual/en/function.mb-internal-encoding.php) | [Multi-bytes Strings](https://www.php.net/manual/en/ref.mbstring.php) |
| i18n\_ja\_jp\_hantozen | [mb\_convert\_kana()](https://www.php.net/manual/en/function.mb-convert-kana.php) | [Multi-bytes Strings](https://www.php.net/manual/en/ref.mbstring.php) |
| i18n\_mime\_header\_decode | [mb\_decode\_mimeheader()](https://www.php.net/manual/en/function.mb-decode-mimeheader.php) | [Multi-bytes Strings](https://www.php.net/manual/en/ref.mbstring.php) |
| i18n\_mime\_header\_encode | [mb\_encode\_mimeheader()](https://www.php.net/manual/en/function.mb-encode-mimeheader.php) | [Multi-bytes Strings](https://www.php.net/manual/en/ref.mbstring.php) |
| imap\_create | [imap\_createmailbox()](https://www.php.net/manual/en/function.imap-createmailbox.php) | [IMAP](https://www.php.net/manual/en/ref.imap.php) |
| imap\_fetchtext | [imap\_body()](https://www.php.net/manual/en/function.imap-body.php) | [IMAP](https://www.php.net/manual/en/ref.imap.php) |
| imap\_getmailboxes | **imap\_list\_full()** | [IMAP](https://www.php.net/manual/en/ref.imap.php) |
| imap\_getsubscribed | **imap\_lsub\_full()** | [IMAP](https://www.php.net/manual/en/ref.imap.php) |
| imap\_header | [imap\_headerinfo()](https://www.php.net/manual/en/function.imap-headerinfo.php) | [IMAP](https://www.php.net/manual/en/ref.imap.php) |
| imap\_listmailbox | [imap\_list()](https://www.php.net/manual/en/function.imap-list.php) | [IMAP](https://www.php.net/manual/en/ref.imap.php) |
| imap\_listsubscribed | [imap\_lsub()](https://www.php.net/manual/en/function.imap-lsub.php) | [IMAP](https://www.php.net/manual/en/ref.imap.php) |
| imap\_rename | [imap\_renamemailbox()](https://www.php.net/manual/en/function.imap-renamemailbox.php) | [IMAP](https://www.php.net/manual/en/ref.imap.php) |
| imap\_scan | [imap\_listscan()](https://www.php.net/manual/en/function.imap-listscan.php) | [IMAP](https://www.php.net/manual/en/ref.imap.php) |
| imap\_scanmailbox | [imap\_listscan()](https://www.php.net/manual/en/function.imap-listscan.php) | [IMAP](https://www.php.net/manual/en/ref.imap.php) |
| ini\_alter | [ini\_set()](https://www.php.net/manual/en/function.ini-set.php) | Base syntax |
| is\_double | [is\_float()](https://www.php.net/manual/en/function.is-float.php) | Base syntax |
| is\_integer | [is\_int()](https://www.php.net/manual/en/function.is-int.php) | Base syntax |
| is\_long | [is\_int()](https://www.php.net/manual/en/function.is-int.php) | Base syntax |
| is\_real | [is\_float()](https://www.php.net/manual/en/function.is-float.php) | Base syntax |
| is\_writeable | [is\_writable()](https://www.php.net/manual/en/function.is-writable.php) | Base syntax |
| join | [implode()](https://www.php.net/manual/en/function.implode.php) | Base syntax |
| key\_exists | [array\_key\_exists()](https://www.php.net/manual/en/function.array-key-exists.php) | Base syntax |
| ldap\_close | [ldap\_unbind()](https://www.php.net/manual/en/function.ldap-unbind.php) | [LDAP](https://www.php.net/manual/en/ref.ldap.php) |
| mbstrcut | [mb\_strcut()](https://www.php.net/manual/en/function.mb-strcut.php) | [Multi-bytes Strings](https://www.php.net/manual/en/ref.mbstring.php) |
| mbstrlen | [mb\_strlen()](https://www.php.net/manual/en/function.mb-strlen.php) | [Multi-bytes Strings](https://www.php.net/manual/en/ref.mbstring.php) |
| mbstrpos | [mb\_strpos()](https://www.php.net/manual/en/function.mb-strpos.php) | [Multi-bytes Strings](https://www.php.net/manual/en/ref.mbstring.php) |
| mbstrrpos | [mb\_strrpos()](https://www.php.net/manual/en/function.mb-strrpos.php) | [Multi-bytes Strings](https://www.php.net/manual/en/ref.mbstring.php) |
| mbsubstr | [mb\_substr()](https://www.php.net/manual/en/function.mb-substr.php) | [Multi-bytes Strings](https://www.php.net/manual/en/ref.mbstring.php) |
| mysql | [mysql\_db\_query()](https://www.php.net/manual/en/function.mysql-db-query.php) | [MySQL](https://www.php.net/manual/en/ref.mysql.php) |
| mysql\_createdb | [mysql\_create\_db()](https://www.php.net/manual/en/function.mysql-create-db.php) | [MySQL](https://www.php.net/manual/en/ref.mysql.php) |
| mysql\_db\_name | [mysql\_result()](https://www.php.net/manual/en/function.mysql-result.php) | [MySQL](https://www.php.net/manual/en/ref.mysql.php) |
| mysql\_dbname | [mysql\_result()](https://www.php.net/manual/en/function.mysql-result.php) | [MySQL](https://www.php.net/manual/en/ref.mysql.php) |
| mysql\_dropdb | [mysql\_drop\_db()](https://www.php.net/manual/en/function.mysql-drop-db.php) | [MySQL](https://www.php.net/manual/en/ref.mysql.php) |
| mysql\_fieldflags | [mysql\_field\_flags()](https://www.php.net/manual/en/function.mysql-field-flags.php) | [MySQL](https://www.php.net/manual/en/ref.mysql.php) |
| mysql\_fieldlen | [mysql\_field\_len()](https://www.php.net/manual/en/function.mysql-field-len.php) | [MySQL](https://www.php.net/manual/en/ref.mysql.php) |
| mysql\_fieldname | [mysql\_field\_name()](https://www.php.net/manual/en/function.mysql-field-name.php) | [MySQL](https://www.php.net/manual/en/ref.mysql.php) |
| mysql\_fieldtable | [mysql\_field\_table()](https://www.php.net/manual/en/function.mysql-field-table.php) | [MySQL](https://www.php.net/manual/en/ref.mysql.php) |
| mysql\_fieldtype | [mysql\_field\_type()](https://www.php.net/manual/en/function.mysql-field-type.php) | [MySQL](https://www.php.net/manual/en/ref.mysql.php) |
| mysql\_freeresult | [mysql\_free\_result()](https://www.php.net/manual/en/function.mysql-free-result.php) | [MySQL](https://www.php.net/manual/en/ref.mysql.php) |
| mysql\_listdbs | [mysql\_list\_dbs()](https://www.php.net/manual/en/function.mysql-list-dbs.php) | [MySQL](https://www.php.net/manual/en/ref.mysql.php) |
| mysql\_listfields | [mysql\_list\_fields()](https://www.php.net/manual/en/function.mysql-list-fields.php) | [MySQL](https://www.php.net/manual/en/ref.mysql.php) |
| mysql\_listtables | [mysql\_list\_tables()](https://www.php.net/manual/en/function.mysql-list-tables.php) | [MySQL](https://www.php.net/manual/en/ref.mysql.php) |
| mysql\_numfields | [mysql\_num\_fields()](https://www.php.net/manual/en/function.mysql-num-fields.php) | [MySQL](https://www.php.net/manual/en/ref.mysql.php) |
| mysql\_numrows | [mysql\_num\_rows()](https://www.php.net/manual/en/function.mysql-num-rows.php) | [MySQL](https://www.php.net/manual/en/ref.mysql.php) |
| mysql\_selectdb | [mysql\_select\_db()](https://www.php.net/manual/en/function.mysql-select-db.php) | [MySQL](https://www.php.net/manual/en/ref.mysql.php) |
| mysql\_tablename | [mysql\_result()](https://www.php.net/manual/en/function.mysql-result.php) | [MySQL](https://www.php.net/manual/en/ref.mysql.php) |
| ociassignelem | [OCICollection::assignElem](https://www.php.net/manual/en/ocicollection.assignelem.php) | [OCI8](https://www.php.net/manual/en/ref.oci8.php) |
| ocibindbyname | [oci\_bind\_by\_name()](https://www.php.net/manual/en/function.oci-bind-by-name.php) | [OCI8](https://www.php.net/manual/en/ref.oci8.php) |
| ocicancel | [oci\_cancel()](https://www.php.net/manual/en/function.oci-cancel.php) | [OCI8](https://www.php.net/manual/en/ref.oci8.php) |
| ocicloselob | [OCILob::close](https://www.php.net/manual/en/ocilob.close.php) | [OCI8](https://www.php.net/manual/en/ref.oci8.php) |
| ocicollappend | [OCICollection::append](https://www.php.net/manual/en/ocicollection.append.php) | [OCI8](https://www.php.net/manual/en/ref.oci8.php) |
| ocicollassign | [OCICollection::assign](https://www.php.net/manual/en/ocicollection.assign.php) | [OCI8](https://www.php.net/manual/en/ref.oci8.php) |
| ocicollmax | [OCICollection::max](https://www.php.net/manual/en/ocicollection.max.php) | [OCI8](https://www.php.net/manual/en/ref.oci8.php) |
| ocicollsize | [OCICollection::size](https://www.php.net/manual/en/ocicollection.size.php) | [OCI8](https://www.php.net/manual/en/ref.oci8.php) |
| ocicolltrim | [OCICollection::trim](https://www.php.net/manual/en/ocicollection.trim.php) | [OCI8](https://www.php.net/manual/en/ref.oci8.php) |
| ocicolumnisnull | [oci\_field\_is\_null()](https://www.php.net/manual/en/function.oci-field-is-null.php) | [OCI8](https://www.php.net/manual/en/ref.oci8.php) |
| ocicolumnname | [oci\_field\_name()](https://www.php.net/manual/en/function.oci-field-name.php) | [OCI8](https://www.php.net/manual/en/ref.oci8.php) |
| ocicolumnprecision | [oci\_field\_precision()](https://www.php.net/manual/en/function.oci-field-precision.php) | [OCI8](https://www.php.net/manual/en/ref.oci8.php) |
| ocicolumnscale | [oci\_field\_scale()](https://www.php.net/manual/en/function.oci-field-scale.php) | [OCI8](https://www.php.net/manual/en/ref.oci8.php) |
| ocicolumnsize | [oci\_field\_size()](https://www.php.net/manual/en/function.oci-field-size.php) | [OCI8](https://www.php.net/manual/en/ref.oci8.php) |
| ocicolumntype | [oci\_field\_type()](https://www.php.net/manual/en/function.oci-field-type.php) | [OCI8](https://www.php.net/manual/en/ref.oci8.php) |
| ocicolumntyperaw | [oci\_field\_type\_raw()](https://www.php.net/manual/en/function.oci-field-type-raw.php) | [OCI8](https://www.php.net/manual/en/ref.oci8.php) |
| ocicommit | [oci\_commit()](https://www.php.net/manual/en/function.oci-commit.php) | [OCI8](https://www.php.net/manual/en/ref.oci8.php) |
| ocidefinebyname | [oci\_define\_by\_name()](https://www.php.net/manual/en/function.oci-define-by-name.php) | [OCI8](https://www.php.net/manual/en/ref.oci8.php) |
| ocierror | [oci\_error()](https://www.php.net/manual/en/function.oci-error.php) | [OCI8](https://www.php.net/manual/en/ref.oci8.php) |
| ociexecute | [oci\_execute()](https://www.php.net/manual/en/function.oci-execute.php) | [OCI8](https://www.php.net/manual/en/ref.oci8.php) |
| ocifetch | [oci\_fetch()](https://www.php.net/manual/en/function.oci-fetch.php) | [OCI8](https://www.php.net/manual/en/ref.oci8.php) |
| ocifetchinto | [oci\_fetch\_array()](https://www.php.net/manual/en/function.oci-fetch-array.php), [oci\_fetch\_row()](https://www.php.net/manual/en/function.oci-fetch-row.php), [oci\_fetch\_assoc()](https://www.php.net/manual/en/function.oci-fetch-assoc.php), [oci\_fetch\_object()](https://www.php.net/manual/en/function.oci-fetch-object.php) | [OCI8](https://www.php.net/manual/en/ref.oci8.php) |
| ocifetchstatement | [oci\_fetch\_all()](https://www.php.net/manual/en/function.oci-fetch-all.php) | [OCI8](https://www.php.net/manual/en/ref.oci8.php) |
| ocifreecollection | [OCICollection::free](https://www.php.net/manual/en/ocicollection.free.php) | [OCI8](https://www.php.net/manual/en/ref.oci8.php) |
| ocifreecursor | [oci\_free\_statement()](https://www.php.net/manual/en/function.oci-free-statement.php) | [OCI8](https://www.php.net/manual/en/ref.oci8.php) |
| ocifreedesc | [oci\_free\_descriptor()](https://www.php.net/manual/en/function.oci-free-descriptor.php) | [OCI8](https://www.php.net/manual/en/ref.oci8.php) |
| ocifreestatement | [oci\_free\_statement()](https://www.php.net/manual/en/function.oci-free-statement.php) | [OCI8](https://www.php.net/manual/en/ref.oci8.php) |
| ocigetelem | [OCICollection::getElem](https://www.php.net/manual/en/ocicollection.getelem.php) | [OCI8](https://www.php.net/manual/en/ref.oci8.php) |
| ociinternaldebug | [oci\_internal\_debug()](https://www.php.net/manual/en/function.oci-internal-debug.php) | [OCI8](https://www.php.net/manual/en/ref.oci8.php) |
| ociloadlob | [OCILob::load](https://www.php.net/manual/en/ocilob.load.php) | [OCI8](https://www.php.net/manual/en/ref.oci8.php) |
| ocilogon | [oci\_connect()](https://www.php.net/manual/en/function.oci-connect.php) | [OCI8](https://www.php.net/manual/en/ref.oci8.php) |
| ocinewcollection | [oci\_new\_collection()](https://www.php.net/manual/en/function.oci-new-collection.php) | [OCI8](https://www.php.net/manual/en/ref.oci8.php) |
| ocinewcursor | [oci\_new\_cursor()](https://www.php.net/manual/en/function.oci-new-cursor.php) | [OCI8](https://www.php.net/manual/en/ref.oci8.php) |
| ocinewdescriptor | [oci\_new\_descriptor()](https://www.php.net/manual/en/function.oci-new-descriptor.php) | [OCI8](https://www.php.net/manual/en/ref.oci8.php) |
| ocinlogon | [oci\_new\_connect()](https://www.php.net/manual/en/function.oci-new-connect.php) | [OCI8](https://www.php.net/manual/en/ref.oci8.php) |
| ocinumcols | [oci\_num\_fields()](https://www.php.net/manual/en/function.oci-num-fields.php) | [OCI8](https://www.php.net/manual/en/ref.oci8.php) |
| ociparse | [oci\_parse()](https://www.php.net/manual/en/function.oci-parse.php) | [OCI8](https://www.php.net/manual/en/ref.oci8.php) |
| ocipasswordchange | [oci\_password\_change()](https://www.php.net/manual/en/function.oci-password-change.php) | [OCI8](https://www.php.net/manual/en/ref.oci8.php) |
| ociplogon | [oci\_pconnect()](https://www.php.net/manual/en/function.oci-pconnect.php) | [OCI8](https://www.php.net/manual/en/ref.oci8.php) |
| ociresult | [oci\_result()](https://www.php.net/manual/en/function.oci-result.php) | [OCI8](https://www.php.net/manual/en/ref.oci8.php) |
| ocirollback | [oci\_rollback()](https://www.php.net/manual/en/function.oci-rollback.php) | [OCI8](https://www.php.net/manual/en/ref.oci8.php) |
| ocisavelob | [OCILob::save](https://www.php.net/manual/en/ocilob.save.php) | [OCI8](https://www.php.net/manual/en/ref.oci8.php) |
| ocisavelobfile | [OCILob::import](https://www.php.net/manual/en/ocilob.import.php) | [OCI8](https://www.php.net/manual/en/ref.oci8.php) |
| ociserverversion | [oci\_server\_version()](https://www.php.net/manual/en/function.oci-server-version.php) | [OCI8](https://www.php.net/manual/en/ref.oci8.php) |
| ocisetprefetch | [oci\_set\_prefetch()](https://www.php.net/manual/en/function.oci-set-prefetch.php) | [OCI8](https://www.php.net/manual/en/ref.oci8.php) |
| ocistatementtype | [oci\_statement\_type()](https://www.php.net/manual/en/function.oci-statement-type.php) | [OCI8](https://www.php.net/manual/en/ref.oci8.php) |
| ociwritelobtofile | [OCILob::export](https://www.php.net/manual/en/ocilob.export.php) | [OCI8](https://www.php.net/manual/en/ref.oci8.php) |
| ociwritetemporarylob | [OCILob::writeTemporary](https://www.php.net/manual/en/ocilob.writetemporary.php) | [OCI8](https://www.php.net/manual/en/ref.oci8.php) |
| odbc\_do | [odbc\_exec()](https://www.php.net/manual/en/function.odbc-exec.php) | [ODBC](https://www.php.net/manual/en/ref.uodbc.php) |
| odbc\_field\_precision | [odbc\_field\_len()](https://www.php.net/manual/en/function.odbc-field-len.php) | [ODBC](https://www.php.net/manual/en/ref.uodbc.php) |
| pg\_clientencoding | [pg\_client\_encoding()](https://www.php.net/manual/en/function.pg-client-encoding.php) | [PostgreSQL](https://www.php.net/manual/en/ref.pgsql.php) |
| pg\_setclientencoding | [pg\_set\_client\_encoding()](https://www.php.net/manual/en/function.pg-set-client-encoding.php) | [PostgreSQL](https://www.php.net/manual/en/ref.pgsql.php) |
| pos | [current()](https://www.php.net/manual/en/function.current.php) | Base syntax |
| recode | [recode\_string()](https://www.php.net/manual/en/function.recode-string.php) | [Recode](https://www.php.net/manual/en/ref.recode.php) |
| show\_source | [highlight\_file()](https://www.php.net/manual/en/function.highlight-file.php) | Base syntax |
| sizeof | [count()](https://www.php.net/manual/en/function.count.php) | Base syntax |
| snmpwalkoid | [snmprealwalk()](https://www.php.net/manual/en/function.snmprealwalk.php) | [SNMP](https://www.php.net/manual/en/ref.snmp.php) |
| strchr | [strstr()](https://www.php.net/manual/en/function.strstr.php) | Base syntax |

**Aliases**

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/appendices/aliases.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Faliases%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=aliases&repo=en&redirect=https://www.php.net/manual/en/aliases.php)

### User Contributed Notes

There are no user contributed notes for this page.

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google