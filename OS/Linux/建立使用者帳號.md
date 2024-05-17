```shell
$ adduser username
# 程式會提示輸入密碼，剩下的欄位都可以直接按 Enter 跳過不填。

$ usermod -aG sudo username
# 加入sudo群組
```

```shell
$ adduser --help
adduser [--home DIR] [--shell SHELL] [--no-create-home] [--uid ID] [--firstuid ID] [--lastuid ID] [--gecos GECOS] [--ingroup GROUP | --gid ID] [--disabled-password] [--disabled-login] [--add_extra_groups] [--encrypt-home] USER
   新增一般使用者

adduser --system [--home DIR] [--shell SHELL] [--no-create-home] [--uid ID] [--gecos GECOS] [--group | --ingroup GROUP | --gid ID] [--disabled-password] [--disabled-login] [--add_extra_groups] USER
   新增系統使用者

adduser --group [--gid ID] GROUP
addgroup [--gid ID] GROUP
   新增一個使用者群組

addgroup --system [--gid ID] GROUP
   新增一個系統群組

adduser USER GROUP
   將現有使用者加入現有的群組

general options:
  --quiet | -q      不要將處理資訊輸出到 stdout
  --force-badname   允許不符合 NAME_REGEX[_SYSTEM] 設定變數的使用者名稱
  --extrausers      使用額外的使用者作為資料庫
  --help | -h       使用說明訊息
  --version | -v    版本號碼和版權資訊
  --conf | -c FILE  使用 FILE 作為設定檔案
```

```shell
$ usermod --help
Usage: usermod [options] LOGIN

Options:
  -b, --badnames                允許使用不良名稱
  -c, --comment COMMENT         GECOS 欄位的新值
  -d, --home HOME_DIR           用戶帳戶的新家目錄
  -e, --expiredate EXPIRE_DATE  將帳戶到期日期設置為 EXPIRE_DATE
  -f, --inactive INACTIVE       在帳戶過期後將密碼設置為 INACTIVE
  -g, --gid GROUP               將 GROUP 強制用作新的主要組
  -G, --groups GROUPS           新的輔助 GROUP 清單
  -a, --append                  在不刪除用戶從其他組中刪除的情況下，將用戶附加到 -G 選項提到的補充 GROUP 中
  -h, --help                    顯示此幫助消息並退出
  -l, --login NEW_LOGIN         登錄名稱的新值
  -L, --lock                    鎖定用戶帳戶
  -m, --move-home               將家目錄的內容移動到新位置（僅使用 -d）
  -o, --non-unique              允許使用重複（非唯一）UID
  -p, --password PASSWORD       使用加密密碼設置新密碼
  -R, --root CHROOT_DIR         chroot 到的目錄
  -P, --prefix PREFIX_DIR       位於 /etc/* 檔案所在的前綴目錄
  -s, --shell SHELL             用戶帳戶的新登錄 Shell
  -u, --uid UID                 用戶帳戶的新 UID
  -U, --unlock                  解鎖用戶帳戶
  -v, --add-subuids FIRST-LAST  添加下屬 UID 範圍
  -V, --del-subuids FIRST-LAST  刪除下屬 UID 範圍
  -w, --add-subgids FIRST-LAST  添加下屬 GID 範圍
  -W, --del-subgids FIRST-LAST  刪除下屬 GID 範圍
  -Z, --selinux-user SEUSER     用戶帳戶的新 SELinux 用戶映射
```

