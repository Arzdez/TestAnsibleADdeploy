# Первый вариант плейбуки разворачивающий доменконтроллер на windows server2016+

Реазизовано 2 варианта:

- Команды на [PowerShell](/ADdeployPS.yaml)
- С помощью модуля ansible [microsoft.ad](/ADdeployAM.yaml)

Чтобы ходить на хосты под управлением  ОС Windows Ansible использет службу [WinRm](https://learn.microsoft.com/ru-ru/windows/win32/winrm/portal), но нужно произвести некоторые настройки в Windows.В простейшем случае достаточно включить Basic auth для WinRm:
```PowerShell
winrm set winrm/config/client/auth '@{Basic="true"}'

winrm set winrm/config/service/auth '@{Basic="true"}'

winrm set winrm/config/service '@{AllowUnencrypted="true"}'

```