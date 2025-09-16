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

## 作業開始の手順

docker compose up -d でコンテナを起動  
localhost:8080でLaravelのhome画面が表示されていたら成功

## よく使うDocker comand

起動しているコンテナを表示（ターミナルからでもOK）
```
docker ps
# docker-compose.ymlに記述してあるコンテナが起動してればOK
```

コンテナの中に入る
```
docker compose exec <入りたいコンテナ名>
```

コンテナから出る
```
exit
```

## よく使うLaravelコマンド
Laravelの標準コマンド php artisan  

マイグレーションの実行(DBを操作)  
```
php artisan migrate
```
