# Installing Magento Modules

This Guide will take you to instructions to install magento modules. where we have two different ways to do so which is composer and manual installation.

## Composer

Since php uses composer as package manager you surely can install additional magento extensions using this way. there will be multiple extensions eshops that provide the extensions you buy or get for free as composer package. after we get our package name which looks like this `<vendor_name>/<module_name>` all we need is to install it into magento and to do so please do as following:

1. make sure magento is error free.
2. enable maintenance mode
```
sudo php bin/magento maintenance:enable
```
3. install the composer package
```
composer require <vendor_name>/<module_name>
```
4. update magento dependecies
```
sudo php bin/magento setup:upgrade
```

5. compile dependency injection code 

```
sudo bin/magento setup:di:compile
```
6. flush the cache 
```
sudo php bin/magento cache:flush
```
7. disable maintenance mode
```
sudo php bin/magento maintenance:disable
```

8. reset file permissions 

```
sudo chmod 777 var/ pub/ generated/ -R
```

## Manual - extensions

as an alternative way for installing magento extensions that maybe not provided from [magento offical repo and marketplace](https://marketplace.magento.com/) you can install extensions in `<magento_root>/app/code` directory and to do so we need to  


1. make sure magento is error free.
2. enable maintenance mode
```
sudo php bin/magento maintenance:enable
```
3. copy/uncompress the code extension files to `app/code` directory

4. update magento dependecies
```
sudo php bin/magento setup:upgrade
```

5. compile dependency injection code 

```
sudo bin/magento setup:di:compile
```
6. flush the cache 
```
sudo php bin/magento cache:flush
```

7. disable maintenance mode
```
sudo php bin/magento maintenance:disable
```
8. reset file permissions 

```
sudo chmod 777 var/ pub/ generated/ -R
```

## Manual - themes

magento themes is major customization for magento apperance usually they are installed manually or created by developers as a special customization for their clients. either way themes are maintained in `<magento_root>/app/design` directory and then specified even more to whatever the theme is `frontend` theme for styling storefront or `adminhtml` theme for styling the admin dashboard which is called an `<area>`. in the end we will have directory like this `<magento_root>/app/design/<area>/<vendor>/<theme_name>` .

1. make sure magento is error free.
2. enable maintenance mode
```
sudo php bin/magento maintenance:enable
```
3. copy/uncompress the theme files to `app/design/<area>` directory

4. update magento dependecies
```
sudo php bin/magento setup:upgrade
```
5. flush the cache 
```
sudo php bin/magento cache:flush
```
6. disable maintenance mode
```
sudo php bin/magento maintenance:disable
```
7. reset file permissions 

```
sudo chmod 777 var/ pub/ generated/ -R
```