- Laravelプロジェクトの作成
```
composer create-project laravel/laravel=6.18.* .
```

- ドキュメントルートを以下に変更
```
/var/www/プロジェクト名/public
```

- apacheの再起動
コンテナ内ではsystemctlが使えない
```
service restart apache2
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
