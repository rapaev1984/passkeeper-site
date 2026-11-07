# PassKeeper_ru — публичный сайт приложения (pkeeper.ru)

Статика без сборки: `index.html` (витрина) + `privacy.html` (политика конфиденциальности)
+ `CNAME` (домен для GitHub Pages).

## Перед публикацией — заменить заготовки

- [ ] `rapaev.vl@mail.ru` — завести почтовый ящик/пересылку у регистратора домена
      (или заменить на реальный адрес в `index.html` и `privacy.html`);
- [x] скриншоты сняты с эмулятора (1080×2400, каталог `screenshots/`) и вставлены в сайт;
      те же файлы пойдут в RuStore;
- [ ] кнопка «Скачать в RuStore» — после публикации вставить ссылку карточки
      (например `https://apps.rustore.ru/app/ru.pkeeper.passkeeper`);
- [ ] дата и реквизиты оператора в `privacy.html` (если нужно указать ИП/ФИО — в п. 1).

## Деплой на GitHub Pages (бесплатно, свой домен)

> Репозиторий сайта отдельный и публичный — секретов в нём нет, публикации не мешает.

1. Создать **публичный** репозиторий (например `rapaev1984/keeper-site`);
2. Скопировать туда `index.html`, `privacy.html`, `CNAME`, каталог `screenshots/`;
3. Settings → Pages → Source: **Deploy from a branch** → `main` / `/ (root)` → Save;
4. Дождаться первого деплоя (~1 мин), затем в Pages появится выпуск сертификата
   для кастомного домена — включить **Enforce HTTPS**;
5. **DNS у регистратора pkeeper.ru:**
   - `A` `@` → `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`
     (адреса GitHub Pages);
   - `CNAME` `www` → `rapaev1984.github.io.` (как алиас);
   - TTL по умолчанию. Распространение — от 10 минут до суток.
6. Проверить: `https://pkeeper.ru` и `https://pkeeper.ru/privacy.html`.

Альтернатива — любой другой статик-хостинг: залить те же файлы в корень домена.

## После запуска сайта — верификация брендинга Google (#21 → #22)

1. **Google Search Console** → добавить ресурс «Домен» `pkeeper.ru` → подтвердить
   TXT-записью в DNS (регистратор покажет куда);
2. **Google Cloud Console** → Google Auth Platform → Branding → **Verify branding**:
   - Homepage: `https://pkeeper.ru`
   - Privacy policy: `https://pkeeper.ru/privacy.html`
   - Authorized domain: `pkeeper.ru`
   - Support email: ваш адрес
3. scopes Drive — restricted: заполнить декларацию использования + демо-видео
   (съёмка экрана: открытие сейфа → подключение Drive → синхронизация);
4. Отправить на ревью (от нескольких дней до ~2 недель).

URLs из этого сайта же пойдут в карточку RuStore (#22).
