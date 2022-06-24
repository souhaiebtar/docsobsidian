update requirements by adding to `composer.json` and install package
`composer require "vendor/package:2.*"`


update requirements by adding pacakge to `require-dev` section in `composer.json` and install package (for package needed in dev only like php-csfixer and phpunit)
`composer require --dev "vendor/packageX:2.*"`


---

in **production** or **staging** run `composer install --no-dev`

in **development** or **testing** run `composer install`

composer dumpautoload --optimize 