# RPG

## Setup
Add to `~/.zshrc` or `~/.bashrcz` this
```
alias sail='[ -f sail ] && sh sail || sh vendor/bin/sail'
```
After that
```
cp .env.example .env

docker run --rm \
    -u "$(id -u):$(id -g)" \
    -v "$(pwd):/var/www/html" \
    -w /var/www/html \
    laravelsail/php82-composer:latest \
    composer install --ignore-platform-reqs
    
php artisan key:generate
sail up
```