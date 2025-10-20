# WordPress Documentation - Claude Code Quick Reference

**For Claude Code AI Assistant - Optimized Search Patterns**

This guide helps Claude Code quickly find the right documentation when you ask questions.

---

## Quick Search Commands

### By Topic (Common Questions)

```bash
# Security & Nonces
grep -r "nonce" /Users/andrewpage/documents/clients/_docs/WordPress/plugins/security/ --include="*.md"

# Transients (Caching)
grep -r "transient" /Users/andrewpage/documents/clients/_docs/WordPress/apis/ --include="*.md"

# WP_Cron (Scheduled Tasks)
grep -r "wp_cron\|cron" /Users/andrewpage/documents/clients/_docs/WordPress/plugins/cron/ --include="*.md" -i

# AJAX
grep -r "ajax" /Users/andrewpage/documents/clients/_docs/WordPress/plugins/javascript/ --include="*.md" -i

# REST API
grep -r "rest\|endpoint" /Users/andrewpage/documents/clients/_docs/WordPress/rest-api/ --include="*.md" -i

# Custom Post Types
grep -r "register_post_type\|custom post type" /Users/andrewpage/documents/clients/_docs/WordPress/plugins/post-types/ --include="*.md" -i

# Settings API
grep -r "settings.*api\|register_setting" /Users/andrewpage/documents/clients/_docs/WordPress/plugins/settings/ --include="*.md" -i

# Hooks (Actions & Filters)
grep -r "add_action\|add_filter\|hooks" /Users/andrewpage/documents/clients/_docs/WordPress/plugins/hooks/ --include="*.md" -i

# WordPress Coding Standards
grep -r "phpcs\|coding.*standard" /Users/andrewpage/documents/clients/_docs/WordPress/coding-standards/ --include="*.md" -i
```

---

## Direct Path Mapping (Question → File Location)

### Plugin Development Questions

| User Question | Primary Location | File Count |
|---------------|------------------|------------|
| "How do I create a plugin?" | `/plugins/plugin-basics/` | 15 files |
| "How do I use nonces?" | `/plugins/security/nonces.md` | 1 file |
| "How do I validate input?" | `/plugins/security/data-validation.md` | 1 file |
| "How do I sanitize data?" | `/plugins/security/securing-input.md` | 1 file |
| "How do I escape output?" | `/plugins/security/securing-output.md` | 1 file |
| "How do I use transients?" | `/apis/transients.md` | 1 file |
| "How do I use WP_Cron?" | `/plugins/cron/` | 3 files |
| "How do I use AJAX?" | `/plugins/javascript/ajax/` | 14 files |
| "How do I create REST endpoints?" | `/rest-api/` | 62 files |
| "How do I create custom post types?" | `/plugins/post-types/` | 8 files |
| "How do I add plugin settings?" | `/plugins/settings/` | 5 files |
| "How do I prevent plugin conflicts?" | `/plugins/plugin-basics/best-practices.md` | 1 file |
| "How do I submit to WordPress.org?" | `/plugins/wordpress-org/` | 10 files |

### Theme Development Questions

| User Question | Primary Location | File Count |
|---------------|------------------|------------|
| "How do I create a WordPress theme?" | `/themes/` | 123 files |
| "What is template hierarchy?" | `/themes/template-hierarchy/` | 8 files |
| "How do I create a block theme?" | `/block-editor/` | 169 files |
| "How do I use theme.json?" | `/block-editor/how-to-guides/themes/` | 15 files |
| "How do I enqueue scripts?" | `/plugins/javascript/enqueuing/` | 2 files |
| "How do I create custom widgets?" | `/themes/theme-functions/widgets.md` | 1 file |
| "How do I create a child theme?" | `/themes/advanced-topics/child-themes.md` | 1 file |

### Advanced WordPress Questions

| User Question | Primary Location | File Count |
|---------------|------------------|------------|
| "How do I use the Options API?" | `/apis/options.md` | 1 file |
| "How do I create database tables?" | `/plugins/creating-tables-with-plugins/` | 1 file |
| "How do I use prepared statements?" | `/apis/wpdb.md` | 1 file |
| "How do I implement user roles?" | `/apis/user-roles-capabilities.md` | 1 file |
| "How do I use WordPress filesystem?" | `/apis/filesystem.md` | 1 file |

### Technology-Specific Questions

| User Question | Primary Location | File Count |
|---------------|------------------|------------|
| "PHP syntax?" | `/php/` | 484 files |
| "MySQL queries?" | `/mysql/` | 201 files |
| "Bootstrap components?" | `/bootstrap/` | 272 files |
| "jQuery methods?" | `/jquery/` | 319 files |
| "CSS properties?" | `/css/` | 141 files |
| "WooCommerce hooks?" | `/woocommerce/` | 240 files |
| "ACF functions?" | `/advanced-custom-fields/` | 218 files |
| "WP-CLI commands?" | `/cli/` | 245 files |

---

## Common Development Workflows

### 1. "I want to build a secure WordPress plugin"

**Search Order:**
1. `/plugins/plugin-basics/` - Plugin structure
2. `/plugins/security/` - Security (nonces, validation, sanitization)
3. `/coding-standards/` - PHPCS compliance
4. `/plugins/hooks/` - Actions and filters
5. `/apis/` - WordPress APIs
6. `/plugins/wordpress-org/` - Submission guidelines

**Key Files:**
- `plugins/security/nonces.md`
- `plugins/security/data-validation.md`
- `plugins/security/securing-input.md`
- `plugins/security/securing-output.md`
- `coding-standards/wordpress-coding-standards/`

### 2. "I want to add AJAX to my plugin"

**Search Order:**
1. `/plugins/javascript/ajax/` - AJAX implementation
2. `/plugins/security/nonces.md` - Nonce verification for AJAX
3. `/jquery/` - jQuery syntax

**Key Files:**
- `plugins/javascript/ajax/`

### 3. "I want to create a REST API endpoint"

**Search Order:**
1. `/rest-api/` - REST API documentation
2. `/plugins/security/` - Authentication & permissions
3. `/reference/` - Function references

**Key Files:**
- `rest-api/extending-the-rest-api/`
- `rest-api/using-the-rest-api/`

### 4. "I want to build a block theme (FSE)"

**Search Order:**
1. `/block-editor/` - Gutenberg/FSE docs
2. `/themes/` - Theme basics
3. `/css/` or `/bootstrap/` - Styling

**Key Files:**
- `block-editor/how-to-guides/themes/`
- `block-editor/reference-guides/block-api/`

### 5. "I want to add caching to my plugin"

**Search Order:**
1. `/apis/transients.md` - Transients API
2. `/plugins/` - Implementation examples

**Key Files:**
- `apis/transients.md`

### 6. "I want to schedule background tasks"

**Search Order:**
1. `/plugins/cron/` - WP_Cron implementation
2. `/apis/` - WordPress APIs

**Key Files:**
- `plugins/cron/`

---

## Integration with Elementor Documentation

When questions involve both WordPress and Elementor:

### "I want to create an Elementor widget"

**WordPress Docs:**
- `/plugins/plugin-basics/` - Plugin structure
- `/plugins/hooks/` - WordPress hooks
- `/php/` - PHP syntax

**Elementor Docs:**
- `/docs/widgets/` - Widget creation
- `/docs/editor-controls/` - All 45 control types
- `/docs/hooks/` - Elementor hooks

### "I want to create an Elementor theme"

**WordPress Docs:**
- `/themes/` - WordPress theme basics
- `/themes/template-hierarchy/` - Template structure

**Elementor Docs:**
- `/docs/themes/` - Elementor theme integration
- `/docs/hello-elementor-theme/` - Base theme
- `/docs/theme-conditions/` - Template logic

---

## Function Reference Lookup

For specific WordPress functions:

```bash
# Search function reference
grep -r "function_name" /Users/andrewpage/documents/clients/_docs/WordPress/reference/ --include="*.md"

# Search across all docs
grep -r "function_name" /Users/andrewpage/documents/clients/_docs/WordPress/ --include="*.md"
```

**Example:**
```bash
grep -r "wp_enqueue_script" /Users/andrewpage/documents/clients/_docs/WordPress/ --include="*.md"
```

---

## File Naming Patterns

Understanding file naming helps predict locations:

- `*-block.md` → Block Editor documentation (root or `/block-editor/`)
- `*-embed.md` → oEmbed providers (root)
- `*-screen.md` → WordPress admin screens (root)
- `twenty-*.md` → Theme changelogs (root)
- `get-*.md`, `wp-*.md`, `the-*.md` → Function references (`/reference/` or root)

---

## Search Tips for Claude

### Multi-term Search
```bash
grep -r "term1\|term2" /path/ --include="*.md" -i
```

### Case-Insensitive Search
```bash
grep -r "term" /path/ --include="*.md" -i
```

### Search with Context (show 3 lines before/after)
```bash
grep -r "term" /path/ --include="*.md" -A 3 -B 3
```

### Search File Names Only
```bash
find /Users/andrewpage/documents/clients/_docs/WordPress/ -name "*keyword*.md"
```

### Count Matches
```bash
grep -r "term" /path/ --include="*.md" | wc -l
```

---

## Priority Folders for Common Tasks

### Security & WordPress.org Submission
1. `/plugins/security/` (5 files)
2. `/coding-standards/` (14 files)
3. `/plugins/wordpress-org/` (10 files)

### Advanced Features
1. `/apis/` (42 files) - Transients, Options, Security
2. `/plugins/cron/` (3 files) - Scheduled tasks
3. `/rest-api/` (62 files) - API development
4. `/plugins/javascript/ajax/` (14 files) - AJAX

### Full-Stack Development
1. `/php/` (484 files)
2. `/mysql/` (201 files)
3. `/bootstrap/` (272 files)
4. `/jquery/` (319 files)

---

## Quick Stats

**Total Files:** 3,293 markdown files

**Top Categories:**
- PHP: 484 files
- jQuery: 319 files
- Bootstrap: 272 files
- WP-CLI: 245 files
- WooCommerce: 240 files
- ACF: 218 files
- Reference: 172 files
- Block Editor: 169 files
- CSS: 141 files
- Themes: 123 files

---

## When User Asks...

| Question Pattern | Action |
|------------------|--------|
| "Where's the documentation for X?" | Use grep to search for X across relevant folders |
| "How do I implement X?" | Check workflow section above, then search specific folders |
| "What's the function for X?" | Search `/reference/` first, then all docs |
| "Show me examples of X" | Search all docs with grep, read relevant files |
| "Is there documentation on X?" | Search all docs, report findings with file paths |

---

**Repository:** https://github.com/oscarcandoit/wordpress
**Companion:** https://github.com/oscarcandoit/elementor-docs
**Local Path:** `/Users/andrewpage/documents/clients/_docs/WordPress/`
