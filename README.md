# codeigniter3-multi-apps
Create multiple CodeIgniter 3 applications using one installation

## Introduction

CodeIgniter 3 allows you to  create multiple applications using one installation by simple creating multiple application folders, each with a unique name.
However, sometimes you may want your applications to share some resources for example you want your applications to share the same models, libraries and even configuration files. 

For you to be able to easily do this, your can modify the CodeIgniter core/Config and core/Loader so that it can fetch resources from a location different from the respective application folder. 
You can create this "shared" resources folder in the root of your application and then create your normal models and libraries the same way you would do in your application folders. 

This package allows you to create the following shared resources: 
- models
- libraries
- config (including database config)
- helpers
- language

Once you have created these resources, you will be able to load and use them exactly the same way you would with your files in application folders. 
N:B. Your files in the shared resources can be overridden or extended by files in your application folders, same way you override system files in your application folders. 
You can also override or extend system files in the shared folder by using the MY_filename.php method.


## Example - Creating 2 Applications
###### 1 root application served by `index.php` and an admin application served by `admin.php` 

- The root application will be inside the `site` folder and served by `index.php`
- The admin application will be inside the `admin` folder and served by admin.php 

1. Download an install CodeIgniter. 
2. Rename `application` folder to `site` 
3. Create a copy of the `site` folder and name it `admin` 
4. Download / clone this repository into the directory you installed CodeIgniter
5. Copy contents of `application` folder into both the `site` and `admin` folders. 
6. Delete CodeIgniter default `index.php` file 
7. Copy `index.sample.php` to `index.php`
8. Open `index.php` and change `$application_folder = 'application';` to `$application_folder = 'site';` somewhere around line `116` 
9. Copy `index.sample.php` to `admin.php`
8. Open `index.php` and change `$application_folder = 'application';` to `$application_folder = 'admin';` somewhere around line `116` 


Your directory structure should look like this: 
```
--root
   |
   |--site/
   |--admin/
   |--shared/
   |--system/
   |--index.php
   |--admin.php
```

