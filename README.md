# Railsプロジェクトの新規作成
$ cd dev-kit

$ docker-compose build

$ docker-compose run --rm web bundle exec rails new . --force --database=mysql --skip-bundle　-d

# databaseのconfigの編集
$ vi config/database.yml
-> database.ymlをコピーする

# コンテナを作成して起動する
docker-compose up -d

# datebase.ymlの設定に従って、データベースを作成する
$ docker-compose run web bundle exec rake db:create

# コンテナ起動確認
docker ps

-> webとdbのプロセス実行されていることを確認

# Rails起動
$ docker exec -it dev-kit_web_1 bundle exec rails s -b 0.0.0.0

# その他：コマンド
$ docker-compose down
