# Laravel + vite の練習

## クローン後の流れ

1 .env.exampleから.envを作る
```
cp .env.example .env
```
  
2 .envのDV設定等を環境に合わせて修正  
  
3 起動準備 (nodeの準備等)
```
docker compose up -d --build
docker compose exec app composer install
docker compose exec node sh
npm install && npm run build
```
  
4 Laravelセットアップ
```
docker compose exec app php artisan migrate
```