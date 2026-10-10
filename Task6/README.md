# Task6 - Rate Limiting партнёрского API

[`nginx.conf`](./nginx.conf)

| Трафик | Ключ | Лимит |
|---|---|---|
| Партнёрский API `/api/partners/` | партнёр по `X-API-Key`, неизвестный ключ - 401 | 20 RPS, burst 10, 50 соединений |
| Сайт | IP клиента | 10 RPS, burst 20 |

`limit_req`, превышение - `429 Too Many Requests`.
Лимит считается на экземпляр ingress-nginx; общий лимит партнёра - на Smart Web Security (Task1).

```bash
docker run --rm -v "$PWD/nginx.conf:/etc/nginx/nginx.conf:ro" nginx:alpine nginx -t
```
