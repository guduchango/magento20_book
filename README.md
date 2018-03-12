# Example Project Magento 2.0.17 with simpledata:deploy

## Creating magento 2 theme

### change configurations admin
```
system >> cache magnament >> full page caching (disabled)
```
### create folders
```
mkdir ./app/design/frontend/Example
mkdir ./app/design/frontend/Example/exercice
```
### make file with content:
#### ./app/design/frotend/Example/exercice/registration.php
```
<?php
\Magento\Framework\Component\ComponentRegistrar::register(
\Magento\Framework\Component\ComponentRegistrar::THEME,
'frontend/Example/exercice',
__DIR__
);
```
### make file with content:
#### ./app/design/frotend/Example/exercice/theme.xml
```
<theme xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:noNamespaceSchemaLocation="urn:magento:framework:Config/etc/theme.xsd">
<title>Example Exercice</title>
<parent>Magento/blank</parent>
</theme>
```
### add image to the theme, put imagen where you want
```
...
<title>Example Exercice</title>
<parent>Magento/blank</parent>
<media>
<preview_image>media/preview.png</preview_image>
</media>
</theme>
```
### clear cache
```
./bin/magento  cache:clean
./bin/magento  cache:flush
composer install
```
### choose new theme
```
stores >> configuration >> design >> example excercice
```
### flush cache reload frotend
```
./bin/magento  cache:flush
```
### enable template hints in the frontend
```
stores >> configuration >> advanced >> developer >> store view (main website)
stores >> configuration >> advanced >> developer >> debug >> Enabled Template Path Hints for Storefront (yes)
stores >> configuration >> advanced >> developer >> debug >> Add Block Names to Hints (yes)
```

### make a folder
```
mkdir ./app/design/frontend/Example/exercice/web
mkdir ./app/design/frontend/Example/exercice/web/images
```