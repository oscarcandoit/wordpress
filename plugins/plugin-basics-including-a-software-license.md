---
url: https://developer.wordpress.org/plugins/plugin-basics/including-a-software-license
scraped_at: 2025-10-20T03:18:57.949Z
---

[Skip to content](https://developer.wordpress.org/plugins/plugin-basics/including-a-software-license/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

Including a Software License


[Home](https://developer.wordpress.org/)[Plugin Handbook](https://developer.wordpress.org/plugins/)[Plugin Basics](https://developer.wordpress.org/plugins/plugin-basics/)Including a Software License

Search

# Including a Software License

[↑ Back to top](https://developer.wordpress.org/plugins/plugin-basics/including-a-software-license/#wp--skip-link--target)

Most WordPress plugins are released under the [GPL](http://www.gnu.org/licenses/gpl.html), which is the same license that [WordPress itself uses](https://wordpress.org/about/license/). However, there are other compatible options available. It is always best to clearly indicate the license your plugin uses.

In the [Header Requirements](https://developer.wordpress.org/plugins/the-basics/header-requirements/) section, we briefly mentioned how you can indicate your plugin’s license within the plugin header comment. Another common, and encouraged, practice is to place a license block comment near the top of your main plugin file (the same one that has the plugin header comment).

This license block comment usually looks something like this:

``
[Expand code](https://developer.wordpress.org/plugins/plugin-basics/including-a-software-license/#)

[Copy](https://developer.wordpress.org/plugins/plugin-basics/including-a-software-license/#)

```php
/*
{Plugin Name} is free software: you can redistribute it and/or modify
it under the terms of the GNU General Public License as published by
the Free Software Foundation, either version 2 of the License, or
any later version.

{Plugin Name} is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the
GNU General Public License for more details.

You should have received a copy of the GNU General Public License
along with {Plugin Name}. If not, see {URI to Plugin License}.
*/
```

First published

September 16, 2014

Last updated

February 20, 2024

[PreviousDetermining Plugin and Content DirectoriesPrevious: Determining Plugin and Content Directories](https://developer.wordpress.org/plugins/plugin-basics/determining-plugin-and-content-directories/)

[NextUninstall MethodsNext: Uninstall Methods](https://developer.wordpress.org/plugins/plugin-basics/uninstall-methods/)

Notifications