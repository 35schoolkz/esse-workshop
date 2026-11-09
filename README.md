# ESSE WORKSHOP

Интерактивная образовательная платформа по написанию эссе.

## Firebase: отзывы и закрытая админ-панель

1. Создайте проект в Firebase Console: https://console.firebase.google.com/
2. Добавьте Web App и скопируйте Firebase config в `firebase-config.js`.
3. В этом же файле замените `ADMIN_EMAIL_HERE` на Google email администратора.
4. В Authentication → Sign-in method включите Google.
5. В Firestore Database создайте базу данных.
6. Откройте Rules, вставьте содержимое `firestore.rules`, заменив `ADMIN_EMAIL_HERE` на тот же email, и опубликуйте правила.
7. В Authentication → Settings → Authorized domains добавьте `35schoolkz.github.io`, если домен отсутствует.
8. Опубликуйте изменения GitHub Pages.

### Безопасность
- Публичные посетители могут только отправлять отзывы.
- Читать, менять статус и удалять отзывы может только указанный подтверждённый Google-аккаунт.
- Firebase web config не является паролем; безопасность обеспечивают Firestore Rules.
- Не размещайте пароли, service account JSON или приватные ключи в репозитории.
- Включите Firebase App Check и настройте ограничения/защиту от спама перед широким запуском.
- Текущая реализация не собирает email автора отзыва. Пользователь может указать псевдоним.

Firebase Spark подходит для небольшого проекта в пределах бесплатных квот; проверьте актуальные лимиты в консоли Firebase.


## Әкімшіге логин мен құпиясөз арқылы кіру
1. Firebase Console → Authentication → Sign-in method бөлімінде **Email/Password** провайдерін қосыңыз.
2. Authentication → Users → Add user арқылы әкімшінің Gmail мекенжайы мен өзіңіз таңдаған құпиясөзді тіркеңіз.
3. `firebase-config.js` ішіндегі `adminEmail` мәнін сол Gmail-ге қойыңыз.
4. `firestore.rules` ішіндегі `ADMIN_EMAIL_HERE` мәнін дәл сол Gmail-ге ауыстырып, ережелерді жариялаңыз.
5. Сайттың «Әкімші» бөлімінде осы Gmail мен Firebase-та тіркелген құпиясөзді енгізіңіз.

Құпиясөзді `index.html`, `firebase-config.js` немесе GitHub-қа ешқашан жазбаңыз. Оны тек Firebase Authentication ішінде сақтаңыз. Егер бұрын Google арқылы кіру қосулы болса, оны өшіруге болады.
