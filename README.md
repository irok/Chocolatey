[Chocolatey](https://chocolatey.org/)

# インストール方法

`cmd.exe`を管理者として実行し、以下のコマンドを実行。

```
@powershell -NoProfile -ExecutionPolicy Bypass -Command "iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1'))" && SET "PATH=%PATH%;%ALLUSERSPROFILE%\chocolatey\bin"
```

続いて`packages.config`に設定しておいたアプリケーションをインストール。

```
cinst packages.config
```
