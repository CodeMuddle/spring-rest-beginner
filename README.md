# spring-rest-beginner
Beginner guide to creating rest api using spring boot

## Goal
Create a system that tells you the time in one city, if you give it(the system) another time from a different city.

```sh
# what time is "10:30 PM kathmandu", in New York?

# input
curl http://localhost:8080/api/v1/time/New York?time=10:30 PM&city=Kathmandu

# output
{
  "city": "New York",
  "time": "12:45 PM"
}
```

## Step by Step

### Code Writing
* Prerequisite: You should have your app running locally!

### Code Tracking
* Initialize git repository in your project

```sh
# inside the root folder of your project
git init
```

* Create a `develop` branch
```sh
git checkout -b develop
```

* Create an empty **Github repository**
  * Go to [Github](https://github.com)
  * Look for *New repository* button, then click it
  * Enter the name `time-checker` of your repository
  * Click *Create repository*
  
* Configure your local machine to send code to Github server
```sh
git remote add origin <url of the repository you created in porevious step>
```

* Add and push all your source code to github
```sh
git add .
git commit -m "create one api that allows users to view time from different cities"
git push origin develop:develop
```

### Writing Tests

* Go to [TestNG website](http://testng.org/doc/) to learn how to use it
  * You can also look at this [Beginner Tutorial](https://www.mkyong.com/unittest/testng-spring-integration-example/)

* Write one unit test for a method that is in charge of computing the time.

* Add configuration to run the test in `build.gradle`

* Make sure you can run the test localy

### Test Automation
Configure **Travis-ci** to run your tests

* Go to [travi-ci.org](https://travis-ci.org/) and login with your github account.
* Go to your profile 
```sh
# the url should look like this after you go to your profile
https://travis-ci.org/profile/<github-username>
```

* Find your `time-checker` github project and click on the toogle button.
  * This will allow **travis-ci** to automatically run your tests

* In your root project folder, create a file called `.travis.yml` and paste in the code below
```
language: java
jdk:
- oraclejdk8
install: 
- "./gradlew build"
script: 
- "./gradlew test"
```

* Commit your changes and push the code to github server
  * Now if you go to **Travis-ci.org**, you should see your tests running!

### Documentation
Tell other developers *how your code is structured*, *how to compile/run it locally*, and *what steps to follow when contributing to your project*

* Create a `README.md` file
* Add a **title** and **description** of your application
```markdwon
# Time Checker
Find out the local time of remote cities
```

* Explain how your code is structured *in short*
  * **NOTE:** this is varies from developer to developer
  
* Explain how to compile and run the project locally
```sh
# terminal
./gradlew clean build bootRun

# eclipse

# vagrant

# ...
```
  
* Explain how other developers can add more code to your project
  * **NOTE:** this varies from developer to developer
```sh
# Assume your local branch is currently develop

# for bug fixing
git checkout -b bugfix/<bug-short-name>

# for feature addition
git checkout -b feature/<feature-short-name>

# when done, make pull request to develop branch
```

* When you push your code to github, you should see your `README content` printed under the file/folder list!

### Test Coverage
TODO



