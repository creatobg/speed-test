# Speed Test Page by Kреато

Тази уеб страница е предназначена за **измерване на скоростта на зареждане** на ресурси при различни хостинг конфигурации – директно зареждане или през CDN.

## 📦 Съдържание

- HTML страница с вградени изображения (общ размер ~6.6 MB)
- Целта е да се измери:
    - Време до първи байт (TTFB)
    - Общо време за зареждане
    - Брой заявки
    - Влияние на CDN (ако е приложим)

## 🚀 Инструкции за тестване

1. **Качи папката `speed-test/` на сървъра си.**

2. **Отвори [WebPageTest](https://www.webpagetest.org/)**:
    - Въведи URL: `https://domain1.bg/speed-test/index.html`
    - Избери локация и браузър
    - Стартирай теста
    - Анализирай:
        - First Byte Time
        - Fully Loaded Time
        - Total Requests
        - Waterfall диаграма

3. **Алтернатива с `curl` в терминал:**

   ```bash
   curl -o /dev/null -s -w "DNS: %{time_namelookup}s\nConnect: %{time_connect}s\nStart Transfer: %{time_starttransfer}s\nTotal: %{time_total}s\n" https://domain1.bg/speed-test/index.html

   curl -o /dev/null -s -w "DNS: %{time_namelookup}s\nConnect: %{time_connect}s\nStart Transfer: %{time_starttransfer}s\nTotal: %{time_total}s\n" https://domain2.bg/speed-test/index.html
   ```

Този проект е създаден за вътрешно тестване и сравнение на производителността между различни хостинг решения и/или CDN услуги. Уеб страницата съдържа изображения с достатъчен обем, за да бъдат забелязани разлики в: време за зареждане, кеширане, компресия, и скорост на доставка.