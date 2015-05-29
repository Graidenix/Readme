#Librarius (developer guide)#

## Requirements ##
1. [Git](https://github.com/msysgit/msysgit/releases/download/Git-1.9.5-preview20150319/Git-1.9.5-preview20150319.exe)
1. [SourceTree](http://downloads.atlassian.com/software/sourcetree/windows/SourceTreeSetup_1.6.14.exe)*
1. [PHPStorm](https://download.jetbrains.com/webide/PhpStorm-8.0.3.exe)
1. [NodeJS x86](http://nodejs.org/dist/v0.12.4/node.exe) or [NodeJS x64](http://nodejs.org/dist/v0.12.4/x64/node.exe) with follow packages:
   
   + **Bower**: `npm i -g bower`
   + **Grunt**: `npm i -g grunt`
   + **Grunt CLI**: `npm i -g grunt-cli`
   + **JS Hint**: `npm i -g jshint`
   + **LESS**: `npm i -g less`

\* - optional

------------

## Install ##
+ Clone the source: `git clone https://grigore_odajiu@bitbucket.org/grigore_odajiu/librarius-new.git`
+ Checkout the branch *feature/site_v2* : 

  1. `$ git fetch`
  2. `$ git checkout feature/site_v2`
  
+ Open terminal in the root of project.

  1. `$ npm install`
  2. `$ cd site`
  3. `$ bower install`
  4. `$ cd ../admin`
  5. `$ bower install`
  
+ Setup the apache2 vhost file for site:
```Shell
<VirtualHost *:80>
    DocumentRoot "[PATH_TO_SITEROOT]\librarius-new\site\public"
    SetEnv CI_ENV development
    ServerName librarius.dev
    ErrorLog "logs/librarius-error.log"
    CustomLog "logs/librarius-access.log" common
</VirtualHost>
```
+ Setup the apache2 vhost file for admin:
```Shell
<VirtualHost *:80>
    DocumentRoot "[PATH_TO_SITEROOT]\librarius-new\admin\public"
    SetEnv CI_ENV development
    ServerName admin.librarius.dev
    ErrorLog "logs/librarius-error.log"
    CustomLog "logs/librarius-access.log" common
</VirtualHost>
```
+ Open browser: [librarius.dev](http://librarius.dev/) and [admin.librarius.dev](http://admin.librarius.dev/) to be sure that everything is **OK**
+ Open _PHPStorm_ and add the project. 
+ Now you are ready to start development

------------

## Site Routes ##

| Page name     | Controller    | URI Path                |
| ------------- | ------------- | ----------------------- |
| Home          | Home          | `/home`                 |
| Catalog       | Catalog       | `/catalog`              |
| Recomandari   | Catalog       | `/catalog/recomends`    |
| Categorie     | Catalog       | `/catalog/books/sci-fi` |
| Autori        | Author        | `/author`               |
| Autor         | Author        | `/author/vasya_pupkin`  |
| Carte         | Product       | `/product/book`         |
| Basket        | Basket        | `/basket`               |
| Editura       | Publisher     | `/publisher`            |
| Cabinetul     | User          | `/user`                 |
| Login         | User          | `/user/login`           |
| Whishlist     | User          | `/wishlist`             |
| About us      | Page          | `/about-us`             |

------------

## Design hints ##

- [Vitesse](http://demo4plazathemes.com/19/ma_vitesse/)
- [Transvelo](http://transvelo.in/demo/html/bookshop/)
