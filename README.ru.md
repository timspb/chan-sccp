# chan-sccp

Этот репозиторий содержит рабочую сборку драйвера chan-sccp для телефонов Cisco SCCP в Asterisk.

Это короткий README для форка: только сборка, установка и базовое использование.

Русская версия: [README.md](README.md)

Проверенный диапазон для этого форка:

- FreePBX 16 или 17
- Asterisk 21 / 22 / 23

## Для чего проект

- Поддержка Cisco SCCP/Skinny телефонов в Asterisk
- Регистрация устройств и обработка вызовов
- Provisioning для SCCP-установок

## Что нужно

- Сборка Asterisk с заголовками и dev-пакетами
- Инструменты сборки: `gcc`, `make`, `autoconf`, `libtool`
- Библиотеки XML/XSLT
- Библиотеки OpenSSL
- `gettext`

Если в системе есть пакетный менеджер, сначала поставьте обычные dev-пакеты. Точные названия пакетов зависят от дистрибутива.

## Сборка из исходников

```bash
git clone https://github.com/timspb/chan-sccp.git
cd chan-sccp
./tools/bootstrap.sh
./configure
make -j2
make install
make reload
```

Если вы обновляете уже существующую копию:

```bash
git pull
./tools/bootstrap.sh
./configure
make -j2
make install
make reload
```

## Примечания

- Этот форк рассчитан на практическое использование и активную разработку.
- README специально короткий, чтобы пользователь быстро дошёл до установки.
- Оригинальный upstream проекта остаётся каноническим источником chan-sccp.

## Если что-то не работает

- Если `./configure` падает, проверьте установку dev-пакетов.
- Если сборка не находит заголовки Asterisk, поставьте matching Asterisk dev package для вашей версии.
- Если драйвер не загружается, смотрите логи Asterisk и проверку модулей.
