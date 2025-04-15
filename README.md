# Laravel + vite の練習

## クローン後の流れ

1 .env.exampleから.envを作り、APP_KEYを自動生成
```
cp .env.example .env
php artisan key:generate
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