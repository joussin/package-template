
# Installation via Composer:


### Public repository:

https repo url:
> https://github.com/joussin/package-template.git


ssh repo url:
> git@github.com:joussin/package-template.git


### Private repository:

PRIVATE https repo url with credentials:

> https://sjoussin:ATBBDf5TXDmL2qBJprdZfRGr3sff9ADE8732@github.com/joussin/package-template.git





### Liaison des packages:

https://getcomposer.org/doc/04-schema.md#package-links
https://getcomposer.org/doc/05-repositories.md


type `vcs` ou `git`:

````json
{
  "repositories": [
    {
      "type": "git",
      "url": "https://github.com/joussin/package-template.git"
    }
  ],
  "require": {
    "php": ">=7.2.0",
    "joussin/package-template": "dev-develop"
  }
}
````

type `composer`:

````json
{
  "repositories": [
    {
      "type": "composer",
      "url": "http://packages.example.com"
    }
  ]
}
````


http://packages.example.com = http://packages.example.com/packages.json

packages.json:
````json
{
  "packages": {
    "joussin/package-template": {
      "dev-develop": {
        "name": "joussin/package-template",
        "version": "dev-develop",
        "source": {
          "url": "https://github.com/joussin/package-template.git",
          "type": "git",
          "reference" : "dev-develop"
        }
      },
      "0.0.1": {}
    }
  }
}
````


ex: https://raw.githubusercontent.com/joussin/package-template/develop/packages.json


````json
{
  "repositories": [
    {
      "type": "composer",
      "url": "https://raw.githubusercontent.com/joussin/package-template/develop/"
    }
  ]
}
````



packages list by url:

https://repo.packagist.org/p2/monolog/monolog.json:
````json
{
  "metadata-url": "/p2/%package%.json"
}
````
https://raw.githubusercontent.com/joussin/package-template/develop/p2/joussin/package-template.json
````json
{
  "metadata-url": "https://raw.githubusercontent.com/joussin/package-template/develop/p2/%package%.json"
}
````




--- 


# Configuration via Composer

### Basic Package composer.json:

````json
{
  "name": "joussin/package-template",
  "type": "library",
  "license": "MIT",
  "homepage": "https://github.com/joussin/package-template",
  "description": "Development package template",
  "keywords": ["package"],
  "authors": [
    {
      "name": "Joussin Stéphane",
      "email": "joussin@live.com",
      "role": "Developer"
    }
  ],
  
  "require": {
    "php": ">=7.2.0"
  },
  
  "require-dev": {
    "symfony/var-dumper": "^6.3"
  },
  
  "autoload": {
    "psr-4": {
      "Joussin\\Package\\": "src/"
    },
    "files": [
      "src/helpers/functions.php"
    ]
  },
  "extra": {
    "branch-alias": {
      "dev-master": "2.0.x-dev"
    },
    "laravel": {}
  },
  "minimum-stability": "dev",
  "prefer-stable": true,
  "conflict": {},
  "suggest": {},
  "scripts": {},
  "config": {
    "sort-packages": true
  }
}
````

### Psr Implementation

For a Psr Implementation, add :

````json
{

  "require": {
    "psr/container": "^1.1.1|^2.0.1"
  },

  "provide": {
    "psr/container-implementation": "1.1|2.0"
  }
}
````

### Script - Tests - Code Clean - Custom script

TODO: voir en détail

For code test & code clean or any script, add :

````json
{
  "require-dev": {
    "phpunit/phpunit": "^9.5.11|^10.0",
    "phpstan/phpstan": "^1.10",
    "friendsofphp/php-cs-fixer": "^3.5",
    "vimeo/psalm": "^4.7.3"
  },

  "scripts": {
    "phpcs": "phpcs",
    "phpstan": "phpstan analyse",
    "phpunit": "phpunit --no-coverage",
    "psalm": "psalm",
    "test": [
      "@phpcs",
      "@phpstan",
      "@psalm",
      "@phpunit"
    ]
  }
}
````

For a Custom bin/script, add :

````json
{
  "bin": [
    "bin/script"
  ],
  
  "scripts-descriptions": {
    "command_name": "Script description"
  },
  "scripts": {
    "command_name": ""
  }
}

````
