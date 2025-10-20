---
url: https://developer.wordpress.org/cli/commands/embed/fetch/
scraped_at: 2025-10-20T03:05:27.461Z
---

[Skip to content](https://developer.wordpress.org/cli/commands/embed-2/fetch/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

wp embed fetch


[Home](https://developer.wordpress.org/)[WP-CLI Commands](https://developer.wordpress.org/cli/commands/)[wp embed](https://developer.wordpress.org/cli/commands/embed-2/)wp embed fetch

Search

# [wp embed fetch](https://developer.wordpress.org/cli/commands/embed-2/fetch/)

Attempts to convert a URL into embed HTML.

## In this article

Table of Contents

- [Options](https://developer.wordpress.org/cli/commands/embed-2/fetch/#options)
- [Examples](https://developer.wordpress.org/cli/commands/embed-2/fetch/#examples)
- [Global Parameters](https://developer.wordpress.org/cli/commands/embed-2/fetch/#global-parameters)

[↑ Back to top](https://developer.wordpress.org/cli/commands/embed-2/fetch/#wp--skip-link--target)

[![GitHub](https://make.wordpress.org/cli/wp-content/plugins/wporg-cli/assets/images/github-mark.svg)](https://github.com/wp-cli/embed-command)

[View Open Issues (0)](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Aembed-fetch+sort%3Aupdated-desc+org%3Awp-cli+is%3Aopen) [View Closed Issues (6)](https://github.com/login?return_to=%2Fissues%3Fq%3Dlabel%3Acommand%3Aembed-fetch+sort%3Aupdated-desc+org%3Awp-cli+is%3Aclosed) [Create New Issue](https://github.com/wp-cli/embed-command/issues/new)

In non-raw mode, starts by checking the URL against the regex of the registered embed handlers. If none of the regex matches and it’s enabled, then the URL will be given to the [WP\_oEmbed](https://developer.wordpress.org/reference/classes/wp_oembed/) class.

In raw mode, checks the providers directly and returns the data.

### [Options](https://developer.wordpress.org/cli/commands/embed-2/fetch/\#options)

<url>URL to retrieve oEmbed data for.\[--width=<width>\]Width of the embed in pixels.\[--height=<height>\]Height of the embed in pixels.\[--post-id=<id>\]Cache oEmbed response for a given post.\[--discover\]Enable oEmbed discovery. Defaults to true.\[--skip-cache\]Ignore already cached oEmbed responses. Has no effect if using the ‘raw’ option, which doesn’t use the cache.\[--skip-sanitization\]Remove the filter that WordPress from 4.4 onwards uses to sanitize oEmbed responses. Has no effect if using the ‘raw’ option, which by-passes sanitization.\[--do-shortcode\]If the URL is handled by a registered embed handler and returns a shortcode, do shortcode and return result. Has no effect if using the ‘raw’ option, which by-passes handlers.\[--limit-response-size=<size>\]Limit the size of the resulting HTML when using discovery. Default 150 KB (the standard WordPress limit). Not compatible with ‘no-discover’.\[--raw\]Return the raw oEmbed response instead of the resulting HTML. Ignores the cache and does not sanitize responses or use registered embed handlers.\[--raw-format=<json\|xml>\]Render raw oEmbed data in a particular format. Defaults to json. Can only be specified in conjunction with the ‘raw’ option.

—

options:

– json

– xml

—

### [Examples](https://developer.wordpress.org/cli/commands/embed-2/fetch/\#examples)

```
# Get embed HTML for a given URL.
$ wp embed fetch https://www.youtube.com/watch?v=dQw4w9WgXcQ
&lt;iframe width="525" height="295" src="https://www.youtube.com/embed/dQw4w9WgXcQ?feature=oembed" ...

# Get raw oEmbed data for a given URL.
$ wp embed fetch https://www.youtube.com/watch?v=dQw4w9WgXcQ --raw
{"author_url":"https:\/\/www.youtube.com\/user\/RickAstleyVEVO","width":525,"version":"1.0", ...

```

### [Global Parameters](https://developer.wordpress.org/cli/commands/embed-2/fetch/\#global-parameters)

These [global parameters](https://make.wordpress.org/cli/handbook/config/) have the same behavior across all commands and affect how WP-CLI interacts with WordPress.

| **Argument** | **Description** |
| :-- | :-- |
| `--path=<path>` | Path to the WordPress files. |
| `--url=<url>` | Pretend request came from given URL. In multisite, this argument is how the target site is specified. |
| `--ssh=[<scheme>:][<user>@]<host\|container>[:<port>][<path>]` | Perform operation against a remote server over SSH (or a container using scheme of “docker”, “docker-compose”, “docker-compose-run”, “vagrant”). |
| `--http=<http>` | Perform operation against a remote WordPress installation over HTTP. |
| `--user=<id\|login\|email>` | Set the WordPress user. |
| `--skip-plugins[=<plugins>]` | Skip loading all plugins, or a comma-separated list of plugins. Note: mu-plugins are still loaded. |
| `--skip-themes[=<themes>]` | Skip loading all themes, or a comma-separated list of themes. |
| `--skip-packages` | Skip loading all installed packages. |
| `--require=<path>` | Load PHP file before running the command (may be used more than once). |
| `--exec=<php-code>` | Execute PHP code before running the command (may be used more than once). |
| `--context=<context>` | Load WordPress in a given context. |
| `--[no-]color` | Whether to colorize the output. |
| `--debug[=<group>]` | Show all PHP errors and add verbosity to WP-CLI output. Built-in groups include: bootstrap, commandfactory, and help. |
| `--prompt[=<assoc>]` | Prompt the user to enter values for all command arguments, or a subset specified as comma-separated values. |
| `--quiet` | Suppress informational messages. |

_Command documentation is regenerated at every release. To add or update an example, please submit a pull request against the corresponding part of the codebase._

Notifications