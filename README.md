# GeoIP-Nginx-Block
Блокировка стран с помощью GeoIP - минималистичный гайд для Debian/Ubuntu без пересборки Nginx из исходников с автообновлением

# Установка необходимых пакетов (Debian/Ubuntu)
apt-get update && apt-get install -y libnginx-mod-http-geoip2 libnginx-mod-http-geoip

Git Репозиторий с актуальными mmdb - перезалив от P3TERX в открытом доступе, без регистраций на сайте и прочего.
https://github.com/P3TERX/GeoLite.mmdb

Скачиваем - cd /usr/share/GeoIP && wget https://git.io/GeoLite2-Country.mmdb

# И приступаем к конфигурации nginx
 1. nginx.conf
 2. sites-available/*.conf

# Добавляем скрипт autoupdate_db.sh в cron раз в неделю
00 6 * * SAT bash /srv/scripts/autoupdate_db.sh