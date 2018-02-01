"# StartAndroidKotlin" 







Подключение по ssh к github.com

Уже не раз стыкался с проблемой: Невозможно склонировать по ssh c github git проэкт проверяем порт по default обычно 22

$ ssh -T git@github.com

ssh: connect to host github.com port 22: Connection timed out

проверяем по 443 порту

$ ssh -T -p 443 git@ssh.github.com

The authenticity of host '[ssh.github.com]:443 ([192.30.253.123]:443)' can't be establishe d. RSA key fingerprint is SHA256:nThbg6kXUpJWGl7E1IGOCspRomTxdCARLviKw6E5SY8. Are you sure you want to continue connecting (yes/no)? yes Warning: Permanently added '[ssh.github.com]:443,[192.30.253.123]:443' (RSA) to the list of known hosts. Hi splaa! You've successfully authenticated, but GitHub does not provide shell access.

если по 443 всё Ок то сылка должна иметь вид

ssh://git@ssh.github.com:443/yourname/reponame.git git clone ssh://git@ssh.github.com:443/SevenPowerX-PHP/StartPHP.git



Изменить origin адрес репозитория двумя способами:

1) Первый способ задать url репозитория:

использовать команду git remote set-url origin, например:

git remote set-url origin git@github.com:vicman-wi/wi-backend.git

2) Второй способ:

Отредактировать файл .git/config: секция [remote "origin"] параметр - url. 

 

Эти два способа идентичные. Т.е. вызов команды git remote set-url origin заменит содержимое git конфига.
