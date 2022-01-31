# Php-Selenium-Sample

![Serenity](https://opengraph.githubassets.com/937a59bc66a1cce749f9f3b390cc8dbfdd66a9058aafa65cc5a25e9b611718af/LambdaTest-sample-test-frameworks/Php-Selenium)

## Prerequisites

To run your test script using php with Selenium.

1. Install php and setup environment variable.([Linux](https://www.php.net/manual/en/install.unix.debian.php), [Windows](https://www.php.net/downloads.php), [Mac](https://www.php.net/manual/en/install.macosx.php)).

## Steps to Run your First Test

Step 1. Clone the Php-Selenium-Sample Repository.

```
git https://github.com/LambdaTest-sample-test-frameworks/Php-Selenium
```

Step 2. Inside selenide-selenium-sample folder, export the Lambda-test Credentials. You can get these from your automation dashboard.

<p align="center">
   <b>For Linux/macOS:</b>
```
export LT_USERNAME="YOUR_USERNAME"
export LT_ACCESS_KEY="YOUR ACCESS KEY"
```
<p align="center">
   <b>For Windows:</b>
```
set LT_USERNAME="YOUR_USERNAME"
set LT_ACCESS_KEY="YOUR ACCESS KEY"
```
Step 3. Install Composer
```
$ php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');"
$ php -r "if (hash_file('SHA384', 'composer-setup.php') === '93b54496392c062774670ac18b134c3b3a95e5a5e5c8f1a9f115f203b75bf9a129d5daa8ba6a13e2cc8a1da0806388a8') { echo 'Installer verified'; } else { echo 'Installer corrupt'; unlink('composer-setup.php'); } echo PHP_EOL;"
$ php composer-setup.php
$ php -r "unlink('composer-setup.php');"
```
Step 4. Install dependencies by composer.
```
composer install 
```
Step 5. To run a test, run
``` 
php tests\LambdaTest.php 
```
## See the Results
You can see the results of the test on Lambdatest [Automation Dashboard](https://automation.lambdatest.com/build)
![Dashboard](https://github.com/LambdaTest-sample-test-frameworks/Php-Selenium/dashboard.png)

## About LambdaTest

[LambdaTest](https://www.lambdatest.com/) is a cloud based selenium grid infrastructure that can help you run automated cross browser compatibility tests on 2000+ different browser and operating system environments. LambdaTest supports all programming languages and frameworks that are supported with Selenium, and have easy integrations with all popular CI/CD platforms. It's a perfect solution to bring your [selenium automation testing](https://www.lambdatest.com/selenium-automation) to cloud based infrastructure that not only helps you increase your test coverage over multiple desktop and mobile browsers, but also allows you to cut down your test execution time by running tests on parallel.

### Resources

##### [SeleniumHQ Documentation](http://www.seleniumhq.org/docs/)

##### [NUnit Documentation](https://github.com/nunit/nunit/wiki)
