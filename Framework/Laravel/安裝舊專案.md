## 安裝已存在的專案

1. 您需要先設定 `env` 設定檔，基本上你在整個專案找不到 `.env` 這個檔案，你只會看到 `.env.example` 這個檔案，沒錯，看到 `.example` 就知道這檔案是個範例，你可以複製一個改名為 `.env` 即可，然後開始要修改裡面的參數，哪些必填哪些選填，範例檔案內會有詳細解釋。

2. 您可能需要安裝 `composer` 才能啟用整個網站。
    ```sh
    composer install
    ```

3. 您可能需要安裝 `npm` 才能啟用前端的東西。
    ```sh
    npm install
    ```

4. 你需要產生 `Laravel` 在加密時會需要使用到的密鑰，這點在 `.env.example` 當中有提到。
    ```sh
    php artisan key:generate
    ```

5. 因為會需要使用到資料庫，所以你就去裝一裝你順眼的資料庫，然後去 `env` 設定一下參數吧，如果還沒設定的記得去設定，然後再做資料庫遷移。
    ```sh
    php artisan migrate --seed
    ```

7. 最後你需要把 `storage` 與 `public` 製作個連結，這樣部分檔案才能正常讀取，例如使用者的大頭貼。
    ```
    php artisan storage:link
    ```
