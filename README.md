# Code Analysis with SonarQube in .NET Projects

https://developer.okta.com/blog/2021/09/08/sonar-qube-dotnet#analysis-results-in-sonarqube

The article published on Okta's blog focuses on the use of SonarQube in .NET projects. SonarQube is an open-source platform used to assess the quality of source code, and it is widely integrated into .NET development processes to provide detailed analysis and reports on code quality. This platform is commonly used to build web and desktop applications using languages such as C# and VB.NET. SonarQube provides insights into various aspects of code quality, including detection of duplicated code, security vulnerabilities, potential bugs, and adherence to coding standards.

## Concepts Learned

1. **SonarQube Setup in .NET Projects**: The article provides guidance on configuring SonarQube to analyze .NET projects, including installing SonarScanner and configuring the project properties file.

2. **Code Analysis Execution**: The steps for executing code analysis using SonarScanner are also covered, including generating reports and viewing results on the SonarQube dashboard.

3. **Interpreting Results**: The article explores how to interpret code analysis results in SonarQube, identifying problematic areas such as duplicated code, security vulnerabilities, and coding standard violations.

4. **Code Quality Improvement**: Strategies for improving code quality based on insights provided by SonarQube are also discussed, including code refactoring, bug fixing, and adoption of coding best practices.

<img alt="sonarqube" src="./assets/Captura de tela 1.png">

This image shows the SonarQube dashboard with general information such as bug counters, vulnerabilities, code issues, and code duplication counts, providing a simplified view with direct metrics.

More detailed metrics and analysis can also be seen in the "Measures" tab.

<img alt="sonarqube" src="./assets/Captura de tela 2.png">

<img alt="sonarqube" src="./assets/Captura de tela 3.png">

The "Issues" tab allows for a deeper dive into source code analysis. SonarQube reports on all possible issues, ranging from minor concerns to critical bugs. Each issue in the code can be explored, along with an explanation and an estimated time to resolve it.

<img alt="sonarqube" src="./assets/Captura de tela 4.png">

# SampleApp-SonarQube

# Analyze Your Code Using SonarQube, Docker and .NET Core

This app is an example app for learning how to use SonarQube on your projects. For more details please read [Analyze Your Code Using SonarQube, Docker and .NET Core](link_to_replace) to see a detailed instruction on how to do that.

**Prerequisites:**

- [Java 11](https://adoptopenjdk.net/)+
- [Docker](https://docs.docker.com/get-docker/)
- [.NET Core](https://dotnet.microsoft.com/download)
- [SonarScanner for .NET Core](https://github.com/SonarSource/sonar-scanner-msbuild/releases/download/4.7.1.2311/sonar-scanner-msbuild-4.7.1.2311-netcoreapp2.0.zip)

**Table of Contents**

- [Getting Started](#getting-started)
- [Help](#help)
- [License](#license)

## Getting Started

Begin with running SonarQube on Docker:
```sh
docker run -d --name sonarqube -p 9000:9000 -p 9092:9092 sonarqube
```

**NOTE:** You'll be able to login with `admin/admin`. After first login, you will be promted to change the default credentials.

In order to run SonarScanner, run the following commands:

```sh
dotnet sonarscanner begin /k:"project-key" /d:sonar.login=admin /d:sonar.password=admin
dotnet build <path_to_solution.sln>
dotnet sonarscanner end /d:sonar.login=admin /d:sonar.password=admin
```

> **NOTE:** Remember to replace "path_to_solution" and "password" with correct ones for your example.

## Help

Please post any questions as comments on the [blog post](link_to_replace), or visit our [Okta Developer Forums](https://devforum.okta.com/). You can also ask them on [Stack Overflow with the `sonarqube` tag](https://stackoverflow.com/tags/sonarqube).

## License

Apache 2.0, see [LICENSE](LICENSE).
