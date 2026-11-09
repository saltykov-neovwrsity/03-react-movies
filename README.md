# 03-react-movies

Застосунок для пошуку фільмів із сервісом TMDB, створений за допомогою Vite, React і TypeScript.

## Налаштування та запуск

1. Створіть файл `.env` у корені проєкту за зразком `.env.example` і додайте ваш токен доступу TMDB:

```env
VITE_TMDB_TOKEN=your_tmdb_read_access_token_here
```

2. Встановіть залежності та запустіть локальний сервер розробки:

```bash
npm install
npm run dev
```

## Перевірки

```bash
npm run typecheck
npm run lint
npm run format:check
npm run build
```

`npm run preview` запускає локальний перегляд production-збірки після `npm run build`.

## Функціональність

- Пошук фільмів за ключовим словом через TMDB API (`axios`, авторизація через Bearer-токен зі змінної оточення `VITE_TMDB_TOKEN`).
- Форма пошуку `SearchBar` реалізована через Form Actions із валідацією порожнього запиту та сповіщеннями `react-hot-toast`.
- Відображення списку знайдених фільмів у компоненті `MovieGrid`, індикатора завантаження `Loader` та повідомлення про помилку `ErrorMessage`.
- Детальна інформація про обраний фільм у модальному вікні `MovieModal` через `createPortal` із закриттям за кліком на хрестик, бекдроп або клавішею `Escape` та блокуванням скролу сторінки.

Кожен компонент має окрему папку в `src/components` із файлами `.tsx` і `.module.css`. Спільні типи містяться в `src/types/movie.ts`, а логіка HTTP-запитів — у `src/services/movieService.ts`.

CSS-модулі взято з [goitacademy/react-movies-styles](https://github.com/goitacademy/react-movies-styles); глобальну нормалізацію забезпечує `modern-normalize`.
