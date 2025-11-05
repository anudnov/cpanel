Перейди в папку с логами:
cd /usr/local/apache/domlogs/

посмотреть топ-IP
Если хочешь узнать, какие IP-адреса делали эти запросы:
```
grep "03:22" example.com | awk '{print $1}' | sort | uniq -c | sort -nr | head
```

Если хочешь искать диапазон времени
Например, между 03:20 и 03:25:
```
grep -E "03:2[0-5]" * | awk -F: '{print $1}' | sort | uniq -c | sort -nr | head
```
Если логи уже сжаты (.gz)
```
zgrep "03:22" /usr/local/apache/domlogs/*.gz | awk -F: '{print $1}' | sort | uniq -c | sort -nr | head
```
