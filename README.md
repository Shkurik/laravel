1) composer create-project --prefer-dist laravel/laravel

2) run project = php -S localhost:8080 -t public
   http://localhost:8080

3) composer require --dev barryvdh/laravel-ide-helper
composer.json ->
"scripts": {
    "post-update-cmd": [
        "Illuminate\\Foundation\\ComposerScripts::postUpdate",
        "@php artisan ide-helper:generate",
        "@php artisan ide-helper:meta"
    ]
},

4) php artisan vendor:publish --provider="Barryvdh\LaravelIdeHelper\IdeHelperServiceProvider" --tag=config

config/ide-helper.php:
'include_fluent' => true