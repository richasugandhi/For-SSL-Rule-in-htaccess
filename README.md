<IfModule mod_rewrite.c>
RewriteEngine on
RewriteCond %{HTTPS} !=on
RewriteRule ^ https://%{HTTP_HOST}%{REQUEST_URI} [L,R=301]


RewriteCond $1 !^(index\.php|images|js|css|transunion|fonts|assets|pixie|documentation|captcha|uploads|letters|phpThumb|ckeditor|ckfinder|swfupload|robots|timthumb|favicon\.ico|info1.php\.txt|phpMyAdmin)
RewriteCond %{REQUEST_FILENAME} !-f
RewriteCond %{REQUEST_FILENAME} !-d
RewriteRule ^(.*)$ index.php/$1 [L,QSA] 


RewriteRule \.(csv|md|fla|docx|mp3)$ - [F,NS,L]
</IfModule>
