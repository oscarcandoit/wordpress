---
url: https://developer.wordpress.org/cli/commands/config/
scraped_at: 2025-10-20T03:01:22.375Z
---

[Skip to content](https://developer.wordpress.org/cli/commands/config/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

wp config


[Home](https://developer.wordpress.org/)[WP-CLI Commands](https://developer.wordpress.org/cli/commands/)wp config

Search

# [wp config\  <command>](https://developer.wordpress.org/cli/commands/config/)

Generates and reads the wp-config.php file.

## In this article

Table of Contents

- [Examples](https://developer.wordpress.org/cli/commands/config/#examples)
- [Subcommands](https://developer.wordpress.org/cli/commands/config/#subcommands)

[↑ Back to top](https://developer.wordpress.org/cli/commands/config/#wp--skip-link--target)

[![GitHub](https://make.wordpress.org/cli/wp-content/plugins/wporg-cli/assets/images/github-mark.svg)](https://github.com/wp-cli/config-command)

[View Open Issues](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Aconfig+sort%3Aupdated-desc+org%3Awp-cli+is%3Aopen) [View Closed Issues](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Aconfig+sort%3Aupdated-desc+org%3Awp-cli+is%3Aclosed) [Create New Issue](https://github.com/wp-cli/config-command/issues/new)

### [Examples](https://developer.wordpress.org/cli/commands/config/\#examples)

```
# Create standard wp-config.php file.
$ wp config create --dbname=testing --dbuser=wp --dbpass=securepswd --locale=ro_RO
Success: Generated 'wp-config.php' file.

# List constants and variables defined in wp-config.php file.
$ wp config list
+------------------+------------------------------------------------------------------+----------+
| key              | value                                                            | type     |
+------------------+------------------------------------------------------------------+----------+
| table_prefix     | wp_                                                              | variable |
| DB_NAME          | wp_cli_test                                                      | constant |
| DB_USER          | root                                                             | constant |
| DB_PASSWORD      | root                                                             | constant |
| AUTH_KEY         | r6+@shP1yO&amp;$)1gdu.hl[/j;7Zrvmt~o;#WxSsa0mlQOi24j2cR,7i+QM/#7S:o^ | constant |\
| SECURE_AUTH_KEY  | iO-z!_m--YH$Tx2tf/&amp;V,YW*13Z_HiRLqi)d?$o-tMdY+82pK$`T.NYW~iTLW;xp | constant |\
+------------------+------------------------------------------------------------------+----------+\
\
# Get wp-config.php file path.\
$ wp config path\
/home/person/htdocs/project/wp-config.php\
\
# Get the table_prefix as defined in wp-config.php file.\
$ wp config get table_prefix\
wp_\
\
# Set the WP_DEBUG constant to true.\
$ wp config set WP_DEBUG true --raw\
Success: Updated the constant 'WP_DEBUG' in the 'wp-config.php' file with the raw value 'true'.\
\
# Delete the COOKIE_DOMAIN constant from the wp-config.php file.\
$ wp config delete COOKIE_DOMAIN\
Success: Deleted the constant 'COOKIE_DOMAIN' from the 'wp-config.php' file.\
\
# Launch system editor to edit wp-config.php file.\
$ wp config edit\
\
# Check whether the DB_PASSWORD constant exists in the wp-config.php file.\
$ wp config has DB_PASSWORD\
$ echo $?\
0\
\
# Assert if MULTISITE is true.\
$ wp config is-true MULTISITE\
$ echo $?\
0\
\
# Get new salts for your wp-config.php file.\
$ wp config shuffle-salts\
Success: Shuffled the salt keys.\
\
```\
\
### [Subcommands](https://developer.wordpress.org/cli/commands/config/\#subcommands)\
\
| Name | Description |\
| --- | --- |\
| [wp config create](https://developer.wordpress.org/cli/commands/config/create/) | Generates a wp-config.php file. |\
| [wp config delete](https://developer.wordpress.org/cli/commands/config/delete/) | Deletes a specific constant or variable from the wp-config.php file. |\
| [wp config edit](https://developer.wordpress.org/cli/commands/config/edit/) | Launches system editor to edit the wp-config.php file. |\
| [wp config get](https://developer.wordpress.org/cli/commands/config/get/) | Gets the value of a specific constant or variable defined in wp-config.php file. |\
| [wp config has](https://developer.wordpress.org/cli/commands/config/has/) | Checks whether a specific constant or variable exists in the wp-config.php file. |\
| [wp config is-true](https://developer.wordpress.org/cli/commands/config/is-true/) | Determines whether value of a specific defined constant or variable is truthy. |\
| [wp config list](https://developer.wordpress.org/cli/commands/config/list/) | Lists variables, constants, and file includes defined in wp-config.php file. |\
| [wp config path](https://developer.wordpress.org/cli/commands/config/path/) | Gets the path to wp-config.php file. |\
| [wp config set](https://developer.wordpress.org/cli/commands/config/set/) | Sets the value of a specific constant or variable defined in wp-config.php file. |\
| [wp config shuffle-salts](https://developer.wordpress.org/cli/commands/config/shuffle-salts/) | Refreshes the salts defined in the wp-config.php file. |\
\
_Command documentation is regenerated at every release. To add or update an example, please submit a pull request against the corresponding part of the codebase._\
\
Notifications