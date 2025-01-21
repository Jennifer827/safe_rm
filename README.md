# safe_rm

通常，シンボリックリンクを rm するとオリジナルのディレクトリやファイルまで消えてしまいます．それに伴う事故を防止するため，シンボリックリンクを rm するとリンクだけが削除され，オリジナルのディレクトリやファイルは削除されないコマンド**safe_rm**を作成しました．safe_rm を通常の rm コマンドにラップすることで，想定外の事故を防止することができます．

Removing a symbolic link with the `rm` command also deletes the original directory or file it points to. To prevent such accidents, I have developed a command called **safe_rm**, which deletes only the symbolic link while leaving the original directory or file intact. By wrapping the standard `rm` command with **safe_rm**, you can prevent unintended mishaps effectively.

## 使用方法 / Usage

1. /bin/safe_rm を作成し本リポジトリの safe_rm をコピペ，権限も変更

   Create `/bin/safe_rm`, copy the `safe_rm` from this repository, and modify its permissions.

```sh
    touch /bin/safe_rm
    chmod 777 /bin/safe_rm
```

2. .bashrc にエイリアスを追加

   Add an alias to `.bashrc`.

```sh
    alias rm='/bin/safe_rm'
```

3. .bashrc を読み込み

   Reload the `.bashrc` file.

```sh
    source .bashrc
```
