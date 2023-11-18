
**Base composer**

Package composer.json:

````json
{
  "name": "packages/package-template",
  "type": "library",
  "description": "Development package template",
  "keywords": ["package"],
  "authors": [
    {
      "name": "Joussin Stéphane",
      "email": "joussin@live.com",
      "role": "Developer"
    }
  ],
  "homepage": "https://github.com/joussin",
  "license": "MIT",
  
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

---

**Psr Implementation**

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



---


**Script - Tests - Code Clean**

TODO: voir en détail

For code test & code clean, add :

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


For a bin/script Implementation, add :


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

