# UI Tests With Selenium And Specflow
ExampleUI Tests project using  .NetCore/C#.<br />
Uses Specflow BDD framework and Selenium Webdriver.<br />
Added option to run from Docker containers.<br />

## Usage:

### 1. Run tests In Visual Studio from local machine
Preconditions:
- Visual Studio 2017 or later
- dotnet-core 2.1
https://dotnet.microsoft.com/download/dotnet-core/2.1

Steps:
- In Visual Studio: Test Explorer -> Run Tests

OR

### 2. Run tests using command line
Preconditions:
- dotnet-core 2.1
https://dotnet.microsoft.com/download/dotnet-core/2.1

Steps:
- Navigate to AutomationHomeExam project folder and execute command: 
dotnet test

OR

### 3. Run in docker container
Preconditions:
- Docker 19.03.7
- Docker-Compose 3.4

Steps:
- Adjust appsettings.json file as described in section Configuration
- Navigate to UITests project folder and execute command: 
docker-compose up

## Test Results Reports
Test Result Reports are stored in /Reports folder next to UITests.dll (by default \bin\Debug\netcoreapp2.1)
However Test Result Reports folder can be specified in appsettings.json file

## Configuration
All parameters available for test run configuration see in appsettings.json file<br />
Below are samples of different test run configuration appsettings.json

### 1. Configuration sample to run from local machine:
```json
{
  "compilerOptions": {
    "noImplicitAny": false,
    "noEmitOnError": true,
    "removeComments": false,
    "sourceMap": true,
    "target": "es5"
  },

  "WebDriverConfiguration": {
    "WebDriverToUse": "Chrome",
    "WebDriverToUse_Comments": "Supported Web Drivers : Chrome, Firefox",
    "ImplicitlyWait": 60,
    "PageLoadTimeout": 60,
    "UseRemote": false,
    "RemoteURI": "",
    "UserAgent": "Apache-HttpClient/4.5.7",
    "Arguments": [ "--no-sandbox" ]
  },

  "ReportConfiguration": {
    "ReportPath": "/Reports/index.html",
    "ScreenshotsPath": "Reports/Screenshots/"
  }
}
```

### 2. Configuration sample to run in docker container:
```json
{
  "compilerOptions": {
    "noImplicitAny": false,
    "noEmitOnError": true,
    "removeComments": false,
    "sourceMap": true,
    "target": "es5"
  },

  "WebDriverConfiguration": {
    "WebDriverToUse": "Chrome",
    "WebDriverToUse_Comments": "Supported Web Drivers : Chrome, Firefox",
    "ImplicitlyWait": 60,
    "PageLoadTimeout": 60,
    "UseRemote": true,
    "RemoteURI": "http://chromedriver:4444/wd/hub",
    "UserAgent": "Apache-HttpClient/4.5.7",
    "Arguments": [ "--no-sandbox", "--headless" ]
  },

  "ReportConfiguration": {
    "ReportPath": "/Reports/index.html",
    "ScreenshotsPath": "Reports/Screenshots/"
  }
}
```
