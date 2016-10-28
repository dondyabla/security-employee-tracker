## Security Employee Tracker

[![MIT Licence](https://badges.frapsoft.com/os/mit/mit.svg?v=103)](https://opensource.org/licenses/mit-license.php)   [![Build Status](https://travis-ci.org/scci/security-employee-tracker.svg?branch=master)](https://travis-ci.org/scci/security-employee-tracker) [![SensioLabsInsight](https://insight.sensiolabs.com/projects/7a8de56d-c4d4-492f-8ea3-d7f8a2441bad/mini.png)](https://insight.sensiolabs.com/projects/7a8de56d-c4d4-492f-8ea3-d7f8a2441bad) [![Scrutinizer Code Quality](https://scrutinizer-ci.com/g/scci/security-employee-tracker/badges/quality-score.png?b=master)](https://scrutinizer-ci.com/g/scci/security-employee-tracker/?branch=master) [![Dependency Status](https://www.versioneye.com/user/projects/58123c993130eb0043c41242/badge.svg?style=flat-square)](https://www.versioneye.com/user/projects/58123c993130eb0043c41242)

SET is for FSO and security officers of DoD companies to manage their employees. This includes the following:
- storing employee files
- tracking training (including renewal requirements)
- monitoring security clearance
- handling visitation rights to bases
- ensuring employees are prepared for travel
- storing miscellaneous notes.
- tracking employee security checks/duty roster that changes on a monthly, weekly or daily basis
- mass notification of news
- import of JPAS security clearance and investigation dates.

## Server Requirements

The application currently utilizes the PHP Laravel 5 framework. It also currently requires an LDAP connection.

- PHP >= 5.6.4
- OpenSSL PHP Extension
- PDO PHP Extension
- Mbstring PHP Extension
- Tokenizer PHP Extension
- XML PHP Extension
- LDAP PHP Extension
- [Composer](https://getcomposer.org/)

To view all the various options including cache, database, settings, email, etc..., view the [Laravel Documentation.](https://laravel.com/docs/master)

## Installation

1. In your command line/ssh, navigate to your site's root directory and execute `git clone https://github.com/scci/security-employee-tracker.git`. 
2. Update the files in the `config` directory.
  * `config/adldap.php` - your LDAP settings.
  * `config/auth.php` - Change the `guards => web => provider` (line 39) value to `adldap` (currently set to users for testing/validation)
  * `config/auth.php` - (line 111) Set the username for the admin/FSO.
3. Rename `.env.example` to `.env` and add your database and email settings.  
4. In your command line/SSH, navigate to the application root folder and run: 
   * `php artisan key:generate`
   * `composer install`
   * `php artisan migrate --force`
5. Point your domain/subdomain to the application's `public` folder.
6. Load the application in your browser.

## Updating

* Execute `git pull`. 

## Tests

You may run tests via executing the following in the application's root folder: `phpunit`

## Contribute

If you wish to submit enhancements, bug fixes and other changes, please submit a pull request. Pull request must have all changes for a single feature **and test cases**.

### License

The SET application is open-sourced software licensed under the [MIT license](http://opensource.org/licenses/MIT)
