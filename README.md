#Laravel Framework 9.52.16
環境構築
https://zenn.dev/eguchi244_dev/articles/laravel-and-docker-introduction-20230822

nginx/default.conf
root /var/www/<Laravelのプロジェクト名>/public;
この部分をLaravelのプロジェクト名に書き替えないとエラーになります。


それぞれのLaravelのインストール方法
docker-compose exec php bash
最新版
root@~/www# laravel new <Laravelのプロジェクト名>

バージョン指定
root@~/www# composer create-project "laravel/laravel=9.*" <Laravelのプロジェクト名>
