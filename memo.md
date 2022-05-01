- Laravelプロジェクトの作成
```
composer create-project laravel/laravel=6.18.* プロジェクト名
```

- サーバ起動
```
php artisan serve --host 0.0.0.0
```

- vueのインストール
```
npm install -D vue
npm install -D vue-template-compiler
```

- vueを使う
  - vueコンポーネントを作る
  - resources/js/app.jsの編集

- artisanコマンドの一覧表示
```
php artisan list
```

- db接続テスト
```
php artisan tinker
DB::connection()->getConfig();
DB::connection()->getPdo();
```

- migrationファイル作成
```
php artisan make:migration filename
```
