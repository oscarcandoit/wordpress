---
url: https://make.wordpress.org/cli/
scraped_at: 2025-10-20T03:02:25.451Z
---

[Skip to content](https://make.wordpress.org/cli/#primary)

- [Log In](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fmake.wordpress.org%2Fcli%2F&locale=en_US)
- [Register](https://login.wordpress.org/register?locale=en_US)

[WordPress.org](https://wordpress.org/)

# [WP-CLI](https://make.wordpress.org/cli)

[**Menu**](https://make.wordpress.org/cli/#)

Hide welcome box

#### Welcome to WP-CLI!

WP-CLI is the official command line tool for interacting with and managing your WordPress sites.

Need help with something? Please [review your available support options](http://wp-cli.org/#support).

Want to help make it better? Check out our [Contributing guide](https://make.wordpress.org/cli/handbook/contributing/) for an introduction, or “ [good first issues](https://github.com/search?q=org%3Awp-cli+label%3Agood-first-issue+is%3Aissue+is%3Aopen&type=issues)” for your first pull request.

#### Contact

The WP-CLI team communicates on [Slack](https://chat.wordpress.org/), in the [#cli](http://wordpress.slack.com/messages/cli/) channel.

There are currently no scheduled office hours, so feel free to chime in whenever.

[![](https://gravatar.com/avatar/d860ed93c93910d7f5c21458a3f4d190?d=mystery)](https://profiles.wordpress.org/peiraisotta/ "Profile of Isotta Peira (@peiraisotta)")

[Isotta Peira](https://profiles.wordpress.org/peiraisotta/ "Profile of Isotta Peira (@peiraisotta)") [9:06 am on June 23, 2025](https://make.wordpress.org/cli/2025/06/23/xpost-the-incident-response-team-is-looking-for-new-members/ "9:06 am (-04:00) on June 23, 2025")

## X-comment from [+make.wordpress.org/community](https://make.wordpress.org/community/ "Make WordPress Community"): Comment on [The Incident Response Team is looking for new members](https://make.wordpress.org/community/2025/06/23/the-incident-response-team-is-looking-for-new-members/\#comment-32528 "We’re expanding the Incident Response Team (IRT) and are looking for new contributors to join us. The mission of the IRT is to provide a clear channel for community members to report and address incidents that may violate the WordPress Community Code of Conduct, ensuring a safe and respectful environment for all participants. If you’re committed to fostering a respectful community and have experience in community moderation, conflict resolution, or DEIB practices, we’d love to hear from you. Apply here You can also open the application form using the following link: https://wordpressdotorg.survey.fm/wordpress-incident-response-team-%E2%80%93-application-formApplications will remain open until July 6, 2025. Selected members will receive dedicated training and onboarding. To create more oppo…")

A new release of WP-CLI, **WP-CLI v2.12.0**, is now available. For this release, we had **68 contributors** collaborate to get **382 pull requests** merged.

As always, big thanks to the [WP-CLI sponsors](https://make.wordpress.org/cli/sponsors/) that make the continued maintenance possible.

This release includes numerous bug fixes and compatibility improvements, but we still could teach WP-CLI a few new tricks which I’ll highlight below. As always, you can also skip directly to the [detailed changelog](https://make.wordpress.org/cli/#changelog) if you prefer.

If you already use WP-CLI, updating is as simple as `wp cli update`. Else, check out our website for [recommended installation methods](https://wp-cli.org/#installing).

### Pluck & patch commands for caches and transients

The `cache` and `transient` commands have now also learned the subtle art of plucking and patching. This means that you can directly manipulate individual entries in an array of values that these commands let you manage.

Here’s an example of how such an operation can look and how it compare to the regular cache/transient operations:

```
# Transient structure
# 'some_key' => ['foo' => ['bar' => 'baz']]

# Retrieve the transient value
$ wp transient get some_key --format=json
{'foo':{'bar':'baz'}}

# Retrieve the value of the foo => bar subkey
$ wp transient pluck some_key foo bar
baz

# Replace baz with bazzer
$ wp transient patch update some_key foo bar bazzer
Success: Updated transient 'some_key'.
```

### Post lists can now handle complex query flags

When using `post list`, you can now use JSON notation to provide complex query arguments to the `--tax_query`, `--meta_query` and `--post_date` fields.

```
$ wp post list --field=post_title --date_query='{"before":{"year":"2024"}}
+--------------------------+
| post_title               |
+--------------------------+
| My year in review - 2021 |
| My year in review - 2022 |
| My year in review - 2023 |
+--------------------------+

$ wp post list --field=post_title --tax_query='[{"taxonomy":"category","field":"slug","terms":"first-category"}]'
...

$ wp post list --field=post_title --meta_query='[{"key":"key2","value":"value2b"}]'
...
```

### Post meta can be forced to only return a single value

The `post meta get` command now has a `--single` flag defaulting to `true` which can be negated with `--no-single`. This flag tells WordPress whether to only return a single value or all existing values for a given key.

```
# Create a post meta key for post with ID 123 that has multiple values
$ wp post meta add 123 my_meta_key value_1
$ wp post meta add 123 my_meta_key value_2
$ wp post meta add 123 my_meta_key value_4

# Retrieve a single value
$ wp post meta get 123 my_meta_key --single
value_1

# Retrieve all values
$ wp post meta get 123 my_meta_key --no-single --format=json
["value_1","value_2","value_3"]
```

### Exclude files on `core checksum` verification

When running a `core checksum` verification, you can exclude one or more files from the checksum verification with the new `--exclude=<files>` flag, which takes a comma-separated list of filepaths relative to the current root.

```
# Make a change to the README file in the WordPress core root folder
$ echo "nonsense" > readme.html

# Run the core checksum verification
$ wp core verify-checksums --exclude='readme.html'
Success: WordPress installation verifies against checksums.
```

### Respect `requires` and `requires_php` tags for plugins and themes

The plugin and theme commands now understand and respect the `requires` and `requires_php` header tags when trying ot install or update extensions. A new state `unavailable` has been introduced to denote the updates that are newer that your current installation but for which your site does not fulfill the requirements.

This also adds new fields `requires` and `requires_php` which are displayed if they contain relevant information and otherwise hidden by default.

```
$ wp plugin list
+----------------+----------+-------------+---------+----------------+-------------+----------+--------------+
| name           | status   | update      | version | update_version | auto_update | requires | requires_php |
+----------------+----------+-------------+---------+----------------+-------------+----------+--------------+
| akismet        | inactive | available   | 5.1     | 5.3.5          | off         | 5.8      | 5.6.20       |
| edit-flow      | inactive | none        | 0.9.9   |                | off         | 6.0      | 8.0          |
| wp-super-cache | inactive | unavailable | 1.9.4   | 1.12.4         | off         | 6.5      | 7.0          |
+----------------+----------+-------------+---------+----------------+-------------+----------+--------------+

$ wp plugin update wp-super-cache
Warning: wp-super-cache: This update requires WordPress version 6.5, but the version installed is 6.2.
Error: No plugins updated.
```

### More control over `make-json` generation

The `make-json` command was made more powerful again. You can not only set a custom text domain to be used, you can also define the file extension to parse.

```
# Use a custom text domain
$ wp i18n make-json foo-theme --domain=my-custom-domain
Success: Created 1 file.

# Include typescript files
$ wp i18n make-json foo-theme --extensions=".ts, .tsx"
Success: Created 2 files.
```

### Force update checks on `plugin|theme list`

When displaying the list of plugins or themes, WP-CLI now always ensures you get fresh data. No need to manually clear transients anymore! The existing `--skip-update-check` flag can be used to prevent this behavior.

```
# Clears any update transients to trigger an update check and display results
$ wp plugin list --fields=name,status,update --force-check
+-------------+----------+--------+
| name        | status   | update |
+-------------+----------+--------+
| hello-dolly | inactive | none   |
+-------------+----------+--------+
```

### PHP 8.4 Compatiblity

WP-CLI is now fully compatible with PHP 8.4. This has required quite a bit of trickery and hacks to maintain compatibility with our current minimum of PHP 5.6+ at the same time. With the next release, we’ll bump the minimum PHP version to 7.2.24+, which will allow us to get rid of all these workarounds again.

### Detailed Change Log

#### [wp-cli/wp-cli-bundle](https://github.com/wp-cli/wp-cli-bundle/)

- Fix Phar path resolution with renamed binaries \[ [#752](https://github.com/wp-cli/wp-cli-bundle/pull/752)\]
- Deployment: Fix `FILENAME` env var \[ [#696](https://github.com/wp-cli/wp-cli-bundle/pull/696)\]
- Address deprecation warnings in Behat tests \[ [#663](https://github.com/wp-cli/wp-cli-bundle/pull/663)\]

#### [wp-cli/wp-cli](https://github.com/wp-cli/wp-cli/)

- Replace `duplicate-post` plugin with `debug-bar` in feature tests \[ [#6091](https://github.com/wp-cli/wp-cli/pull/6091)\]
- Use forked `mustache` library \[ [#6090](https://github.com/wp-cli/wp-cli/pull/6090)\]
- Escape CSV output \[ [#6089](https://github.com/wp-cli/wp-cli/pull/6089)\]
- Make sure existing `esc_like()` takes precedence \[ [#6088](https://github.com/wp-cli/wp-cli/pull/6088)\]
- Set `display_errors` to `stderr` (lowercase) instead of `STDERR` \[ [#6084](https://github.com/wp-cli/wp-cli/pull/6084)\]
- Fix update step for nightlies \[ [#6075](https://github.com/wp-cli/wp-cli/pull/6075)\]
- Detect MariaDB vs MySQL \[ [#6072](https://github.com/wp-cli/wp-cli/pull/6072)\]
- Update WP-CLI update message \[ [#6071](https://github.com/wp-cli/wp-cli/pull/6071)\]
- Add `WP_CLI_REQUIRE` environment variable for including extra PHP files \[ [#6070](https://github.com/wp-cli/wp-cli/pull/6070)\]
- Remove `array_column()` compatibility function \[ [#6068](https://github.com/wp-cli/wp-cli/pull/6068)\]
- Support multiple files in `WP_CLI_EARLY_REQUIRE` \[ [#6065](https://github.com/wp-cli/wp-cli/pull/6065)\]
- Properly create missing WP-CLI configuration file when needed \[ [#6062](https://github.com/wp-cli/wp-cli/pull/6062)\]
- Improve command suggestions for taxonomies and post types \[ [#6059](https://github.com/wp-cli/wp-cli/pull/6059)\]
- Fix undefined variable issue \[ [#6058](https://github.com/wp-cli/wp-cli/pull/6058)\]
- Pass `working-directory` and `stdin` to docker scheme \[ [#5974](https://github.com/wp-cli/wp-cli/pull/5974)\] & \[ [#6057](https://github.com/wp-cli/wp-cli/pull/6057)\]
- Add test for line breaks in table view \[ [#6055](https://github.com/wp-cli/wp-cli/pull/6055)\]
- Ensure code after `wp-settings.php` call is loaded \[ [#6042](https://github.com/wp-cli/wp-cli/pull/6042)\]
- Allow collecting PHPUnit coverage \[ [#6041](https://github.com/wp-cli/wp-cli/pull/6041)\]
- don’t forcefully `exec()` `docker version` \[ [#6040](https://github.com/wp-cli/wp-cli/pull/6040)\]
- Improve regular expression for detecting `wp-settings.php` \[ [#6039](https://github.com/wp-cli/wp-cli/pull/6039)\]
- Check PHP version requirement in update check \[ [#6037](https://github.com/wp-cli/wp-cli/pull/6037)\]
- Add hook to `http_request()` utility function \[ [#6036](https://github.com/wp-cli/wp-cli/pull/6036)\]
- Add PHPDoc for `cmd_starts_with()` method \[ [#6034](https://github.com/wp-cli/wp-cli/pull/6034)\]
- Update expected error message in unit tests \[ [#6032](https://github.com/wp-cli/wp-cli/pull/6032)\]
- Update outdated AJAX documentation link \[ [#6031](https://github.com/wp-cli/wp-cli/pull/6031)\]
- Add global documentation \[ [#6017](https://github.com/wp-cli/wp-cli/pull/6017)\]
- Allow remote binary customization \[ [#6013](https://github.com/wp-cli/wp-cli/pull/6013)\]
- Add configurable user agent to WP-CLI to detect in firewall logs \[ [#5998](https://github.com/wp-cli/wp-cli/pull/5998)\]
- Convert PHPUnit deprecations into exceptions \[ [#5994](https://github.com/wp-cli/wp-cli/pull/5994)\]
- Remove unused automerge workflow \[ [#5992](https://github.com/wp-cli/wp-cli/pull/5992)\]
- Fix CSV escaping deprecation notices \[ [#5991](https://github.com/wp-cli/wp-cli/pull/5991)\]
- Check for root earlier \[ [#5987](https://github.com/wp-cli/wp-cli/pull/5987)\]
- Remove use of `E_STRICT` for `wp_debug_mode()` \[ [#5986](https://github.com/wp-cli/wp-cli/pull/5986)\]
- Fix deprecation notices for `ReflectionProperty::setValue()` \[ [#5984](https://github.com/wp-cli/wp-cli/pull/5984)\]
- Fix “missing return type” deprecation warnings in `WP_CLI\Iterators\CSV` \[ [#5983](https://github.com/wp-cli/wp-cli/pull/5983)\]
- Fix implicitly nullable parameters \[ [#5982](https://github.com/wp-cli/wp-cli/pull/5982)\]
- Update Requests to v2.0.12 \[ [#5981](https://github.com/wp-cli/wp-cli/pull/5981)\]
- Update log and warning logger functions comment according to the actual functionality \[ [#5979](https://github.com/wp-cli/wp-cli/pull/5979)\]
- Add defaults and accepted values for `runcommand()` options in documentation \[ [#5953](https://github.com/wp-cli/wp-cli/pull/5953)\]

#### [wp-cli/handbook](https://github.com/wp-cli/handbook/)

- Update documentation to include new `WP_CLI_SSH_BINARY` value \[ [#559](https://github.com/wp-cli/handbook/pull/559)\]
- Add documentation for newly supported `ENV` vars \[ [#556](https://github.com/wp-cli/handbook/pull/556)\]
- Update URL for True-False Hosting \[ [#553](https://github.com/wp-cli/handbook/pull/553)\]

#### [wp-cli/cache-command](https://github.com/wp-cli/cache-command/)

- Fix expired transients tests \[ [#104](https://github.com/wp-cli/cache-command/pull/104)\]
- Allow manually dispatching tests workflow \[ [#99](https://github.com/wp-cli/cache-command/pull/99)\]
- Make transient test more robust against added transients by core \[ [#98](https://github.com/wp-cli/cache-command/pull/98)\]
- Add `pluck` & `patch` commands for caches and transients \[ [#89](https://github.com/wp-cli/cache-command/pull/89)\]

#### [wp-cli/checksum-command](https://github.com/wp-cli/checksum-command/)

- Add blank space when trimming the version \[ [#130](https://github.com/wp-cli/checksum-command/pull/130)\]
- Add `--exclude` argument for verifying checksums \[ [#123](https://github.com/wp-cli/checksum-command/pull/123)\]
- Remove unused variable \[ [#134](https://github.com/wp-cli/checksum-command/pull/134)\]
- Don’t check missing files \[ [#131](https://github.com/wp-cli/checksum-command/pull/131)\]

#### [wp-cli/config-command](https://github.com/wp-cli/config-command/)

- Don’t require file to be writable for `config has` \[ [#187](https://github.com/wp-cli/config-command/pull/187)\]
- Suppress output of `eval(get_wp_config_code)` preventing errors printing twice \[ [#188](https://github.com/wp-cli/config-command/pull/188)\]

#### [wp-cli/core-command](https://github.com/wp-cli/core-command/)

- Fix flaky tests due to changing download URL \[ [#277](https://github.com/wp-cli/core-command/pull/277)\]
- Allow installing major version with trailing zero \[ [#276](https://github.com/wp-cli/core-command/pull/276)\]
- Use existing `WpOrgApi` helper class \[ [#283](https://github.com/wp-cli/core-command/pull/283)\]
- Add doc comment for `$insecure` \[ [#281](https://github.com/wp-cli/core-command/pull/281)\]
- Host shouldn’t include `http://` \[ [#279](https://github.com/wp-cli/core-command/pull/279)\]

#### [wp-cli/cron-command](https://github.com/wp-cli/cron-command/)

- Harden test checking for log file \[ [#111](https://github.com/wp-cli/cron-command/pull/111)\]

#### [wp-cli/db-command](https://github.com/wp-cli/db-command/)

- Correct error message in `db search` for `--format=count` \[ [#267](https://github.com/wp-cli/db-command/pull/267)\]
- Update `db search` documentation \[ [#265](https://github.com/wp-cli/db-command/pull/265)\]
- Add `--add-drop-table` to `export` command options \[ [#263](https://github.com/wp-cli/db-command/pull/263)\]
- Improve MariaDB detection/compatibility \[ [#280](https://github.com/wp-cli/db-command/pull/280)\]
- Add affected rows count for queries that can modify data in `db query` \[ [#277](https://github.com/wp-cli/db-command/pull/277)\]
- Don’t hardcode MySQL command names \[ [#275](https://github.com/wp-cli/db-command/pull/275)\]

#### [wp-cli/entity-command](https://github.com/wp-cli/entity-command/)

- Add missing options header in `signup list` command \[ [#508](https://github.com/wp-cli/entity-command/pull/508)\]
- Ensure `user update` returns non-zero exit code for invalid users \[ [#527](https://github.com/wp-cli/entity-command/pull/527)\]
- Make `term-migrate` test more robust \[ [#524](https://github.com/wp-cli/entity-command/pull/524)\]
- Add a flag for getting post meta as a single value or not \[ [#523](https://github.com/wp-cli/entity-command/pull/523)\]
- Add JSON input support for `tax_query` and `meta_query` \[ [#522](https://github.com/wp-cli/entity-command/pull/522)\]
- Add JSON input support for `date_query` argument \[ [#520](https://github.com/wp-cli/entity-command/pull/520)\]
- `wp option` – new autoload values in autoload filter \[ [#515](https://github.com/wp-cli/entity-command/pull/515)\]
- Return a proper `WP_Error` object when failing to update a comment \[ [#514](https://github.com/wp-cli/entity-command/pull/514)\]
- Add test cases asserting `post/term update` error exit codes \[ [#513](https://github.com/wp-cli/entity-command/pull/513)\]
- Safeguard `remove cap` from collisions with roles \[ [#530](https://github.com/wp-cli/entity-command/pull/530)\]

#### [wp-cli/export-command](https://github.com/wp-cli/export-command/)

- Use `get_post_stati()` instead of `get_post_statuses()` to support all registered post statuses in export \[ [#121](https://github.com/wp-cli/export-command/pull/121)\]

#### [wp-cli/extension-command](https://github.com/wp-cli/extension-command/)

- Use `strpos()` instead of `str_contains()` in `get_wporg_data()` function \[ [#432](https://github.com/wp-cli/extension-command/pull/432)\]
- Don’t use transient values when doing `plugin|theme list` \[ [#446](https://github.com/wp-cli/extension-command/pull/446)\]
- Fix fatal error issue in `in_array()` function \[ [#445](https://github.com/wp-cli/extension-command/pull/445)\]
- Support `requires` and `requires_php` in `plugin|theme list` and `plugin|theme update` commands \[ [#440](https://github.com/wp-cli/extension-command/pull/440)\]
- Update logic when deleting and uninstalling plugins \[ [#438](https://github.com/wp-cli/extension-command/pull/438)\]
- Check WordPress and PHP requirements before installing a theme or plugin \[ [#436](https://github.com/wp-cli/extension-command/pull/436)\]
- Add `--force-check` flag to `wp plugin list` and `wp theme list`. \[ [#426](https://github.com/wp-cli/extension-command/pull/426)\]
- Cache certain GitHub URLs \[ [#385](https://github.com/wp-cli/extension-command/pull/385)\]

#### [wp-cli/i18n-command](https://github.com/wp-cli/i18n-command/)

- Convert PHPUnit deprecations to exceptions \[ [#413](https://github.com/wp-cli/i18n-command/pull/413)\]
- `make-pot`: scan any `theme.json` file in any level \[ [#424](https://github.com/wp-cli/i18n-command/pull/424)\]
- Add ability to pass extensions to `make-json` command \[ [#439](https://github.com/wp-cli/i18n-command/pull/439)\]
- Update schema fallback files \[ [#431](https://github.com/wp-cli/i18n-command/pull/431)\]
- `make-json`: Add new `--domain` argument \[ [#430](https://github.com/wp-cli/i18n-command/pull/430)\]
- `update-po`: merge `X-Domain` header \[ [#429](https://github.com/wp-cli/i18n-command/pull/429)\]
- Add `php-format` and `js-format` flags \[ [#428](https://github.com/wp-cli/i18n-command/pull/428)\]

#### [wp-cli/language-command](https://github.com/wp-cli/language-command/)

- Mention `site switch-language` in readme \[ [#159](https://github.com/wp-cli/language-command/pull/159)\]
- Allow filtering languages by multiple statuses \[ [#162](https://github.com/wp-cli/language-command/pull/162)\]

#### [wp-cli/php-cli-tools](https://github.com/wp-cli/php-cli-tools/)

- Example code: remove use of `E_STRICT` \[ [#175](https://github.com/wp-cli/php-cli-tools/pull/175)\]
- Fix implicitly nullable parameters \[ [#173](https://github.com/wp-cli/php-cli-tools/pull/173)\]
- Replace tabs in tables with 4 spaces \[ [#181](https://github.com/wp-cli/php-cli-tools/pull/181)\]
- Properly handle line breaks in column value \[ [#179](https://github.com/wp-cli/php-cli-tools/pull/179)\]
- Support line breaks and tab replacement in tabular table values \[ [#182](https://github.com/wp-cli/php-cli-tools/pull/182)\]
- Fix removal of trailing tab / whitespace in tabular table \[ [#184](https://github.com/wp-cli/php-cli-tools/pull/184)\]
- Avoid deprecation warnings in newer PHP \[ [#185](https://github.com/wp-cli/php-cli-tools/pull/185)\]

#### [wp-cli/rewrite-command](https://github.com/wp-cli/rewrite-command/)

- Improve warning message in `rewrite flush` \[ [#69](https://github.com/wp-cli/rewrite-command/pull/69)\]

#### [wp-cli/scaffold-command](https://github.com/wp-cli/scaffold-command/)

- Convert PHPUnit deprecations to exceptions \[ [#348](https://github.com/wp-cli/scaffold-command/pull/348)\]
- Add dependency checks and error handling for `svn` and download tools \[ [#345](https://github.com/wp-cli/scaffold-command/pull/345)\]
- Accept Bitbucket as valid CI in `scaffold plugin` \[ [#340](https://github.com/wp-cli/scaffold-command/pull/340)\]
- Update Bitbucket CI \[ [#339](https://github.com/wp-cli/scaffold-command/pull/339)\]
- Update templates for child theme scaffolding \[ [#342](https://github.com/wp-cli/scaffold-command/pull/342)\]
- Update custom post type and taxonomy scaffolding \[ [#341](https://github.com/wp-cli/scaffold-command/pull/341)\]
- Update GitLab CI configuration file \[ [#338](https://github.com/wp-cli/scaffold-command/pull/338)\]
- Remove `grunt` from plugin scaffolding \[ [#337](https://github.com/wp-cli/scaffold-command/pull/337)\]

#### [wp-cli/shell-command](https://github.com/wp-cli/shell-command/)

- Add missing `do` construct \[ [#68](https://github.com/wp-cli/shell-command/pull/68)\]

#### [wp-cli/wp-config-transformer](https://github.com/wp-cli/wp-config-transformer/)

- Add read-only option for `WPConfigTransformer` \[ [#54](https://github.com/wp-cli/wp-config-transformer/pull/54)\]
- Add a `branch-alias` for `dev-main` \[ [#55](https://github.com/wp-cli/wp-config-transformer/pull/55)\]
- Deletion of constants deletes more lines than expected \[ [#53](https://github.com/wp-cli/wp-config-transformer/pull/53)\]

### Contributors

[@9ete](https://github.com/9ete), [@amirhmoradi](https://github.com/amirhmoradi), [@baizmandesign](https://github.com/baizmandesign), [@benjaminprojas](https://github.com/benjaminprojas), [@BhargavBhandari90](https://github.com/BhargavBhandari90), [@cliffordp](https://github.com/cliffordp), [@daalderp](https://github.com/daalderp), [@dac514](https://github.com/dac514), [@danielbachhuber](https://github.com/danielbachhuber), [@dd32](https://github.com/dd32), [@dkoston](https://github.com/dkoston), [@dlind1](https://github.com/dlind1), [@drzraf](https://github.com/drzraf), [@elenachavdarova](https://github.com/elenachavdarova), [@ernilambar](https://github.com/ernilambar), [@gedex](https://github.com/gedex), [@gitlost](https://github.com/gitlost), [@greatislander](https://github.com/greatislander), [@herregroen](https://github.com/herregroen), [@i-am-chitti](https://github.com/i-am-chitti), [@iDschepe](https://github.com/iDschepe), [@imrraaj](https://github.com/imrraaj), [@itsmekopila](https://github.com/itsmekopila), [@janw-me](https://github.com/janw-me), [@jenkoian](https://github.com/jenkoian), [@jkrrv](https://github.com/jkrrv), [@jrfnl](https://github.com/jrfnl), [@karthick-murugan](https://github.com/karthick-murugan), [@l3ku](https://github.com/l3ku), [@localheinz](https://github.com/localheinz), [@marksabbath](https://github.com/marksabbath), [@matiasbenedetto](https://github.com/matiasbenedetto), [@matzeeable](https://github.com/matzeeable), [@meszarosrob](https://github.com/meszarosrob), [@michaelw85](https://github.com/michaelw85), [@michaelzangl](https://github.com/michaelzangl), [@mostafasoufi](https://github.com/mostafasoufi), [@mrsdizzie](https://github.com/mrsdizzie), [@oandregal](https://github.com/oandregal), [@ocean90](https://github.com/ocean90), [@ouikhuan](https://github.com/ouikhuan), [@PARTHVATALIYA](https://github.com/PARTHVATALIYA), [@pbiron](https://github.com/pbiron), [@peterwilsoncc](https://github.com/peterwilsoncc), [@petitphp](https://github.com/petitphp), [@pfefferle](https://github.com/pfefferle), [@pmbaldha](https://github.com/pmbaldha), [@ponsfrilus](https://github.com/ponsfrilus), [@pwtyler](https://github.com/pwtyler), [@ramonjd](https://github.com/ramonjd), [@rodrigoprimo](https://github.com/rodrigoprimo), [@Roy-Orbison](https://github.com/Roy-Orbison), [@saas786](https://github.com/saas786), [@sabithahmd](https://github.com/sabithahmd), [@sdnunca](https://github.com/sdnunca), [@shendy-a8c](https://github.com/shendy-a8c), [@shreya0204](https://github.com/shreya0204), [@siliconforks](https://github.com/siliconforks), [@strarsis](https://github.com/strarsis), [@swissspidy](https://github.com/swissspidy), [@todeveni](https://github.com/todeveni), [@Tug](https://github.com/Tug), [@tyrann0us](https://github.com/tyrann0us), [@wojsmol](https://github.com/wojsmol), [@wpeople-dev](https://github.com/wpeople-dev), [@WPprodigy](https://github.com/WPprodigy), [@yousan](https://github.com/yousan)

[#release](https://make.wordpress.org/cli/tag/release/), [#v2-12-0](https://make.wordpress.org/cli/tag/v2-12-0/)

Amazing

- [Login to Reply](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fmake.wordpress.org%2Fcli%2F2025%2F05%2F07%2Fwp-cli-v2-12-0-release-notes%2F%23comment-225&locale=en_US)

[![](https://gravatar.com/avatar/b2851597769206f4a8bfc53033c3ab18?d=mystery)](https://profiles.wordpress.org/harishanker/ "Profile of Hari Shanker R (@harishanker)")

[Hari Shanker R](https://profiles.wordpress.org/harishanker/ "Profile of Hari Shanker R (@harishanker)") [2:58 am on October 8, 2024](https://make.wordpress.org/cli/2024/10/08/xpost-announcing-the-third-cohort-2024-q4-of-the-wordpress-contributor-mentorship-program/ "2:58 am (-04:00) on October 8, 2024")

## X-post from [+make.wordpress.org/community](https://make.wordpress.org/community/ "Make WordPress Community"): [Announcing the Third Cohort (2024 Q4) of the WordPress Contributor Mentorship Program](https://make.wordpress.org/community/2024/10/08/announcing-the-third-cohort-2024-q4-of-the-wordpress-contributor-mentorship-program/ "The WordPress Contributor Working Group is thrilled to announce the launch of the third cohort of the WordPress Contributor Mentorship Program, that has kicked off on Monday, October 7th! This program offers newer WordPress enthusiasts  a unique opportunity to engage deeply with the project and make meaningful contributions by pairing them with experienced contributors (mentors) for a six-week period. Who are the Mentees? This cohort includes over 100 diverse contributors (mentees), each either paired with a mentor, involved in a task-focused project under the guidance of multiple mentors, or participating with a broader cohort group. These participants were selected from a pool of 150 applicants worldwide. All applicants should have received an email with the results of their applica…")

[![](https://gravatar.com/avatar/b2851597769206f4a8bfc53033c3ab18?d=mystery)](https://profiles.wordpress.org/harishanker/ "Profile of Hari Shanker R (@harishanker)")

[Hari Shanker R](https://profiles.wordpress.org/harishanker/ "Profile of Hari Shanker R (@harishanker)") [3:28 pm on August 16, 2024](https://make.wordpress.org/cli/2024/08/16/xpost-wordpress-contributor-mentorship-program-cohort-3-2024-q4-call-for-mentees-mentors/ "3:28 pm (-04:00) on August 16, 2024")

## X-post from [+make.wordpress.org/project](https://make.wordpress.org/project/ "WordPress.org Project"): [WordPress Contributor Mentorship Program Cohort \#3 (2024 Q4): Call for Mentees & Mentors](https://make.wordpress.org/project/2024/08/16/wordpress-contributor-mentorship-program-cohort-3-2024-q4-call-for-mentees-mentors/ "Following the success of our 2023 Q3 and 2024 Q1 cohorts, I’m thrilled to announce the official launch of the third WordPress Contributor Mentorship Program cohort, set for the final quarter of 2024. This program connects seasoned WordPress experts with newcomers, offering a fantastic opportunity for mentees to gain hands-on experience contributing to WordPress, while mentors share their expertise and improve their leadership skills.  Note: If you applied during the early call for interest in June-July 2024, you do not need to re-apply. This application is for new applicants. Criteria for Mentees Whether you are new to WordPress or looking to enhance your skills, this program offers a unique opportunity to learn from experienced contributors. Receive personalized guidance, develop your ski…")

A new release of WP-CLI, **WP-CLI v2.11.0**, is now available. For this release, we had **61 contributors** collaborate to get **274 pull requests** merged.

As always, big thanks to the [WP-CLI sponsors](https://make.wordpress.org/cli/sponsors/) that make the continued maintenance possible.

This is a small release that fixes a lot of small and not so small bugs, but we also have a couple of new features that I’ll want to highlight. As always, you can also skip directly to the [detailed changelog](https://make.wordpress.org/cli/#changelog) if you prefer.

If you already use WP-CLI, updating is as simple as `wp cli update`. Else, check out our website for [recommended installation methods](https://wp-cli.org/#installing).

Thank you for providing the additional details on the pull requests. I’ll go through each one and provide improved highlights with examples and usage details:

### Improved CSV Handling

The CSV reading functionality has been enhanced to properly handle multi-line values. This fix ensures that complex CSV data can be processed correctly, improving the reliability of commands that work with CSV input.

Example of a CSV file that can now be correctly processed:

```
id,name,description
1,"Product A","This is a
multi-line
description"
2,"Product B","Another description"
```

### New Signup Management Commands

New commands have been added for managing signups on multisite installations:

- `wp user signup list`: List signups
- `wp user signup get`: Get details about a signup
- `wp user signup activate`: Activate one or more signups
- `wp user signup delete`: Delete one or more signups

Example usage:

```
# List all signups
$ wp user signup list

# Activate a signup
$ wp user signup activate johndoe@example.com

# Delete a signup
$ wp user signup delete 123
```

### New Site Generator Command

A new `wp site generate` command has been added to create multiple sites programmatically in a multisite installation. This is useful for testing or development purposes.

Example usage:

```
# Generate 10 new sites
$ wp site generate --count=10

# Generate sites with a specific slug
$ wp site generate --count=2 --slug=testsite
```

### GitHub Release Installation Support

The extension command now supports installing plugins and themes directly from GitHub releases. This feature allows users to easily install and manage extensions hosted on GitHub without manual downloads.

Example usage:

```
# Install a plugin from its latest GitHub release
$ wp plugin install https://github.com/username/plugin-name/releases/latest

# Install a specific version of a theme from GitHub
$ wp theme install https://github.com/username/theme-name/releases/tag/v1.2.3
```

### Improved Plugin Management

A new `--recently-active` option has been added to the `plugin list` command, allowing users to quickly identify and manage plugins that have been recently active on their site.

Example usage:

```
# List recently active plugins
$ wp plugin list --recently-active

# Activate all recently active plugins
$ wp plugin activate $(wp plugin list --recently-active --field=name)
```

## Option to Delete Unknown Image Sizes

A new `--delete-unknown` flag has been added to the `wp media regenerate` command. This allows users to remove files and image metadata for image sizes that no longer exist in the site’s configuration, without regenerating other thumbnails.

Example usage:

```
# Remove unknown image sizes for all images
$ wp media regenerate --delete-unknown

# Remove unknown image sizes for a specific image
$ wp media regenerate 123 --delete-unknown
```

This feature is particularly useful for cleaning up after changing image size configurations or removing plugins that added custom image sizes.

## User Existence Check Command

A new `wp user exists` command has been added, similar to the existing `wp post exists` command. This allows for quick checks on whether a user exists in the WordPress database.

Example usage:

```
# The user exists.
$ wp user exists 1337
Success: User with ID 1337 exists.
$ echo $?
0

# The user does not exist.
$ wp user exists 10000
$ echo $?
1
```

### Fish Shell Completion Support

WP-CLI now supports command completion for the Fish shell, expanding its compatibility beyond Bash and Zsh. This addition makes it easier for Fish shell users to work with WP-CLI commands.

### Detailed change log

_To avoid too much noise in the list above, the following types of pull requests have been omitted:_

- _PRs that only bumped dependencies to their latest version._
- _PRs that only fixed a typo in the documentation._
- _PRs that add a Composer script_.

#### [wp-cli/wp-cli-bundle](https://github.com/wp-cli/wp-cli-bundle/)

- Update versions of WP-CLI used in tests \[ [#658](https://github.com/wp-cli/wp-cli-bundle/pull/658)\]
- Stop testing WordPress `latest` version on PHP < 7.2 \[ [#651](https://github.com/wp-cli/wp-cli-bundle/pull/651)\]

#### [wp-cli/wp-cli](https://github.com/wp-cli/wp-cli/)

- Add fish shell completion \[ [#5954](https://github.com/wp-cli/wp-cli/pull/5954)\]
- Add defaults and accepted values for `runcommand()` options in documentation \[ [#5953](https://github.com/wp-cli/wp-cli/pull/5953)\]
- Address warnings with filenames ending in full stop on Windows \[ [#5951](https://github.com/wp-cli/wp-cli/pull/5951)\]
- Fix unit tests \[ [#5950](https://github.com/wp-cli/wp-cli/pull/5950)\]
- Update copyright year in license \[ [#5942](https://github.com/wp-cli/wp-cli/pull/5942)\]
- Fix breaking multi-line CSV values on reading \[ [#5939](https://github.com/wp-cli/wp-cli/pull/5939)\]
- Fix broken Gutenberg test \[ [#5938](https://github.com/wp-cli/wp-cli/pull/5938)\]
- Update docker runner to resolve docker path using `/usr/bin/env` \[ [#5936](https://github.com/wp-cli/wp-cli/pull/5936)\]
- Fix `inherit` path in nested directory \[ [#5930](https://github.com/wp-cli/wp-cli/pull/5930)\]
- Minor docblock improvements \[ [#5929](https://github.com/wp-cli/wp-cli/pull/5929)\]
- Add Signup fetcher \[ [#5926](https://github.com/wp-cli/wp-cli/pull/5926)\]
- Ensure the alias has the leading `@` symbol when added \[ [#5924](https://github.com/wp-cli/wp-cli/pull/5924)\]
- Include any non-default hook information in `CompositeCommand` \[ [#5921](https://github.com/wp-cli/wp-cli/pull/5921)\]
- Correct completion case when it ends in `=` \[ [#5913](https://github.com/wp-cli/wp-cli/pull/5913)\]
- Fix inline comments \[ [#5912](https://github.com/wp-cli/wp-cli/pull/5912)\]
- Update inline comments \[ [#5910](https://github.com/wp-cli/wp-cli/pull/5910)\]
- Add a real-world example for `cli has-command` \[ [#5908](https://github.com/wp-cli/wp-cli/pull/5908)\]
- Fix typos \[ [#5901](https://github.com/wp-cli/wp-cli/pull/5901)\]
- Avoid PHP deprecation notices in PHP 8.1.x \[ [#5899](https://github.com/wp-cli/wp-cli/pull/5899)\]

#### [wp-cli/handbook](https://github.com/wp-cli/handbook/)

- Update handbook for v2.11.0 release \[ [#531](https://github.com/wp-cli/handbook/pull/531)\]
- Add missing scaffold package markdown files \[ [#529](https://github.com/wp-cli/handbook/pull/529)\]
- Fix `Undefined array key` warning \[ [#525](https://github.com/wp-cli/handbook/pull/525)\]
- Add files autoloader for `bin/command.php` \[ [#524](https://github.com/wp-cli/handbook/pull/524)\]
- Small typo correction \[ [#523](https://github.com/wp-cli/handbook/pull/523)\]
- Fix documentation generation error \[ [#520](https://github.com/wp-cli/handbook/pull/520)\]
- Add Yoast WP-CLI command to `tools.md` \[ [#517](https://github.com/wp-cli/handbook/pull/517)\]
- Add search and replace quick start & adding new command \[ [#515](https://github.com/wp-cli/handbook/pull/515)\]
- Add Composer package name \[ [#514](https://github.com/wp-cli/handbook/pull/514)\]
- Clean up hosting links \[ [#513](https://github.com/wp-cli/handbook/pull/513)\]
- Add to `hosting-companies.md` \[ [#512](https://github.com/wp-cli/handbook/pull/512)\]
- Remove invalid link from handbook \[ [#511](https://github.com/wp-cli/handbook/pull/511)\]
- Update contributor day page for WCEU 2024 \[ [#510](https://github.com/wp-cli/handbook/pull/510)\]
- Add documentation on Fish completions \[ [#508](https://github.com/wp-cli/handbook/pull/508)\]
- Add code quality setup \[ [#506](https://github.com/wp-cli/handbook/pull/506)\]
- Fix global parameters 404 link \[ [#504](https://github.com/wp-cli/handbook/pull/504)\]
- Fix release checklist hyperlink \[ [#503](https://github.com/wp-cli/handbook/pull/503)\]
- Fix broken link for the global parameters hyperlink \[ [#502](https://github.com/wp-cli/handbook/pull/502)\]
- Include hook details in documentation \[ [#501](https://github.com/wp-cli/handbook/pull/501)\]
- Add link to contribution tutorial videos \[ [#500](https://github.com/wp-cli/handbook/pull/500)\]
- Update `hosting-companies.md` \[ [#499](https://github.com/wp-cli/handbook/pull/499)\]
- Refresh the Hack Day page for April 2024 \[ [#498](https://github.com/wp-cli/handbook/pull/498)\]
- Fix branch name in common issues handbook page \[ [#497](https://github.com/wp-cli/handbook/pull/497)\]
- Fix common issues title \[ [#496](https://github.com/wp-cli/handbook/pull/496)\]
- Fix broken link \[ [#494](https://github.com/wp-cli/handbook/pull/494)\]
- Add Hack Day page to manifest \[ [#492](https://github.com/wp-cli/handbook/pull/492)\]
- Separate out the WP-CLI Hack Day and WordCamp Contributor Day docs \[ [#490](https://github.com/wp-cli/handbook/pull/490)\]
- Update `running-commands-remotely.md` \[ [#489](https://github.com/wp-cli/handbook/pull/489)\]
- Update brew formula link \[ [#487](https://github.com/wp-cli/handbook/pull/487)\]
- Update `installing.md` \[ [#481](https://github.com/wp-cli/handbook/pull/481)\]

#### [wp-cli/cache-command](https://github.com/wp-cli/cache-command/)

- Update failing tests after new transient in WP core \[ [#97](https://github.com/wp-cli/cache-command/pull/97)\]

#### [wp-cli/config-command](https://github.com/wp-cli/config-command/)

- Improve messaging when shuffling salts \[ [#177](https://github.com/wp-cli/config-command/pull/177)\]
- Fix incorrect message shuffling salt in PHP 5.6 \[ [#176](https://github.com/wp-cli/config-command/pull/176)\]
- Update `config` commands examples \[ [#174](https://github.com/wp-cli/config-command/pull/174)\]
- Refactor `config create` command \[ [#181](https://github.com/wp-cli/config-command/pull/181)\]

#### [wp-cli/core-command](https://github.com/wp-cli/core-command/)

- Remove extraneous argument in `core update` example \[ [#255](https://github.com/wp-cli/core-command/pull/255)\]
- Fix `--format` in `core check-update` command \[ [#253](https://github.com/wp-cli/core-command/pull/253)\]
- Update `core` commands docs \[ [#251](https://github.com/wp-cli/core-command/pull/251)\]

#### [wp-cli/cron-command](https://github.com/wp-cli/cron-command/)

- Fix `cron` commands examples \[ [#102](https://github.com/wp-cli/cron-command/pull/102)\]
- Add `--all` flag to `cron event delete` \[ [#98](https://github.com/wp-cli/cron-command/pull/98)\]

#### [wp-cli/db-command](https://github.com/wp-cli/db-command/)

- Add note about multisite usage in `db query` docs \[ [#251](https://github.com/wp-cli/db-command/pull/251)\]
- Enable `--format=<format>` for `db search` \[ [#247](https://github.com/wp-cli/db-command/pull/247)\]
- Update tests after change in WP `trunk` version \[ [#257](https://github.com/wp-cli/db-command/pull/257)\]

#### [wp-cli/embed-command](https://github.com/wp-cli/embed-command/)

- Update examples for `embed` commands \[ [#75](https://github.com/wp-cli/embed-command/pull/75)\]

#### [wp-cli/entity-command](https://github.com/wp-cli/entity-command/)

- Avoid time dependent test in `user application-password` \[ [#499](https://github.com/wp-cli/entity-command/pull/499)\]
- Support new upstream autoload options \[ [#496](https://github.com/wp-cli/entity-command/pull/496)\]
- Support nickname when creating user \[ [#495](https://github.com/wp-cli/entity-command/pull/495)\]
- Use `twentytwelve` theme in menu location test \[ [#494](https://github.com/wp-cli/entity-command/pull/494)\]
- Add examples for `option set-autoload` and `option get-autoload` commands \[ [#492](https://github.com/wp-cli/entity-command/pull/492)\]
- Add missing `## OPTIONS` in `CommandWithTerms` class \[ [#487](https://github.com/wp-cli/entity-command/pull/487)\]
- Add `user exists` command \[ [#486](https://github.com/wp-cli/entity-command/pull/486)\]
- Accept user login and email in `user spam` and `user unspam` commands \[ [#485](https://github.com/wp-cli/entity-command/pull/485)\]
- Update doc for `user spam` and `user unspam` command \[ [#483](https://github.com/wp-cli/entity-command/pull/483)\]
- Validate reassigning user in `user delete` command \[ [#482](https://github.com/wp-cli/entity-command/pull/482)\]
- Fix warning message in `user spam` command \[ [#481](https://github.com/wp-cli/entity-command/pull/481)\]
- Add missing `application-password` and `site meta` subcommands to readme \[ [#478](https://github.com/wp-cli/entity-command/pull/478)\]
- Introduce `--format=ids` in `user application-password list` \[ [#475](https://github.com/wp-cli/entity-command/pull/475)\]
- Fix dynamic property issue in user session class \[ [#470](https://github.com/wp-cli/entity-command/pull/470)\]
- Fix PHP notice in `comment recount` with invalid ID \[ [#469](https://github.com/wp-cli/entity-command/pull/469)\]
- Fix example for `site deactivate` command \[ [#468](https://github.com/wp-cli/entity-command/pull/468)\]
- Update examples in `user` commands \[ [#467](https://github.com/wp-cli/entity-command/pull/467)\]
- Update `term` commands examples \[ [#466](https://github.com/wp-cli/entity-command/pull/466)\]
- Update example output for `comment delete` command \[ [#465](https://github.com/wp-cli/entity-command/pull/465)\]
- Fix `menu` command output examples \[ [#462](https://github.com/wp-cli/entity-command/pull/462)\]
- Add `site generate` command \[ [#498](https://github.com/wp-cli/entity-command/pull/498)\]
- Add commands for managing signups on multisite \[ [#489](https://github.com/wp-cli/entity-command/pull/489)\]

#### [wp-cli/extension-command](https://github.com/wp-cli/extension-command/)

- Improve warning message for installing and activating multiple themes \[ [#419](https://github.com/wp-cli/extension-command/pull/419)\]
- Replace `user-switching` plugin from feature tests \[ [#418](https://github.com/wp-cli/extension-command/pull/418)\]
- Update the theme in feature tests \[ [#417](https://github.com/wp-cli/extension-command/pull/417)\]
- Show additional plugin header values in `plugin get <plugin>` output \[ [#414](https://github.com/wp-cli/extension-command/pull/414)\]
- Add `tested_up_to` field \[ [#413](https://github.com/wp-cli/extension-command/pull/413)\]
- Warn when supplying multiple themes with `theme install --activate` \[ [#408](https://github.com/wp-cli/extension-command/pull/408)\]
- Fix `plugin` commands examples \[ [#403](https://github.com/wp-cli/extension-command/pull/403)\]
- Update `theme` commands examples \[ [#401](https://github.com/wp-cli/extension-command/pull/401)\]
- Correct parameter type in `ParseThemeNameInput` trait \[ [#400](https://github.com/wp-cli/extension-command/pull/400)\]
- Add `--recently-active` option in `plugin list` command \[ [#424](https://github.com/wp-cli/extension-command/pull/424)\]
- Fix visibility in command class methods \[ [#423](https://github.com/wp-cli/extension-command/pull/423)\]
- Add support for GitHub release installation \[ [#421](https://github.com/wp-cli/extension-command/pull/421)\]
- Replace `edit-flow` plugin by `debug-bar` in feature tests \[ [#427](https://github.com/wp-cli/extension-command/pull/427)\]

#### [wp-cli/i18n-command](https://github.com/wp-cli/i18n-command/)

- Skip strings without translation in `make-php` \[ [#389](https://github.com/wp-cli/i18n-command/pull/389)\]
- Add more headers to PHP translation files \[ [#388](https://github.com/wp-cli/i18n-command/pull/388)\]
- Use relative paths for file header references \[ [#384](https://github.com/wp-cli/i18n-command/pull/384)\]
- Translate “description” field from `theme.json` \[ [#408](https://github.com/wp-cli/i18n-command/pull/408)\]
- Revert changes to extract title from `styles.blocks.variations` \[ [#407](https://github.com/wp-cli/i18n-command/pull/407)\]
- find `title` string within `styles.blocks.variations` in `theme.json` \[ [#405](https://github.com/wp-cli/i18n-command/pull/405)\]
- Add tests for `rspack` and `esbuild` bundle output \[ [#404](https://github.com/wp-cli/i18n-command/pull/404)\]
- Fix deprecation warnings in unit tests \[ [#402](https://github.com/wp-cli/i18n-command/pull/402)\]
- Use relative paths for file header references (Windows fix) \[ [#400](https://github.com/wp-cli/i18n-command/pull/400)\]
- Ensure that the POT file uses the same license as the theme \[ [#399](https://github.com/wp-cli/i18n-command/pull/399)\]
- Add examples for `i18n update-po` command \[ [#392](https://github.com/wp-cli/i18n-command/pull/392)\]
- Add examples for `i18 make-pot` \[ [#390](https://github.com/wp-cli/i18n-command/pull/390)\]

#### [wp-cli/language-command](https://github.com/wp-cli/language-command/)

- Update examples for `language` command \[ [#145](https://github.com/wp-cli/language-command/pull/145)\]
- Update examples for `language core` command \[ [#142](https://github.com/wp-cli/language-command/pull/142)\]
- Update examples for `language theme` command \[ [#141](https://github.com/wp-cli/language-command/pull/141)\]
- Update examples for `language plugin` command \[ [#140](https://github.com/wp-cli/language-command/pull/140)\]
- Improve warning message for unavailable language pack \[ [#139](https://github.com/wp-cli/language-command/pull/139)\]
- Update doc for `language core install` command \[ [#153](https://github.com/wp-cli/language-command/pull/153)\]
- Add `--format=count` in `language list` commands \[ [#151](https://github.com/wp-cli/language-command/pull/151)\]
- Update feature tests for `language core update` \[ [#149](https://github.com/wp-cli/language-command/pull/149)\]

#### [wp-cli/maintenance-mode-command](https://github.com/wp-cli/maintenance-mode-command/)

- Add missing `OPTIONS` heading in `maintenance-mode activate` command \[ [#28](https://github.com/wp-cli/maintenance-mode-command/pull/28)\]

#### [wp-cli/media-command](https://github.com/wp-cli/media-command/)

- Fix incorrect image sizes in `media image-size` command \[ [#192](https://github.com/wp-cli/media-command/pull/192)\]
- Remove extraneous error check \[ [#191](https://github.com/wp-cli/media-command/pull/191)\]
- Update `media` commands examples \[ [#189](https://github.com/wp-cli/media-command/pull/189)\]
- Optimize memory consumption when querying attachments \[ [#188](https://github.com/wp-cli/media-command/pull/188)\]
- Add option to delete unknown image sizes \[ [#199](https://github.com/wp-cli/media-command/pull/199)\]

#### [wp-cli/package-command](https://github.com/wp-cli/package-command/)

- Update docs and examples for `package` commands \[ [#186](https://github.com/wp-cli/package-command/pull/186)\]
- Fix failing test \[ [#185](https://github.com/wp-cli/package-command/pull/185)\]
- Fix failing PHPUnit tests \[ [#188](https://github.com/wp-cli/package-command/pull/188)\]

#### [wp-cli/php-cli-tools](https://github.com/wp-cli/php-cli-tools/)

- Fix unit tests \[ [#172](https://github.com/wp-cli/php-cli-tools/pull/172)\]

#### [wp-cli/scaffold-command](https://github.com/wp-cli/scaffold-command/)

- Update theme tests to remove `p2` and use `twentytwelve` \[ [#336](https://github.com/wp-cli/scaffold-command/pull/336)\]
- Correct plugin main file in bootstrap in scaffolded test \[ [#335](https://github.com/wp-cli/scaffold-command/pull/335)\]
- Scaffold theme test should work in PHP greater than 8.0 \[ [#334](https://github.com/wp-cli/scaffold-command/pull/334)\]
- Add GitHub as valid CI for `plugin scaffold` and `theme scaffold` \[ [#331](https://github.com/wp-cli/scaffold-command/pull/331)\]
- Update `scaffold` command examples \[ [#329](https://github.com/wp-cli/scaffold-command/pull/329)\]

#### [wp-cli/search-replace-command](https://github.com/wp-cli/search-replace-command/)

- Fix tests after change in WordPress trunk \[ [#195](https://github.com/wp-cli/search-replace-command/pull/195)\]
- Fix test for WordPress trunk \[ [#197](https://github.com/wp-cli/search-replace-command/pull/197)\]

#### [wp-cli/super-admin-command](https://github.com/wp-cli/super-admin-command/)

- Add IDs as format for `super admin` list \[ [#60](https://github.com/wp-cli/super-admin-command/pull/60)\]
- Correct `super-admin` commands examples \[ [#57](https://github.com/wp-cli/super-admin-command/pull/57)\]

#### [wp-cli/widget-command](https://github.com/wp-cli/widget-command/)

- Replace `p2` theme with `twentytwelve` in feature test \[ [#61](https://github.com/wp-cli/widget-command/pull/61)\]

#### [wp-cli/wp-config-transformer](https://github.com/wp-cli/wp-config-transformer/)

- Fix failing PHPUnit tests \[ [#52](https://github.com/wp-cli/wp-config-transformer/pull/52)\]

### Contributors

[@2ndkauboy](https://github.com/2ndkauboy), [@aldisruiz](https://github.com/aldisruiz), [@austinginder](https://github.com/austinginder), [@benjaminprojas](https://github.com/benjaminprojas), [@BrianHenryIE](https://github.com/BrianHenryIE), [@Chintesh](https://github.com/Chintesh), [@christianwach](https://github.com/christianwach), [@cliffordp](https://github.com/cliffordp), [@dac514](https://github.com/dac514), [@danielbachhuber](https://github.com/danielbachhuber), [@dd32](https://github.com/dd32), [@dlind1](https://github.com/dlind1), [@drzraf](https://github.com/drzraf), [@elenachavdarova](https://github.com/elenachavdarova), [@ernilambar](https://github.com/ernilambar), [@gedex](https://github.com/gedex), [@gitlost](https://github.com/gitlost), [@grafruessel](https://github.com/grafruessel), [@greatislander](https://github.com/greatislander), [@herregroen](https://github.com/herregroen), [@huzaifaalmesbah](https://github.com/huzaifaalmesbah), [@i-am-chitti](https://github.com/i-am-chitti), [@janw-me](https://github.com/janw-me), [@jenkoian](https://github.com/jenkoian), [@jkrrv](https://github.com/jkrrv), [@jrfnl](https://github.com/jrfnl), [@l3ku](https://github.com/l3ku), [@localheinz](https://github.com/localheinz), [@matzeeable](https://github.com/matzeeable), [@meszarosrob](https://github.com/meszarosrob), [@michaelzangl](https://github.com/michaelzangl), [@Mike-Hermans](https://github.com/Mike-Hermans), [@mrsdizzie](https://github.com/mrsdizzie), [@oandregal](https://github.com/oandregal), [@ocean90](https://github.com/ocean90), [@oxyc](https://github.com/oxyc), [@pbiron](https://github.com/pbiron), [@pdaalder](https://github.com/pdaalder), [@petitphp](https://github.com/petitphp), [@pmbaldha](https://github.com/pmbaldha), [@ponsfrilus](https://github.com/ponsfrilus), [@ramonjd](https://github.com/ramonjd), [@rodrigoprimo](https://github.com/rodrigoprimo), [@Roy-Orbison](https://github.com/Roy-Orbison), [@saas786](https://github.com/saas786), [@schlessera](https://github.com/schlessera), [@Scotchester](https://github.com/Scotchester), [@sdnunca](https://github.com/sdnunca), [@shawnhooper](https://github.com/shawnhooper), [@shendy-a8c](https://github.com/shendy-a8c), [@siliconforks](https://github.com/siliconforks), [@strarsis](https://github.com/strarsis), [@swissspidy](https://github.com/swissspidy), [@szepeviktor](https://github.com/szepeviktor), [@Takshil-Kunadia](https://github.com/Takshil-Kunadia), [@tfirdaus](https://github.com/tfirdaus), [@thelovekesh](https://github.com/thelovekesh), [@Tug](https://github.com/Tug), [@UmeshSingla](https://github.com/UmeshSingla), [@wojsmol](https://github.com/wojsmol), [@yousan](https://github.com/yousan)

[#release](https://make.wordpress.org/cli/tag/release/), [#v2-11-0](https://make.wordpress.org/cli/tag/v2-11-0/)

The “Option to Delete Unknown Image Sizes” is such a huge win! Love it!

- [Login to Reply](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fmake.wordpress.org%2Fcli%2F2024%2F08%2F08%2Fwp-cli-v2-11-0-release-notes%2F%23comment-218&locale=en_US)

I have a backup WordPress and with the help of this got a cron job that auto saves the WordPress database and post to another domain.

But it’s on a SSD and want it every day so if there a wp-cli command that will only copy the changes to WordPress Database? I don’t think there is a command do that that but could some one make a command that will do that. Sort of like what rsync can do when copying files. Maybe a type a rsync command can do in wp-cli ?

That would be very good command hope some one can do it.

Thank for making this wp-cli and make it so can auto backup to another WordPress domain.

- [Login to Reply](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fmake.wordpress.org%2Fcli%2F2024%2F08%2F08%2Fwp-cli-v2-11-0-release-notes%2F%23comment-219&locale=en_US)

I did it with the help of chat GPT and this is a html code to show how to do this so it auto backs up the Database and media. Shows how to put it in a cron job too.

The only thing I wish that it would not copy 100% of the database but just the changes. Like the media it don’t copy 100% of it just the changes. If any one knows how to do that post it or let me know thank you.

\[code\]

WordPress Database and Media Copy Script

body {

font-family: Arial, sans-serif;

margin: 20px;

}

pre {

background-color: #f4f4f4;

padding: 10px;

border-radius: 5px;

border: 1px solid #ccc;

white-space: pre-wrap;

word-wrap: break-word;

position: relative;

}

.highlight {

background-color: #ffffcc;

}

.copy-btn {

position: absolute;

top: 5px;

right: 5px;

padding: 5px 10px;

background-color: #007bff;

color: white;

border: none;

border-radius: 5px;

cursor: pointer;

font-size: 12px;

}

.copy-btn:hover {

background-color: #0056b3;

}

# Script to Copy WordPress Database and Media

This script copies a WordPress database and media from a source server to a destination server. Please replace the placeholders with your actual WordPress domain name.

```
<h2>Step 1: Easy Install WordPress</h2>
Follow the instructions in the link below to install WordPress:
<a href="https://linux.how2shout.com/script-to-install-lamp-wordpress-on-ubuntu-20-04-lts-destination-quickly-with-one-command/" target="_blank">Easy Install WordPress Script</a>

<h2>Step 2: Install Required Packages and Set Up WP-CLI</h2>
<pre>
    <button class="copy-btn" onclick="copyToClipboard(this)">Copy</button>

```

apt install curl

apt install rsync

curl -O [https://raw.githubusercontent.com/wp-cli/builds/gh-pages/phar/wp-cli.phar](https://raw.githubusercontent.com/wp-cli/builds/gh-pages/phar/wp-cli.phar)

chmod +x wp-cli.phar

mv wp-cli.phar /usr/local/bin/wp

ssh-keygen -t rsa -b 4096

ssh-copy-id root@source

nano /root/.my.cnf

\[client\]

user=root

password=your\_password

chmod 600 /root/.my.cnf

The `.my.cnf` file stores the database username and password.

```
<h2>Step 3: Create and Configure Scripts</h2>

<h3>On the Source Server</h3>
Create the script to copy the database:
<pre>
    <button class="copy-btn" onclick="copyToClipboard(this)">Copy</button>

```

nano WP-copy-DB\_to\_destination.sh

#!/bin/bash

wp db export –allow-root –path=/var/www/html backup.sql

scp “/root/backup.sql” root@destination:/root/backup.sql

chmod 755 WP-copy-DB\_to\_destination.sh

```
<h3>On the Destination Server</h3>
Create the script to import the database and sync media:
Note: You may need to add the following lines to your script for cron jobs:
<pre class="highlight">
    <button class="copy-btn" onclick="copyToClipboard(this)">Copy</button>

```

# Set PATH for cron job

export PATH=/usr/local/bin:/usr/bin:/bin:/usr/sbin:/sbin

```
        Copy
nano Get-WP-DB-from_source.sh

#!/bin/bash
wp db import /root/backup.sql --allow-root --path=/var/www/html
mysql wordpressdb < /root/wordpress-change-domain-migration.sql
rsync -avP --delete root@source:/var/www/html/wp-content/uploads/ /var/www/html/wp-content/uploads

chmod 700 Get-WP-DB-from_source.sh

```

Edit the SQL script to update the URLs:

```
        Copy
nano wordpress-change-domain-migration.sql

SET @oldsite='http://source';
SET @newsite='http://destination';
UPDATE wp_options SET option_value = replace(option_value, @oldsite, @newsite) WHERE option_name = 'home' OR option_name = 'siteurl';
UPDATE wp_posts SET post_content = replace(post_content, @oldsite, @newsite);
UPDATE wp_links SET link_url = replace(link_url, @oldsite, @newsite);
UPDATE wp_postmeta SET meta_value = replace(meta_value, @oldsite, @newsite);

/* only uncomment next line if you want all your current posts to post to RSS again as new */
#UPDATE wp_posts SET guid = replace(guid, @oldsite, @newsite)

```

```
<h2>Step 4: Set Up Cron Jobs</h2>

<h3>On the Source Server</h3>
<pre>
    <button class="copy-btn" onclick="copyToClipboard(this)">Copy</button>

```

crontab -e

0 2 \* \* \* /root/WP-copy-DB\_to\_destination.sh

```
<h3>On the Destination Server</h3>
<pre>
    <button class="copy-btn" onclick="copyToClipboard(this)">Copy</button>

```

crontab -e

20 2 \* \* \* /root/Get-WP-DB-from\_source.sh

```
<h2>Step 5: Set Up SSH Keys for Automation</h2>
<pre>
    <button class="copy-btn" onclick="copyToClipboard(this)">Copy</button>

```

ssh-copy-id

ssh-copy-id root@destination

```
<h2>Step 6: Test the Script</h2>

<h3>On the Source Server</h3>
<pre>
    <button class="copy-btn" onclick="copyToClipboard(this)">Copy</button>

```

sh WP-copy-DB\_to\_hp2.sh

```
<h3>On the Destination Server</h3>
<pre>
    <button class="copy-btn" onclick="copyToClipboard(this)">Copy</button>

```

sh Get-WP-DB-from\_source.sh

```
<script>
    function copyToClipboard(button) {
        const text = button.parentElement.innerText.replace('Copy', '').trim();
        navigator.clipboard.writeText(text).then(() => {
            alert('Commands copied to clipboard!');
        }).catch(err => {
            console.error('Could not copy text: ', err);
        });
    }
</script>

```

\[/code\]

- [Login to Reply](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fmake.wordpress.org%2Fcli%2F2024%2F08%2F08%2Fwp-cli-v2-11-0-release-notes%2F%23comment-220&locale=en_US)

I put it on my google drive so here is the link:

It did not show here real good but it will if you download it and open in a web browser.

- [Login to Reply](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fmake.wordpress.org%2Fcli%2F2024%2F08%2F08%2Fwp-cli-v2-11-0-release-notes%2F%23comment-221&locale=en_US)

Looked like it removed that link I guess can’t post it.

- [Login to Reply](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fmake.wordpress.org%2Fcli%2F2024%2F08%2F08%2Fwp-cli-v2-11-0-release-notes%2F%23comment-222&locale=en_US)

Got a free little web server and I put that info on there. It’s a lot easier to follower to install this script on another WordPress install for a backup.

[Here is the link.](http://wordpresscopyscript.infinityfreeapp.com/?i=1)

Let me know if it works for you. I got this on a low power Windows tablet that can install Linux on and used the OTG USB port to mount a HDD or SSD.

- [Login to Reply](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fmake.wordpress.org%2Fcli%2F2024%2F08%2F08%2Fwp-cli-v2-11-0-release-notes%2F%23comment-224&locale=en_US)

The v2.11.0 release of WP-CLI is scheduled to be published on Tuesday, August 6th 2024.

Apart from bug fixes and compatibility improvements, you can also expect a few command and parameter additions to help make the tool more efficient, as well as a large swath of documentation fixes and improvements.

The third ever WP-CLI Hack Day is now complete!

It was really nice to connect with folks both on Zoom and in Slack. With how much async collaboration we have in the project, it’s quite refreshing to discuss bugs and implementations in real-time. I think we had a Zoom room open for over seven hours.

**Many thanks to everyone that participated!** 🙏 [@abhi3315](https://profiles.wordpress.org/abhi3315/), [@brianhenryie](https://profiles.wordpress.org/brianhenryie/), [@danielbachhuber](https://profiles.wordpress.org/danielbachhuber/), Deepak Kumar, isla w, [@johnbillion](https://profiles.wordpress.org/johnbillion/), [@kau-boy](https://profiles.wordpress.org/kau-boy/), [@mkrndmane](https://profiles.wordpress.org/mkrndmane/), [@meszarosrob](https://profiles.wordpress.org/meszarosrob/), [@petitphp](https://profiles.wordpress.org/petitphp/), [@rabmalin](https://profiles.wordpress.org/rabmalin/), [@schlessera](https://profiles.wordpress.org/schlessera/), [@swissspidy](https://profiles.wordpress.org/swissspidy/), Takshil Kunadia, [@tfirdaus](https://profiles.wordpress.org/tfirdaus/), [@thelovekesh](https://profiles.wordpress.org/thelovekesh/)

We had **15 pull requests that were merged** during the event:

01. [Update docker runner to resolve docker path using `/usr/bin/env`](https://github.com/wp-cli/wp-cli/pull/5936)
02. [Add `Signup` fetcher](https://github.com/wp-cli/wp-cli/pull/5926)
03. [Fix broken Gutenberg test](https://github.com/wp-cli/wp-cli/pull/5938)
04. [Warn when supplying multiple themes with `theme install --activate`](https://github.com/wp-cli/extension-command/pull/408)
05. [Add `wp-versions-data-fetcher` workflow](https://github.com/wp-cli/wp-cli-tests/pull/199)
06. [Improve warning message for install and activate multiple themes](https://github.com/wp-cli/extension-command/pull/419)
07. [Fix breaking multi-line CSV values on reading](https://github.com/wp-cli/wp-cli/pull/5939)
08. [Ensure that the POT file use the same license as the theme](https://github.com/wp-cli/i18n-command/pull/399)
09. [Fix `inherit` path in nested directory](https://github.com/wp-cli/wp-cli/pull/5930)
10. [Update failing tests after new transient in WP core](https://github.com/wp-cli/cache-command/pull/97)
11. [Add `tested_up_to` field](https://github.com/wp-cli/extension-command/pull/413)
12. [Correct plugin main file in bootstrap in scaffolded test](https://github.com/wp-cli/scaffold-command/pull/335)
13. [Include any non default hook information in CompositeCommand](https://github.com/wp-cli/wp-cli/pull/5921)
14. [Add support for GitHub release installation](https://github.com/wp-cli/extension-command/pull/421)
15. [Enable `--format=<format>` for `db search`](https://github.com/wp-cli/db-command/pull/247)

In addition to those, we had an additional **6 pull requests with substantial progress** during the event that aren’t yet merged:

- [Add Support for Retry in WP CLI Core Download Command](https://github.com/wp-cli/core-command/pull/258)
- [Support beta/rc releases](https://github.com/wp-cli/core-command/pull/260)
- [Add commands for managing signups on multisite](https://github.com/wp-cli/entity-command/pull/489)
- [Add site generator command](https://github.com/wp-cli/entity-command/pull/498)
- [Add `--format` flag in `core update`](https://github.com/wp-cli/core-command/pull/254)
- [Add pluck/patch commands for caches and transients](https://github.com/wp-cli/cache-command/pull/89)

See you at the next WP-CLI Hack Day!

It was really fun to participate again! 🙌

I’m especially happy that the PR I have worked on last time is finally merged. I can’t wait to use that new `--format` option on the `wp db search` command in the future.

I’m looking forward to the next WP-CLI Hack Day!

P.S. I think the profile for Makarand Mane is this one: [https://profiles.wordpress.org/mkrndmane/](https://profiles.wordpress.org/mkrndmane/)

P.P.S How about giving all who contributed the “WP-CLI Contributor” profile badge? It seems those have to be assigned manually.

- [Login to Reply](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fmake.wordpress.org%2Fcli%2F2024%2F04%2F27%2Ffifteen-merged-prs-for-wp-cli-hack-day-2024%2F%23comment-214&locale=en_US)

yes that username is correct

- [Login to Reply](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fmake.wordpress.org%2Fcli%2F2024%2F04%2F27%2Ffifteen-merged-prs-for-wp-cli-hack-day-2024%2F%23comment-216&locale=en_US)

[@danielbachhuber](https://profiles.wordpress.org/danielbachhuber/) my wp.org username is [@mkrndmane](https://profiles.wordpress.org/mkrndmane/)

Can u mention me

- [Login to Reply](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fmake.wordpress.org%2Fcli%2F2024%2F04%2F27%2Ffifteen-merged-prs-for-wp-cli-hack-day-2024%2F%23comment-215&locale=en_US)

Done!

- [Login to Reply](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fmake.wordpress.org%2Fcli%2F2024%2F04%2F27%2Ffifteen-merged-prs-for-wp-cli-hack-day-2024%2F%23comment-217&locale=en_US)

We’re happy to announce the third ever **WP-CLI Hack Day**! 🤓🎈

On 🕓 **Friday, 26th April 2024** we’ll officially kick off the WP-CLI Hack Day at 🕗 **[Friday, April 26, 2024 at 04:00 AM EDT](https://www.timeanddate.com/worldclock/fixedtime.html?iso=20240426T0800)**. From that point on, [@schlessera](https://profiles.wordpress.org/schlessera/), [@swissspidy](https://profiles.wordpress.org/swissspidy/), and I will be generally available in [Slack #cli channel](https://wordpress.slack.com/messages/C02RP4T41) and on the [GitHub `wp-cli` organization](https://github.com/wp-cli/) to onboard new contributors, help people pick issues to work on and remove hurdles that keep them from finishing their PRs. This will continue more or less without interruption during the entire event.

From 🕓 **[Friday, April 26, 2024 at 05:00 AM EDT](https://www.timeanddate.com/worldclock/fixedtime.html?iso=20240426T0900)** to **[Friday, April 26, 2024 at 06:00 AM EDT](https://www.timeanddate.com/worldclock/fixedtime.html?iso=20240426T1000)** and then again between 🕓 **[Friday, April 26, 2024 at 11:00 AM EDT](https://www.timeanddate.com/worldclock/fixedtime.html?iso=20240426T1500)** and **[Friday, April 26, 2024 at 12:00 PM EDT](https://www.timeanddate.com/worldclock/fixedtime.html?iso=20240426T1600)** we’ll have an open video chat that everyone can join, where we can discuss remaining issues live and chat about the progress we’ve made. This extended video chat session will then conclude the event. Shortly after 🕕 **[Friday, April 26, 2024 at 06:00 PM EDT](https://www.timeanddate.com/worldclock/fixedtime.html?iso=20240426T2200)**, I will post a [make/cli](https://make.wordpress.org/cli/) blog post about the progress we were able to make during the allotted time frame.

The 🎯 **goal** for this WP-CLI Hack Day is both simple and ambitious:

**Finish the day with 2️⃣0️⃣ pull requests that have been merged during the event ❗️**

Everyone is welcome to participate! This event is supposed to be fun and inspiring, and we expect people to help each other make progress along the way.

**Let’s make this happen! 👍** The official hashtag for the event is [#hackwpcli](https://twitter.com/hashtag/hackwpcli?src=hash&f=live) 📣

[#hack-day](https://make.wordpress.org/cli/tag/hack-day/)

Hello. How do you get access to Slack?

- [Login to Reply](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fmake.wordpress.org%2Fcli%2F2024%2F04%2F02%2Fsave-the-date-wp-cli-hack-day-on-friday-april-26th%2F%23comment-210&locale=en_US)

Visit [https://make.wordpress.org/chat/](https://make.wordpress.org/chat/) to get started with the WordPress Slack.

In short:

1. Download Slack
2. Visit [https://wordpress.slack.com/](https://wordpress.slack.com/)
3. Sign in with `samrueby@chat.wordpress.org` as your email address

- [Login to Reply](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fmake.wordpress.org%2Fcli%2F2024%2F04%2F02%2Fsave-the-date-wp-cli-hack-day-on-friday-april-26th%2F%23comment-212&locale=en_US)

I have no idea how that knew my real email address.

Worked. Thank you.

- [Login to Reply](https://login.wordpress.org/?redirect_to=https%3A%2F%2Fmake.wordpress.org%2Fcli%2F2024%2F04%2F02%2Fsave-the-date-wp-cli-hack-day-on-friday-april-26th%2F%23comment-213&locale=en_US)

A new release of WP-CLI, **WP-CLI v2.10.0**, is now available. For this release, we had **63 contributors** collaborate to get **233 pull requests** merged.

As always, big thanks to the [WP-CLI sponsors](https://make.wordpress.org/cli/sponsors/) that make the continued maintenance possible.

This is a small release that fixes a lot of small and not so small bugs, but we also have a couple of new features that I’ll want to highlight. As always, you can also skip directly to the [detailed changelog](https://make.wordpress.org/cli/#changelog) if you prefer.

If you already use WP-CLI, updating is as simple as `wp cli update`. Else, check out our website for [recommended installation methods](https://wp-cli.org/#installing).

### New `i18n make-php` command

The WordPress core performance team is working on the [Performant Translations](https://make.wordpress.org/core/2023/09/05/call-for-testing-performant-translations/) feature project, which aims to speed up translations by using PHP files instead of MO files. The goal is to get it ready for WordPress 6.5.

The new `i18n make-php` command allows you to experiment with these faster translations right away and see how these work for your projects.

```
# Create PHP files for all PO files in the current directory.

$ wp i18n make-php .

# Create a PHP file from a single PO file in a specific directory.

$ wp i18n make-php example-plugin-de_DE.po languages
```

### Update themes to minor or patch versions

When updating themes with WP-CLI, you can now to choose to only update to the latest minor or patch version with the new flags `--minor` and `--patch`.

You could already do this for plugin updates, and now themes are joining the club as well.

### Support for adding and removing of multiple user roles

The two commands `user add-role` and `user remove-role` are now less lazy and can accept multiple roles to add or remove for a given user. You can make this work by simply adding as many roles as needed as separate arguments.

```
$ wp user add-role 12 author editor

Success: Added 'author', 'editor' roles for johndoe (12).

$ wp user remove-role 12 author editor

Success: Removed 'author', 'editor' roles for johndoe (12).
```

### Filter the site list by user

When displaying a list of sites on your multisite network, you can now filter this list by a site user and only display sites that this user is a part of. You can do so by using the new `--site_user` flag for the `site list` command.

This can be helpful for administrative tasks around access control or for offboarding users.

### Detailed change log

_To avoid too much noise in the list above, the following types of pull requests have been omitted:_

- _PRs that only bumped dependencies to their latest version._
- _PRs that only fixed a typo in the documentation._
- _PRs that add a Composer script_.

#### [wp-cli/wp-cli-bundle](https://github.com/wp-cli/wp-cli-bundle/)

- Fix SQLite tests \[ [#588](https://github.com/wp-cli/wp-cli-bundle/pull/588)\]

#### [wp-cli/wp-cli](https://github.com/wp-cli/wp-cli/)

- Fix PHP deprecation warnings \[ [#5897](https://github.com/wp-cli/wp-cli/pull/5897)\]
- Only use `--skip-column-statistics` flag when available \[ [#5895](https://github.com/wp-cli/wp-cli/pull/5895)\]
- Handle unparseable tags gracefully \[ [#5894](https://github.com/wp-cli/wp-cli/pull/5894)\]
- `WpOrgApi`: allow specifying fields request parameters \[ [#5893](https://github.com/wp-cli/wp-cli/pull/5893)\]
- Remove unneeded compatibility shim \[ [#5885](https://github.com/wp-cli/wp-cli/pull/5885)\]
- Use `has_config()` in `get_config()` to prevent warnings on `null` values \[ [#5880](https://github.com/wp-cli/wp-cli/pull/5880)\]
- Suggest `'network meta'` intead of `'network option'` \[ [#5879](https://github.com/wp-cli/wp-cli/pull/5879)\]
- Updated docblock for `admin.php` \[ [#5877](https://github.com/wp-cli/wp-cli/pull/5877)\]
- Fix PHP fatals when `admin.php` has `CRLF` line endings \[ [#5875](https://github.com/wp-cli/wp-cli/pull/5875)\]
- Standard completion of current option \[ [#5873](https://github.com/wp-cli/wp-cli/pull/5873)\]
- Add `WP_CLI\Utils\has_stdin()` function \[ [#5872](https://github.com/wp-cli/wp-cli/pull/5872)\]
- Add verbosity level and quiet flag in ssh command based on debug flag \[ [#5869](https://github.com/wp-cli/wp-cli/pull/5869)\]
- Remove the pre-commit hook installation and its corresponding command \[ [#5868](https://github.com/wp-cli/wp-cli/pull/5868)\]
- Add missing required arguments when using `--prompt` \[ [#5865](https://github.com/wp-cli/wp-cli/pull/5865)\]
- Move `RecursiveDataStructureTraverser` to `wp-cli/wp-cli` package \[ [#5864](https://github.com/wp-cli/wp-cli/pull/5864)\] \[ [#5866](https://github.com/wp-cli/wp-cli/pull/5866)\] \[ [#5871](https://github.com/wp-cli/wp-cli/pull/5871)\]
- Add `docker compose` command support in SSH command generation \[ [#5863](https://github.com/wp-cli/wp-cli/pull/5863)\]
- Add missing documentation for `$data` attribute in `http_request()` \[ [#5861](https://github.com/wp-cli/wp-cli/pull/5861)\]
- Update inline PHP documentation \[ [#5853](https://github.com/wp-cli/wp-cli/pull/5853)\]
- Remove `contrib-list.php` \[ [#5851](https://github.com/wp-cli/wp-cli/pull/5851)\]
- Update release checklist template \[ [#5850](https://github.com/wp-cli/wp-cli/pull/5850)\]
- Update tests to accommodate for SQLite \[ [#5849](https://github.com/wp-cli/wp-cli/pull/5849)\]
- Post-release version bump after v2.9.0 \[ [#5848](https://github.com/wp-cli/wp-cli/pull/5848)\]
- Update `Formatter\show_table` to use `Runner->in_color` rather than `shouldColorize` \[ [#5804](https://github.com/wp-cli/wp-cli/pull/5804)\]

#### [wp-cli/handbook](https://github.com/wp-cli/handbook/)

- Fix handbook generation when Phar is used directly \[ [#476](https://github.com/wp-cli/handbook/pull/476)\]
- Hack Day edits \[ [#474](https://github.com/wp-cli/handbook/pull/474)\]
- Refresh functional test docs \[ [#471](https://github.com/wp-cli/handbook/pull/471)\]
- Refresh Contributor Day Page for November 2023 Hack Day \[ [#470](https://github.com/wp-cli/handbook/pull/470)\]

#### [wp-cli/wp-cli.github.com](https://github.com/wp-cli/wp-cli.github.com/)

- Update translations \[ [#434](https://github.com/wp-cli/wp-cli.github.com/pull/434)\]
- Fix link in `index.md` \[ [#433](https://github.com/wp-cli/wp-cli.github.com/pull/433)\]
- Update `ja/index.md` \[ [#432](https://github.com/wp-cli/wp-cli.github.com/pull/432)\]

#### [wp-cli/checksum-command](https://github.com/wp-cli/checksum-command/)

- Add edge case handling checksum verification of `hello-dolly` plugin \[ [#119](https://github.com/wp-cli/checksum-command/pull/119)\]

#### [wp-cli/config-command](https://github.com/wp-cli/config-command/)

- Add support for MySQL socket connection \[ [#171](https://github.com/wp-cli/config-command/pull/171)\]
- Fix tests for SQLite \[ [#168](https://github.com/wp-cli/config-command/pull/168)\]

#### [wp-cli/core-command](https://github.com/wp-cli/core-command/)

- Add `--force-check` flag to `check-update` command \[ [#246](https://github.com/wp-cli/core-command/pull/246)\]
- Improve SQLite compatibility \[ [#243](https://github.com/wp-cli/core-command/pull/243)\]

#### [wp-cli/db-command](https://github.com/wp-cli/db-command/)

- Better document `--skip-column-names` for retrieving a specific value \[ [#249](https://github.com/wp-cli/db-command/pull/249)\]
- Regenerate README file \[ [#246](https://github.com/wp-cli/db-command/pull/246)\]
- Document what `wp db check` doesn’t do and provide suggestions for next commands \[ [#244](https://github.com/wp-cli/db-command/pull/244)\]

#### [wp-cli/entity-command](https://github.com/wp-cli/entity-command/)

- Add missing documentation \[ [#451](https://github.com/wp-cli/entity-command/pull/451)\]
- Add command to get the post ID by URL \[ [#449](https://github.com/wp-cli/entity-command/pull/449)\]
- Fix archiving a site by numeric slug \[ [#448](https://github.com/wp-cli/entity-command/pull/448)\]
- Regenerate README file \[ [#447](https://github.com/wp-cli/entity-command/pull/447)\]
- Add `origin` and `exclude-role-names` filters to `list-caps` command \[ [#445](https://github.com/wp-cli/entity-command/pull/445)\]
- Fix deleting a site by a slug that is an integer \[ [#444](https://github.com/wp-cli/entity-command/pull/444)\]
- Reuse `has_stdin()` from framework \[ [#443](https://github.com/wp-cli/entity-command/pull/443)\]
- Remove `RecursiveDataStructureTraverser` \[ [#442](https://github.com/wp-cli/entity-command/pull/442)\]
- Support for adding and removing of multiple user roles \[ [#437](https://github.com/wp-cli/entity-command/pull/437)\]
- Add examples on listing unapproved, spam and trash comments \[ [#436](https://github.com/wp-cli/entity-command/pull/436)\]
- Fix super admin test on SQLite \[ [#434](https://github.com/wp-cli/entity-command/pull/434)\]
- Do not assume `get_super_admins()` has the `0` array index \[ [#432](https://github.com/wp-cli/entity-command/pull/432)\]
- Improve SQLite compatibility \[ [#431](https://github.com/wp-cli/entity-command/pull/431)\]
- Fix example for `post create` command \[ [#458](https://github.com/wp-cli/entity-command/pull/458)\]
- Update examples for `user application delete` command \[ [#457](https://github.com/wp-cli/entity-command/pull/457)\]
- Regenerate README file \[ [#456](https://github.com/wp-cli/entity-command/pull/456)\]
- Fix variable name in `application_name_exists` polyfill \[ [#455](https://github.com/wp-cli/entity-command/pull/455)\]
- Add filter `site__user_in` on `wp site list` \[ [#438](https://github.com/wp-cli/entity-command/pull/438)\]

#### [wp-cli/extension-command](https://github.com/wp-cli/extension-command/)

- Regenerate README file \[ [#381](https://github.com/wp-cli/extension-command/pull/381)\]
- Add `update_version` to the default fields for `plugin` and `theme` commands \[ [#380](https://github.com/wp-cli/extension-command/pull/380)\]
- Update some tests for SQLite \[ [#378](https://github.com/wp-cli/extension-command/pull/378)\]
- Remove duplicated code \[ [#391](https://github.com/wp-cli/extension-command/pull/391)\]
- Switch tests to use `site-secrets` instead of `user-switching` \[ [#389](https://github.com/wp-cli/extension-command/pull/389)\]
- Support `'wporg_status'` and `'wporg_last_updated'` as optional `wp plugin list` fields \[ [#382](https://github.com/wp-cli/extension-command/pull/382)\]
- Regenerate README file \[ [#397](https://github.com/wp-cli/extension-command/pull/397)\]
- Added `--minor` and `--patch` CLI option in `wp theme update` \[ [#393](https://github.com/wp-cli/extension-command/pull/393)\]
- Fix counting of errors when attempting activations \[ [#398](https://github.com/wp-cli/extension-command/pull/398)\]

#### [wp-cli/i18n-command](https://github.com/wp-cli/i18n-command/)

- `make-mo`: Add destination file support \[ [#373](https://github.com/wp-cli/i18n-command/pull/373)\]
- Stage the correct files in schema workflow \[ [#370](https://github.com/wp-cli/i18n-command/pull/370)\]
- Update `theme-i18n.json` \[ [#366](https://github.com/wp-cli/i18n-command/pull/366)\]
- Fix file format in `make-php` \[ [#379](https://github.com/wp-cli/i18n-command/pull/379)\]
- Regenerate README file \[ [#378](https://github.com/wp-cli/i18n-command/pull/378)\]
- Add file references for plugin/theme headers \[ [#377](https://github.com/wp-cli/i18n-command/pull/377)\]
- Add `wp i18n make-php` command \[ [#363](https://github.com/wp-cli/i18n-command/pull/363)\]

#### [wp-cli/language-command](https://github.com/wp-cli/language-command/)

- Fix tests after WordPress 6.4 release \[ [#133](https://github.com/wp-cli/language-command/pull/133)\]
- Skip some tests on SQLite \[ [#132](https://github.com/wp-cli/language-command/pull/132)\]
- Allow for PHP 8.2+ warning on old WP core \[ [#130](https://github.com/wp-cli/language-command/pull/130)\]
- Remove use of `@require-wp-latest` \[ [#135](https://github.com/wp-cli/language-command/pull/135)\]
- Re-enable some tests for SQLite \[ [#134](https://github.com/wp-cli/language-command/pull/134)\]
- Properly delete JSON & PHP translation files \[ [#137](https://github.com/wp-cli/language-command/pull/137)\]

#### [wp-cli/maintenance-mode-command](https://github.com/wp-cli/maintenance-mode-command/)

- Evaluate `$upgrading` numeric value when checking if maintenance mode is active \[ [#22](https://github.com/wp-cli/maintenance-mode-command/pull/22)\]

#### [wp-cli/media-command](https://github.com/wp-cli/media-command/)

- Add `--file_name=<name>` argument for `wp media import` \[ [#187](https://github.com/wp-cli/media-command/pull/187)\]

#### [wp-cli/package-command](https://github.com/wp-cli/package-command/)

- Fix compatibility with newer Composer versions \[ [#183](https://github.com/wp-cli/package-command/pull/183)\]

#### [wp-cli/php-cli-tools](https://github.com/wp-cli/php-cli-tools/)

- Fix `maxFlag` to `flagMax` and `maxOption` to `optionMax` typos in `HelpScreen` class \[ [#170](https://github.com/wp-cli/php-cli-tools/pull/170)\]
- Use class instead of static variables for the speed measurement \[ [#168](https://github.com/wp-cli/php-cli-tools/pull/168)\]
- Remove inexistent `post-install-cmd` \[ [#167](https://github.com/wp-cli/php-cli-tools/pull/167)\]
- Fix type hinting for prompt function \[ [#141](https://github.com/wp-cli/php-cli-tools/pull/141)\]

#### [wp-cli/scaffold-command](https://github.com/wp-cli/scaffold-command/)

- Add `@require-mysql` for tests with explicit MySQL dependency \[ [#326](https://github.com/wp-cli/scaffold-command/pull/326)\]
- Remove Travis CI from `wp scaffold plugin-tests` \[ [#325](https://github.com/wp-cli/scaffold-command/pull/325)\]

#### [wp-cli/search-replace-command](https://github.com/wp-cli/search-replace-command/)

- Skip search and replace on objects that can’t deserialize safely \[ [#192](https://github.com/wp-cli/search-replace-command/pull/192)\]

- PHP 8.2 Deprecation: Fix creation of dynamic property. \[ [#193](https://github.com/wp-cli/search-replace-command/pull/193)\]


#### [wp-cli/super-admin-command](https://github.com/wp-cli/super-admin-command/)

- PHP 8.2 Deprecation: Fix creation of dynamic property. \[ [#55](https://github.com/wp-cli/super-admin-command/pull/55)\]

#### [wp-cli/wp-config-transformer](https://github.com/wp-cli/wp-config-transformer/)

- Replace DOS line endings with LF \[ [#49](https://github.com/wp-cli/wp-config-transformer/pull/49)\]
- Fix empty line comment parsing by checking for the existing of a line ending \[ [#48](https://github.com/wp-cli/wp-config-transformer/pull/48)\]

### Contributors

[@2ndkauboy](https://github.com/2ndkauboy), [@benjaminprojas](https://github.com/benjaminprojas), [@benlk](https://github.com/benlk), [@christianwach](https://github.com/christianwach), [@cliffordp](https://github.com/cliffordp), [@connerbw](https://github.com/connerbw), [@Dan-Q](https://github.com/Dan-Q), [@danielbachhuber](https://github.com/danielbachhuber), [@dd32](https://github.com/dd32), [@dlind1](https://github.com/dlind1), [@dougaxe1](https://github.com/dougaxe1), [@drzraf](https://github.com/drzraf), [@elenachavdarova](https://github.com/elenachavdarova), [@ernilambar](https://github.com/ernilambar), [@gedex](https://github.com/gedex), [@gitlost](https://github.com/gitlost), [@greatislander](https://github.com/greatislander), [@herregroen](https://github.com/herregroen), [@janw-me](https://github.com/janw-me), [@jenkoian](https://github.com/jenkoian), [@johnbillion](https://github.com/johnbillion), [@johnrom](https://github.com/johnrom), [@jrfnl](https://github.com/jrfnl), [@JulianBustamante](https://github.com/JulianBustamante), [@kodie](https://github.com/kodie), [@krupal-panchal](https://github.com/krupal-panchal), [@l3ku](https://github.com/l3ku), [@localheinz](https://github.com/localheinz), [@MarkBerube](https://github.com/MarkBerube), [@marksabbath](https://github.com/marksabbath), [@matzeeable](https://github.com/matzeeable), [@michaelzangl](https://github.com/michaelzangl), [@oandregal](https://github.com/oandregal), [@ocean90](https://github.com/ocean90), [@pbiron](https://github.com/pbiron), [@pdaalder](https://github.com/pdaalder), [@pekkakortelainen](https://github.com/pekkakortelainen), [@pfefferle](https://github.com/pfefferle), [@pmbaldha](https://github.com/pmbaldha), [@ponsfrilus](https://github.com/ponsfrilus), [@rodrigoprimo](https://github.com/rodrigoprimo), [@Roy-Orbison](https://github.com/Roy-Orbison), [@sandeshjangam](https://github.com/sandeshjangam), [@schlessera](https://github.com/schlessera), [@sdnunca](https://github.com/sdnunca), [@sejas](https://github.com/sejas), [@selul](https://github.com/selul), [@shail-mehta](https://github.com/shail-mehta), [@shawnhooper](https://github.com/shawnhooper), [@shendy-a8c](https://github.com/shendy-a8c), [@siliconforks](https://github.com/siliconforks), [@Soean](https://github.com/Soean), [@strarsis](https://github.com/strarsis), [@swissspidy](https://github.com/swissspidy), [@thelovekesh](https://github.com/thelovekesh), [@todeveni](https://github.com/todeveni), [@Tug](https://github.com/Tug), [@up1512001](https://github.com/up1512001), [@valeriySeregin](https://github.com/valeriySeregin), [@wojsmol](https://github.com/wojsmol), [@wojtekn](https://github.com/wojtekn), [@xknown](https://github.com/xknown), [@yousan](https://github.com/yousan)

[#release](https://make.wordpress.org/cli/tag/release/), [#v2-10-0](https://make.wordpress.org/cli/tag/v2-10-0/)

[![](https://gravatar.com/avatar/78ed219920991477554b4c2be7967437?d=mystery)](https://profiles.wordpress.org/juliarosia/ "Profile of Julia Golomb (@juliarosia)")

[Julia Golomb](https://profiles.wordpress.org/juliarosia/ "Profile of Julia Golomb (@juliarosia)") [4:20 pm on February 2, 2024](https://make.wordpress.org/cli/2024/02/02/xpost-incident-response-team-call-for-nominations/ "4:20 pm (-05:00) on February 2, 2024")

## X-comment from [+make.wordpress.org/project](https://make.wordpress.org/project/ "WordPress.org Project"): Comment on [Incident Response Team: Call for Nominations](https://make.wordpress.org/project/2024/02/02/incident-response-team-call-for-nominations/\#comment-512 "Summary: Submit your Incident Response Team nominations by February 14, through the button below. The WordPress Project Community Code of Conduct helps WordPress community members and contributors understand how we aspire to work together in “official” WordPress spaces. When people see behavior that doesn’t match the Code of Conduct, the Incident Response Team can assist in determining if the Code of Conduct has been breached and addressing situations that are in question of doing so. The Incident Response Team does not actively search for or monitor behavior. Instead, this team is a resource to the community for when things don’t go as expected. The Incident Response Team handbook captures the team's current practices. The first Incident Response Team cohort was onboarded to the team in D…")

## Site resources

ssearchccompose new postrreplyeedittgo to topjgo to the next post or commentkgo to the previous post or commentotoggle comment visibilityesccancel edit post or comment

0

Clear All