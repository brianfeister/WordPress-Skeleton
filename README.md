# Getting Started

To get the project locally, you'll want to use the development branch.  The `master` branch is reserved for staying current with the upstream parents ( (WP-Skeletone)[https://github.com/markjaquith/WordPress-Skeleton] & (WP-Stack)[https://github.com/brianfeister/WP-Stack] ).

So, let's take it from zero:
* Create a new MySQL database in PHPmyAdmin
* Navigate to the location where want to keep the project locally in terminal and do
```git clone --recursive -b develop git@github.com:brianfeister/WordPress-Skeleton.git```
* Open `local-config-sample.php`, replace the credentials with the database you just created and then save it as `local-config.php`.
* The `/shared` directory is empty by default, but in order to upload files, you'll need to create a `content` directory inside it and then a `uploads` directory inside the newly created `content` directory.  Final file structure should be `/shared/content/uploads`.
* Go into `wp-config.php` and comment out `define('MULTISITE', true);` through `define('BLOG_ID_CURRENT_SITE', 1);` so that it looks like this:

```
// ===========================================================================================
// Multisite
// ===========================================================================================
define('WP_ALLOW_MULTISITE', true);
// define('MULTISITE', true);
// define('SUBDOMAIN_INSTALL', true);
// define('DOMAIN_CURRENT_SITE', 'artsite.devxlocal.com');
// define('PATH_CURRENT_SITE', '/cms/');
// define('SITE_ID_CURRENT_SITE', 1);
// define('BLOG_ID_CURRENT_SITE', 1);
```

* In your web browser, navigate to the `/cms` directory of your local path where you cloned the git project. You should get the default WP install screen.  Complete the install.
* Go to **Tools -> Network Setup**, scroll to the bottom, click **Install Network**.
* **DO NOT** follow the instructions on the next page, rather, just go back and uncomment the Multisite section above, restoring it to it's original format.
* Refresh your WP admin in browser, you'll be logged out.  Log back in and you're done.

## WordPress Skeleton

This is simply a skeleton repo for a WordPress site. Use it to jump-start your WordPress site repos, or fork it and customize it to your own liking!

## Assumptions

* WordPress as a Git submodule in `/cms/`
* Custom content directory in `/content/` (cleaner, and also because it can't be in `/cms/`)
* `wp-config.php` in the root (because it can't be in `/cms/`)
* All writable directories are symlinked to similarly named locations under `/shared/`.
