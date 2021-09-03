# htaccess for nextjs static site

## this var can help you if you has some problem with routing in urls with folders and server

```
# Disable directory indexes and MultiViews
Options -Indexes -MultiViews

# Prevent mod_dir appending a slash to directory requests
DirectorySlash Off

# Prevent any further processing if the URL already ends with a file extension
RewriteRule \.\w{2.4}$ - [L]

# Redirect any requests to remove a trailing slash
RewriteRule (.*)/$ /$1 [R=301,L]

# Rewrite /foo to /foo.html if it exists
RewriteCond %{DOCUMENT_ROOT}/$1.html -f
RewriteRule (.*) $1.html [L]

# Otherwise, rewrite /foo to /foo/index.html if it exists
RewriteCond %{DOCUMENT_ROOT}/$1/index.html -f
RewriteRule (.*) $1/index.html [L]

```


