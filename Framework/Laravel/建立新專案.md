## 建立新專案

```bash
composer create-project --prefer-dist laravel/laravel project-name
```

## 設定

### 目錄權限

安裝 Laravel 後，你必須對一些權限進行設定。目錄 `storage` 及 `bootstrap/cache` 內的子目錄必須是讓網頁伺服器可寫的，否則 Laravel 就無法正常執行。
