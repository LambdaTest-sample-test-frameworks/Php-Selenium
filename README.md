# Run Selenium Tests With PHP — TestMu AI (Formerly LambdaTest)

![image](https://user-images.githubusercontent.com/70570645/171994020-d3c81aca-bd93-4467-a372-ff0283fef8df.png)
<p align="center">
  <a href="https://www.testmuai.com/blog/?utm_source=github&utm_medium=repo&utm_campaign=php-selenium" target="_bank">Blog</a>
  &nbsp; &#8901; &nbsp;
  <a href="https://www.testmuai.com/support/docs/?utm_source=github&utm_medium=repo&utm_campaign=php-selenium" target="_bank">Docs</a>
  &nbsp; &#8901; &nbsp;
  <a href="https://www.testmuai.com/learning-hub/?utm_source=github&utm_medium=repo&utm_campaign=php-selenium" target="_bank">Learning Hub</a>
  &nbsp; &#8901; &nbsp;
  <a href="https://www.testmuai.com/newsletter/?utm_source=github&utm_medium=repo&utm_campaign=php-selenium" target="_bank">Newsletter</a>
  &nbsp; &#8901; &nbsp;
  <a href="https://www.testmuai.com/certifications/?utm_source=github&utm_medium=repo&utm_campaign=php-selenium" target="_bank">Certifications</a>
  &nbsp; &#8901; &nbsp;
  <a href="https://www.youtube.com/@TestMuAI" target="_bank">YouTube</a>
</p>
&emsp;
&emsp;
&emsp;

*Learn how to run your PHP automation testing scripts on the TestMu AI platform*

[<img height="58" width="200" src="https://user-images.githubusercontent.com/70570645/171866795-52c11b49-0728-4229-b073-4b704209ddde.png">](https://accounts.lambdatest.com/register)


## Table Of Contents

* [Pre-requisites](#pre-requisites)
* [Run Your First Test](#run-your-first-test)
* [Local Testing With PHP](#testing-locally-hosted-or-privately-hosted-projects)

## Prerequisites

Before you begin automation testing with Selenium, you would need to:

* Make sure that you have the latest **PHP** installed on your system. You can download and install **PHP** using following commands in the terminal:

  * **MacOS:** Previous versions of **MacOS** have **PHP** installed by default. But for the latest **MacOS** versions starting with **Monterey**, **PHP** has to be downloaded and installed manually by using below commands: 
  ```bash
  /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
  brew install php
  ```
    * **Windows:** 
  ```bash
  sudo apt-get install curl libcurl3 libcurl3-dev php
  ```
  **Note:** For **Windows**, you can download **PHP** from [here](http://windows.php.net/download/). Also, refer to this [documentation](http://php.net/manual/en/install.windows.php) for ensuring the accessibility of PHP through Command Prompt(cmd).

* Download **composer** in the project directory ([Linux/MacOS](https://getcomposer.org/download/), [Windows](https://getcomposer.org/doc/00-intro.md#installation-windows)).

  **Note:** To use the **composer** command directly, it either should have been downloaded in the project directory or should be accessible globally which can be done by the command below:
  ```bash
  mv composer.phar /usr/local/bin/composer
  ```
### Installing Selenium Dependencies And Tutorial Repo

**Step 1:** Clone the TestMu AI’s Php-Selenium repository and navigate to the code directory as shown below:

```bash
git clone https://github.com/LambdaTest-sample-test-frameworks/Php-Selenium
cd Php-Selenium
```
**Step 2:** Install the composer dependencies in the current project directory using the command below:
```bash
composer install
```

### Setting Up Your Authentication

Make sure you have your TestMu AI credentials with you to run test automation scripts on TestMu AI Selenium Grid. You can obtain these credentials from the [TestMu AI Automation Dashboard](https://automation.lambdatest.com/build) or through [TestMu AI Profile](https://accounts.lambdatest.com/login).

**Step 3:** Set TestMu AI `Username` and `Access Key` in environment variables.
  * For **Linux/macOS**:
  ```bash
  export LT_USERNAME="YOUR_USERNAME" export LT_ACCESS_KEY="YOUR ACCESS KEY"
  ```
  * For **Windows**:
  ```bash
  set LT_USERNAME="YOUR_USERNAME" set LT_ACCESS_KEY="YOUR ACCESS KEY"
  ```

## Run Your First Test

>**Test Scenario**: The sample LambdaTest.php file tests a sample to-do list app by marking couple items as done, adding a new item to the list and finally displaying the count of pending items as output.

Let's check the sample test script [LambdaTest.php](https://github.com/LambdaTest-sample-test-frameworks/Php-Selenium/blob/master/tests/LambdaTest.php) file.

### Configuration Of Your Test Capabilities

**Step 4:** In the test script, you need to update your test capabilities. Here, the code will select the basic capabilities such as OS, browser, browser version and so on.

```php
//Basic Test Configurations For PHP

$capabilities = array(
    "build" => "your build name",
    "name" => "your test name",
    "platform" => "macOS High Sierra",
    "browserName" => "Firefox",
    "version" => "64.0",
    "resolution" => "1280x1024",
    "selenium_version" => "3.13.0",
    "screenshot" => true,
    "firefox.driver" => v0.23.0
    )
```
You can generate capabilities for your test requirements with the help of our inbuilt [Desired Capability Generator](https://www.testmuai.com/capabilities-generator/).


### Executing the Test

**Step 5:** The tests can be executed in the terminal using the following command:

```bash
php tests/LambdaTest.php
```
Your test results would be displayed on the test console (or command-line interface if you are using terminal/cmd) and on [TestMu AI automation dashboard](https://automation.lambdatest.com/build). 

## Testing Locally Hosted Or Privately Hosted Projects

You can test your locally hosted or privately hosted projects with TestMu AI Selenium grid using TestMu AI Tunnel. All you would have to do is set up an SSH tunnel using tunnel and pass toggle `tunnel = True` via desired capabilities. TestMu AI Tunnel establishes a secure SSH protocol based tunnel that allows you in testing your locally hosted or privately hosted pages, even before they are live.

Refer our [TestMu AI Tunnel documentation](https://www.testmuai.com/support/docs/testing-locally-hosted-pages/) for more information.

Here’s how you can establish TestMu AI Tunnel.

Download the binary file of:
* [TestMu AI Tunnel for Windows](https://downloads.lambdatest.com/tunnel/v3/windows/64bit/LT_Windows.zip)
* [TestMu AI Tunnel for macOS](https://downloads.lambdatest.com/tunnel/v3/mac/64bit/LT_Mac.zip)
* [TestMu AI Tunnel for Linux](https://downloads.lambdatest.com/tunnel/v3/linux/64bit/LT_Linux.zip)

Open command prompt and navigate to the binary folder.

Run the following command:

```bash
LT -user {user’s login email} -key {user’s access key}
```
So if your user name is lambdatest@example.com and key is 123456, the command would be:

```bash
LT -user lambdatest@example.com -key 123456
```
Once you are able to connect **TestMu AI Tunnel** successfully, you would just have to pass on tunnel capabilities in the code shown below :

**Tunnel Capability**

```
 "tunnel" => true
```

## Tutorials 📙

Check out our latest tutorials on PHP automation testing 👇

* [10 of the Best PHP Testing Frameworks for 2021](https://www.testmuai.com/blog/best-php-testing-frameworks-2021/)
* [Getting Started With Selenium PHP For Automation Testing](https://www.testmuai.com/blog/selenium-php-tutorial/)
* [Web automation testing using Selenium PHP on cloud-based Selenium Grid](https://www.testmuai.com/blog/selenium-php-tutorial)
* [Handling Multiple Browser Windows and Tabs in Selenium PHP](https://www.testmuai.com/blog/handling-windows-in-selenium-with-php/)
* [How to Work with Tables in Selenium PHP?](https://www.testmuai.com/blog/tables-in-selenium-php/)
* [How To Open IE and Edge Browsers In Selenium WebDriver Using PHP](https://www.testmuai.com/blog/open-ie-and-edge-browser-in-selenium-webdriver-using-php/)
* [How to Handle Synchronization in Selenium PHP Using Implicit and Explicit Wait?](https://www.testmuai.com/blog/implicit-explicit-wait-in-selenium/)
* [How to Execute JavaScript in Selenium PHP?](https://www.testmuai.com/blog/executing-javascript-in-selenium-php/)
* [How to Generate PHPUnit Coverage Report in HTML and XML?](https://www.testmuai.com/blog/phpunit-code-coverage-report-html/)
* [How to Setup CI/CD Pipeline with Bamboo for PHP Projects?](https://www.testmuai.com/blog/how-to-setup-cicd-pipeline-with-bamboo-for-php-projects/)


## Documentation & Resources :books:

      
Visit the following links to learn more about TestMu AI's features, setup and tutorials around test automation, mobile app testing, responsive testing, and manual testing.

* [TestMu AI Documentation](https://www.testmuai.com/support/docs/?utm_source=github&utm_medium=repo&utm_campaign=php-selenium)
* [TestMu AI Blog](https://www.testmuai.com/blog/?utm_source=github&utm_medium=repo&utm_campaign=php-selenium)
* [TestMu AI Learning Hub](https://www.testmuai.com/learning-hub/?utm_source=github&utm_medium=repo&utm_campaign=php-selenium)    

## TestMu AI Community :busts_in_silhouette:

The [TestMu AI Community](https://community.testmuai.com/) allows people to interact with tech enthusiasts. Connect, ask questions, and learn from tech-savvy people. Discuss best practises in web development, testing, and DevOps with professionals from across the globe 🌎

## What's New At TestMu AI ❓

To stay updated with the latest features and product add-ons, visit [Changelog](https://changelog.lambdatest.com/)

## 🚀 [LambdaTest is Now TestMu AI](https://www.testmuai.com/lambdatest-is-now-testmuai/)

👋 Welcome to TestMu AI, the next evolution of LambdaTest. As of January 2026, LambdaTest has officially rebranded to TestMu AI. We have evolved from a cross-browser testing cloud into a unified, AI-native quality engineering platform designed for the modern DevOps era.

Whether you have been part of the LambdaTest community for years or are just discovering TestMu AI, our mission remains the same: to help you ship faster with high-scale test execution, autonomous testing, and deep quality analytics.

**🔄 Our Rebrand Journey**

We chose the name TestMu AI to reflect our shift towards intelligent, autonomous testing. While our identity has changed, our core technology and commitment to the testing community stay the same.

**✨ Specialties**

- 🤖 AI-Native Test Execution (Formerly LambdaTest)
- ⚡ Autonomous Test Automation
- 🌐 Cross-Browser & Mobile Testing
- 📊 Unified Quality Intelligence

👉 Find [LambdaTest's New Home](https://www.testmuai.com/).