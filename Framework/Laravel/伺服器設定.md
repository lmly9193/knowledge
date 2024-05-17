## Apache

Laravel 內包含了一個 `public/.htaccess` 檔案用於讓 URLs 路徑不帶有前端控制器 `index.php`。使用 Apache 部署 Laravel 前，請確認是否將 `mod_rewrite` 模組啟用，這樣 `.htaccess` 檔案才能夠正確的被伺服器正確解析。

如果 Laravel 專案內預先搭載的 `.htaccess` 檔案在你的 Apache 環境下不能使用，你可以嘗試這個方法：

```text
Options +FollowSymLinks
RewriteEngine On

RewriteCond %{REQUEST_FILENAME} !-d
RewriteCond %{REQUEST_FILENAME} !-f
RewriteRule ^ index.php [L]
```

## Nginx

若你是使用 Nginx，可以透過在你的網站設定內加入以下的指令來導向所有的請求至 `index.php` 前端控制器：

```text
location / {
    try_files $uri $uri/ /index.php?$query_string;
}
```
