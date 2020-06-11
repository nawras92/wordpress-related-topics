# Enable GZIP Compression

- Add this code to the .htaccess file in the website root directory.

*This code will only work on apache servers.*

```
# Enable gzip compression for HTML, CSS, JS, and XML

<IfModule mod_deflate.c>

  AddOutputFilterByType DEFLATE application/javascript
  AddOutputFilterByType DEFLATE application/xhtml+xml
  AddOutputFilterByType DEFLATE application/xml

  AddOutputFilterByType DEFLATE text/css
  AddOutputFilterByType DEFLATE text/html
  AddOutputFilterByType DEFLATE text/javascript
  AddOutputFilterByType DEFLATE text/plain
  AddOutputFilterByType DEFLATE text/xml

</IfModule>
```
