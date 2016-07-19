   ###composer 安装laravel
启用镜像服务的方式有两种：  
**系统全局配置：** 即将配置信息添加到 Composer 的全局配置文件 `config.json` 中。  
**单个项目配置：** 将配置信息添加到某个项目的 `composer.json` 文件中  
**例1：修改 composer 的全局配置文件（推荐方式）**  
 >打开命令行窗口（windows用户）或控制台（Linux、Mac 用户）并执行如下命令：  
`composer config -g repo.packagist composer https://packagist.phpcomposer.com`

**创建一个名为 blog 的 Laravel 项目**  
`composer create-project laravel/laravel blog --prefer-dist`
---
**例2：修改当前项目的 composer.json 配置文件：**  
>打开命令行窗口（windows用户）或控制台（Linux、Mac 用户），进入你的项目的根目录（也就是`composer.json` 文件所在目录），执行如下命令：  
`composer config -g repo.packagist composer https://packagist.phpcomposer.com`   


上述命令将会在当前项目中的 `composer.json`文件的末尾自动添加镜像的配置信息（你也可以自己手工添加）：
```
"repositories": {
   "packagist": {
    "type": "composer",
    "url": "https://packagist.phpcomposer.com"
   }
}
```
以 laravel 项目的 composer.json 配置文件为例，执行上述命令后如下所示（注意最后几行）：
```
{
    "name": "laravel/laravel",
    "description": "The Laravel Framework.",
    "keywords": [
        "framework",
        "laravel"
    ],
    "license": "MIT",
    "type": "project",
    "require": {
        "php": ">=5.5.9",
        "laravel/framework": "5.2.*"
    },
    "require-dev": {
        "fzaninotto/faker": "~1.4",
        "mockery/mockery": "0.9.*",
        "phpunit/phpunit": "~4.0",
        "symfony/css-selector": "2.8.*|3.0.*",
        "symfony/dom-crawler": "2.8.*|3.0.*"
    },
    "autoload": {
        "classmap": [
            "database"
        ],
        "psr-4": {
            "App\\": "app/"
        }
    },
    "autoload-dev": {
        "classmap": [
            "tests/TestCase.php"
        ]
    },
    "scripts": {
        "post-root-package-install": [
            "php -r \"copy('.env.example', '.env');\""
        ],
        "post-create-project-cmd": [
            "php artisan key:generate"
        ],
        "post-install-cmd": [
            "php artisan clear-compiled",
            "php artisan optimize"
        ],
        "pre-update-cmd": [
            "php artisan clear-compiled"
        ],
        "post-update-cmd": [
            "php artisan optimize"
        ]
    },
    "config": {
        "preferred-install": "dist"
    },
    "repositories": {
        "packagist": {
            "type": "composer",
            "url": "https://packagist.phpcomposer.com"
        }
    }
}
```
OK，一切搞定！试一下 composer install 来体验飞一般的速度吧！
