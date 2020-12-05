docker-compose run app rails new . --force --no-deps --database=postgresql --skip-bundle
docker-compose run app bundle update

このタイミングで database.yml を修正

docker-compose build --no-cache
docker-compose run app rails db:create
docker-compose run app rails webpacker:install

docker-compose run app yarn install --check-files
docker-compose run app yarn add jquery popper.js



docker-compose run app rails g rspec:install
docker-compose run app bundle exec guard init
docker-compose run app bundle exec spring binstub --all

---------
rails _6.0.3.4_ new . --webpacker