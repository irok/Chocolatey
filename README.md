[Chocolatey](https://chocolatey.org/)

# インストール方法

`cmd.exe`を管理者として実行し、以下のコマンドを実行。

```
@powershell -NoProfile -ExecutionPolicy Bypass -Command "iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1'))" && SET "PATH=%PATH%;%ALLUSERSPROFILE%\chocolatey\bin"
```

続いて`packages.config`に設定しておいたアプリケーションをインストール。

```
cinst packages.config -y
```

もし、以下のようなエラーが表示された場合は

```
WARNING: Missing package checksums are not allowed (by default for HTTP/FTP,
 HTTPS when feature 'allowEmptyChecksumsSecure' is disabled) for
 safety and security reasons. Although we strongly advise against it,
 if you need this functionality, please set the feature
 'allowEmptyChecksums' ('choco feature enable -n
 allowEmptyChecksums')
 or pass in the option '--allow-empty-checksums'. You can also pass
 checksums at runtime (recommended). See choco install -? for details.
The integrity of the file 'php-7.0.9-nts-Win32-VC14-x64.zip' from 'http://windows.php.net/downloads/releases/archives/php-7.0.9-nts-Win32-VC14-x64.zip' has not been verified by a checksum in the package scripts.
Do you wish to allow the install to continue (not recommended)?
[Y] Yes [N] No (default is "N")
N
ERROR: Empty checksums are no longer allowed by default for non-secure sources. Please ask the maintainer to add checksums to this package. In the meantime if you need this package to work correctly, please enable the feature allowEmptyChecksums, provide the runtime switch '--allow-empty-checksums', or pass in checksums at runtime (recommended - see 'choco install -?' / 'choco upgrade -?' for details). It is strongly advised against allowing empty checksums for non-internal HTTP/FTP sources.
Environment Vars (like PATH) have changed. Close/reopen your shell to
 see the changes (or in powershell/cmd.exe just type `refreshenv`).
The install of php was NOT successful.
Error while running 'C:\ProgramData\chocolatey\lib\php\tools\chocolateyInstall.ps1'.
 See log for details.

Chocolatey installed 0/1 packages. 1 packages failed.
 See the log for details (C:\ProgramData\chocolatey\logs\chocolatey.log).

Failures
 - php (exited -1) - Error while running 'C:\ProgramData\chocolatey\lib\php\tools\chocolateyInstall.ps1'.
 See log for details.
```

インストールオプションとして `--allow-empty-checksums` を指定する。
